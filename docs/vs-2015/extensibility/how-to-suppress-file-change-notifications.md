---
title: 'Nasıl yapılır: dosya değişiklik bildirimlerini gösterme | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - suppress file change notification
ms.assetid: 891c1eb4-f6d0-4073-8df0-2859dbd417ca
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a17869c8c51f940abc03e3670e20768c61f8bc4f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49906513"
---
# <a name="how-to-suppress-file-change-notifications"></a>Nasıl yapılır: dosya değişiklik bildirimlerini gösterme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Metin arabelleğini temsil eden bir fiziksel dosya değiştirildiğinde, iletinin bir iletişim kutusu görüntüler **aşağıdaki öğelerdeki değişiklikleri kaydetmek istiyor musunuz?** Bu dosya değişikliği bildirimi bilinir. Birçok değişiklik dosyaya kullanacaksanız, ancak bu iletişim kutusunu tekrar tekrar görüntüleme hızlı bir şekilde rahatsız edici hale gelebilir.  
  
 Programlı olarak aşağıdaki yordamı kullanarak bu iletişim kutusunu gizleyebilirsiniz. Bunu yaparak, bir dosya hemen her zaman değişiklikleri kaydetmek için kullanıcıdan gerek kalmadan yeniden yükleyebilirsiniz.  
  
### <a name="to-suppress-file-change-notification"></a>Dosya değişikliği bildirimi gizlemek için  
  
1.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> hangi metin arabelleği nesnesi, açık dosya ile ilişkili olduğunu belirlemek için yöntemi.  
  
2.  Doğrudan <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> elde ederek dosya değişiklikleri yoksaymak için bellekte izlediği nesne <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl> alanından arabirim <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> (belge veri) nesnesi ve ardından uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> yöntemiyle `fIgnore` parametresi kümesine `true`.  
  
3.  Yöntemleri çağırma <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> arabirimler, bellek içinde güncelleştirilecek <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> (örneğin, bir alan bileşeninize eklendiğinde) dosya değişiklikleri nesne.  
  
4.  Dosyanın disk üzerinde bekleyen kullanıcı sürüyor olabilir düzenlemeleri göz önüne almadan değişikliklerle güncelleştirin.  
  
     Bu şekilde, doğrudan olduğunda <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> nesne dosyası için izlemeyi sürdürmek için değişiklik bildirimleri, bellekte metin arabelleğini diğer bekleyen düzenlemeler yanı sıra oluşturulan değişiklikleri yansıtır. Diskteki dosya sizin tarafınızdan oluşturulan en son kodu yansıtır ve herhangi daha önce kullanıcı tarafından değişiklikler kullanıcı tarafından düzenlenen kodda kaydedilir.  
  
5.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> yöntemi bildirmek için <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> ayarlayarak dosya değişikliği bildirimleri için izlemeyi sürdürmek için nesne `fIgnore` parametresi `false`.  
  
6.  Kaynak kodu denetimi (SCC) olduğu gibi dosyanın birkaç değişiklik planlıyorsanız dosya değişiklik bildirimlerini geçici olarak askıya almak için genel dosya değiştirme hizmeti söylemeniz gerekir.  
  
     Örneğin, dosyayı yeniden zaman damgası daha sonra değiştirirseniz, ayrı bir dosya olay değiştikçe yeniden yazma ve timestample işlemlerini her sayısı gibi dosya değişiklik bildirimlerini askıya gerekir. Bunun yerine çağırmalıdır genel dosya değişikliği bildirimini etkinleştirmek için <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx.IgnoreFile%2A> yöntemi.  
  
## <a name="example"></a>Örnek  
 Dosya değişikliği bildirimi Önle nasıl gösterir.  
  
```cpp#  
//Misc. helper classes  
  
CSuspendFileChanges::CSuspendFileChanges(  
    /* [in] */ const CString& strMkDocument,   
    /* [in] */ BOOL fSuspendNow /* = TRUE */)   
:  
    m_strMkDocument(strMkDocument),  
    m_fFileChangeSuspended(FALSE)  
{  
    if(fSuspendNow)  
        Suspend();  
}  
CSuspendFileChanges::~CSuspendFileChanges()  
{  
    Resume();  
}  
void CSuspendFileChanges::Suspend()  
{  
    USES_CONVERSION;  
  
    // Prevent suspend from suspending more than once.  
    if(m_fFileChangeSuspended)  
        return;  
  
    IVsRunningDocumentTable* pRDT =   
      _VxModule.GetIVsRunningDocumentTable();  
    ASSERT(pRDT);  
    if (!pRDT)  
        return;  
  
    CComPtr<IUnknown> srpDocData;  
    VSCOOKIE vscookie = VSCOOKIE_NIL;  
    pRDT->FindAndLockDocument(RDT_NoLock, T2COLE(m_strMkDocument),    
      NULL, NULL, &srpDocData, &vscookie);  
    if ( (vscookie == VSCOOKIE_NIL) || !srpDocData)  
        return;  
    CComPtr<IVsFileChangeEx> srpIVsFileChangeEx;  
    HRESULT hr = _VxModule.QueryService(SID_SVsFileChangeEx,   
      IID_IVsFileChangeEx, (void **)&srpIVsFileChangeEx);  
    if (SUCCEEDED(hr) && srpIVsFileChangeEx)  
    {  
        m_fFileChangeSuspended = TRUE;  
        srpIVsFileChangeEx->IgnoreFile(NULL, m_strMkDocument, TRUE);   
        srpDocData->QueryInterface(IID_IVsDocDataFileChangeControl,   
          (void**)&m_srpIVsDocDataFileChangeControl);  
        if(m_srpIVsDocDataFileChangeControl)  
            m_srpIVsDocDataFileChangeControl->IgnoreFileChanges(TRUE);  
    }  
}  
void CSuspendFileChanges::Resume()  
{  
    if(!m_fFileChangeSuspended)  
        return;  
  
    CComPtr<IVsFileChangeEx> srpIVsFileChangeEx;  
    HRESULT hr = _VxModule.QueryService(SID_SVsFileChangeEx,   
      IID_IVsFileChangeEx, (void **)&srpIVsFileChangeEx);  
    if (SUCCEEDED(hr) && srpIVsFileChangeEx)  
  
    srpIVsFileChangeEx->IgnoreFile(NULL, m_strMkDocument, FALSE);   
    if(m_srpIVsDocDataFileChangeControl)  
        m_srpIVsDocDataFileChangeControl->IgnoreFileChanges(FALSE);  
    m_fFileChangeSuspended = FALSE;  
    m_srpIVsDocDataFileChangeControl.Release();  
}  
// Misc. helper classes  
```  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Ardından durumunuz SCC, olduğu gibi dosyanın çok sayıda değişiklik içeriyorsa dosya değişiklikleri için izlemeyi sürdürmek için belge verileri uyarmadan önce genel dosya değişiklik bildirimlerini sürdürmek önemlidir.

