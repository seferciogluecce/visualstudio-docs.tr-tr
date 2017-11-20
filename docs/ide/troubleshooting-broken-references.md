---
title: "Bozuk başvurularda sorun giderme | Microsoft Docs"
ms.custom: 
ms.date: 03/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual C# projects, references
- Visual Basic projects, references
- troubleshooting references
- referencing files from projects
- referencing components, troubleshooting
ms.assetid: 00a9ade9-652e-40de-8ada-85f63cd183ee
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7a6216f70f6e9eab3887439dee2f35aa59de37c0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="troubleshoot-broken-references"></a>Bozuk başvurularda sorun giderme
Uygulamanızı kırık referans kullanmaya çalışırsa, bir özel durum hatası oluşturulur. Başvurulan bileşeni bulun yeteneğinin, hata için birincil tetikleyici olmakla birlikte bozuk bir başvuru düşünülebilir bazı durumlar vardır. Bu örnekler aşağıdaki listede gösterilir:  

-   Projenin başvurusu yanlış veya tamamlanmamış yoludur.  

-   Başvurulan dosya silindi.  

-   Başvurulan dosyası yeniden adlandırıldı.  

-   Ağ bağlantısını veya kimlik doğrulama başarısız oldu.  

-   Referans bilgisayarda yüklü değil bir COM bileşeni sağlamaktır.  

 Bu sorunları çözümler aşağıda verilmiştir.  

> [!NOTE]
>  Derleme dosyalarında proje dosyasında mutlak yollar ile başvurulur. Bu nedenle, yerel ortamlarında başvurulan bir derleme eksik geliþtiricili ortamında çalışan kullanıcıların mümkündür. Bu hataları önlemek için proje proje başvuruları eklemek için bu gibi durumlarda daha iyi olur. Daha fazla bilgi için bkz: [Derlemelerle programlama](/dotnet/framework/app-domains/programming-with-assemblies).

## <a name="reference-path-is-incorrect"></a>Başvuru yolu geçersiz  
 Farklı bilgisayarlarda Paylaşılan projeleri, her bilgisayarda farklı bir dizinde bir bileşen bulunduğunda bazı başvuruları bulunmayabilir. Başvurular (örneğin, MyComponent) bileşeni dosyasının adı altında depolanır. Bir başvuru projeye eklendiğinde, bileşen dosya klasör konumunu (örneğin, C:\MyComponents\\) eklenir **ReferencePath** proje özelliği.  

 Proje açıldığında, başvuru yolundaki dizinlerde bakarak bu başvurulan bileşen dosyaları bulmaya çalışır. Proje D:\MyComponents gibi farklı bir dizinde bileşen depolayan bir bilgisayarda açık olduğunda\\, başvurusu bulunamıyor ve bir hata görev listesinde görünür.  

 Bu sorunu gidermek için kırık referans silin ve ardından Başvuru Ekle iletişim kutusunu kullanarak değiştirin. Başka bir çözüm **başvuru yolu** projenin özellik sayfalarında madde ve klasörler listesinde doğru konuma işaret edecek şekilde değiştirin. **Başvuru yolu** özelliği, her bilgisayardaki her kullanıcı için kalıcıdır. Bu nedenle, başvuru yolun değiştirilmesi projenin diğer kullanıcıların etkilemez.  

> [!TIP]
>  Proje Proje başvuruları bu sorunları gerekmez. Şunları yapabilirsiniz, bu nedenle, dosya referansları yerine kullanın.  

#### <a name="to-fix-a-broken-project-reference-by-correcting-the-reference-path"></a>Referans yolu düzelterek bozuk proje başvurusu düzeltmek için  

1.  İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklatın ve **özellikleri**.  

2.  **Proje Tasarımcısı** görüntülenir.  

3.  Visual Basic kullanıyorsanız seçin **başvuruları** sayfasında ve tıklayın **başvuru yollarını** düğmesi. İçinde **başvuru yollarını** iletişim kutusunda, başvuru istediğiniz öğeyi içeren klasörün yolunu yazın **klasörü** alan ve ardından **klasörü Ekle** düğmesi.  

     veya  

     Visual C# kullanıyorsanız seçin **başvuru yollarını** sayfası. İçinde **klasörü** alan, başvuru ve ardından istediğiniz öğeyi içeren klasörün yolunu yazın **klasörü Ekle** düğmesi.  

## <a name="referenced-file-has-been-deleted"></a>Başvurulan dosya silindi  
 Başvurulan dosya silindi ve artık sürücüde yok mümkündür.  

#### <a name="to-fix-a-broken-project-reference-for-a-file-that-no-longer-exists-on-your-drive"></a>Artık bir dosyanın bozuk proje başvurusu diskinize düzeltmek için  

-   Başvuru silin.  

-   Bilgisayarınızda başka bir konuma başvuru zaten varsa, o konumdan okuyun.  

## <a name="referenced-file-has-been-renamed"></a>Başvurulan dosya yeniden adlandırıldı  
 Başvurulan dosyası yeniden adlandırıldı mümkündür.  

#### <a name="to-fix-a-broken-reference-for-a-file-that-has-been-renamed"></a>Kopuk bir başvuruyu yeniden adlandırılmış bir dosya için düzeltme  

-   Başvuru silin ve sonra yeniden adlandırılmış dosya için bir başvuru ekleyin.  

-   Bilgisayarınızda başka bir konuma başvuru bulunması durumunda içinde o konumdan okumak zorunda.

## <a name="network-connection-or-authentication-has-failed"></a>Ağ bağlantısı veya kimlik doğrulama başarısız oldu  
 Erişilemeyen dosyalar birçok olası nedeni olabilir: başarısız ağ bağlantısı veya başarısız bir kimlik doğrulama, örneğin. Her neden kurtarma benzersiz bir çeşit olabilir; Örneğin, gerekli kaynaklara erişimi için yerel yönetici başvurun gerekebilir. Ancak, başvuru silme ve onu kullanılan kod çözme her zaman bir seçenektir.

## <a name="com-component-is-not-installed-on-computer"></a>COM bileşeni bilgisayarda yüklü değil  
 Bir kullanıcı bir COM bileşeni başvuru ekledi ve kod bu bileşeni yüklü olmayan bir bilgisayarda çalıştırmak ikinci bir kullanıcı çalışırsa, ikinci kullanıcı başvuru bozuk olduğunu belirten bir hata alırsınız. İkinci bilgisayarda bileşeni yüklemeyi hatayı düzeltin. COM bileşenlerini başvurular projelerinizde kullanma hakkında daha fazla bilgi için bkz: [.NET Framework uygulamalarında COM birlikte çalışabilirliği](/dotnet/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications).  

## <a name="see-also"></a>Ayrıca bkz.  
 [Başvurular sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/references-page-project-designer-visual-basic.md)   