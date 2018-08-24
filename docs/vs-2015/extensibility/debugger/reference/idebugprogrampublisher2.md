---
title: IDebugProgramPublisher2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgramPublisher2
helpviewer_keywords:
- IDebugProgramPublisher2 interface
ms.assetid: b1d17f63-7146-4076-a588-034cfc6858b9
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8715309e80e22709cf6faa6e3cb8a46a616535be
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695253"
---
# <a name="idebugprogrampublisher2"></a>IDebugProgramPublisher2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgramPublisher2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogrampublisher2).  
  
Bu arabirim, hata ayıklama altyapısı (DE) veya hata ayıklama için programlar kaydetmek için özel bağlantı noktası sağlayıcıları sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugProgramPublisher2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Visual Studio programlar arasında birden çok işlemde hata ayıklama için görebilmesi için ayıklanan kaydetmek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 COM'ın arama `CoCreateInstance` işleviyle `CLSID_ProgramPublisher` almak için bu arabirimi (örneğe bakın). Bir DE veya özel bağlantı noktası sağlayıcısı bu arabirim, hataları ayıklanmakta olan programlar temsil eden program düğümleri kaydetmek için kullanır.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Bu arabirim, aşağıdaki yöntemleri uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)|Bir program düğüm DEs ve oturumu için hata ayıklama Yöneticisi (SDM) kullanılabilmesini sağlar.|  
|[UnpublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogramnode.md)|Böylece artık kullanılabilir bir program düğümü kaldırır.|  
|[PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md)|Bir program DEs ve SDM kullanılabilmesini sağlar.|  
|[UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)|Artık kullanılabilir olması bir program kaldırır.|  
|[SetDebuggerPresent](../../../extensibility/debugger/reference/idebugprogrampublisher2-setdebuggerpresent.md)|Bir hata ayıklayıcı mevcut olduğunu belirten bir bayrak ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim program ve program düğümleri kullanılabilir hale getirir (diğer bir deyişle, "bunları DEs ve oturum hata ayıklama Yöneticisi (SDM) tarafından kullanım için yayımlayan"). Yayımlanan programları ve program düğümleri erişim için [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) arabirimi. Bir program ayıklanmakta olan Visual Studio tanıyabilmesi tek yolu budur.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>Örnek  
 Bu örnekte, program yayımcı örneği oluşturmak ve bir program düğüm kaydettirmek gösterilmektedir. Bu öğreticide, alınmış [Program düğüm yayımlama](http://msdn.microsoft.com/en-us/d0100e02-4e2b-4e72-9e90-f7bc11777bae).  
  
```cpp#  
// This is how m_srpProgramPublisher is defined in the class definition:  
// CComPtr<IDebugProgramPublisher2> m_srpProgramPublisher.  
  
void CProgram::Start(IDebugEngine2 * pEngine)  
{  
    m_spEngine = pEngine;  
  
    HRESULT hr = m_srpProgramPublisher.CoCreateInstance(CLSID_ProgramPublisher);  
    if ( FAILED(hr) )  
    {  
        ATLTRACE("Failed to create the program publisher: 0x%x.", hr);  
        return;  
    }  
  
    // Register ourselves with the program publisher. Note that  
    // CProgram implements the IDebgProgramNode2 interface, hence  
    // the static cast on "this".  
    hr = m_srpProgramPublisher->PublishProgramNode(  
        static_cast<IDebugProgramNode2*>(this));  
    if ( FAILED(hr) )  
    {  
        ATLTRACE("Failed to publish the program node: 0x%x.", hr);  
        m_srpProgramPublisher.Release();  
        return;  
    }  
  
    ATLTRACE("Added program node.\n");  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)
