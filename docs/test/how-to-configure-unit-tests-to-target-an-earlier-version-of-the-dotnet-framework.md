---
title: "Nasıl yapılır: birim testlerini .NET Framework'ün önceki bir sürümünü hedefleyecek şekilde yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: adb6c011-5abd-41d2-8ead-08cd7579bf37
caps.latest.revision: "12"
ms.author: douge
manager: douge
ms.openlocfilehash: d7a899e16d79ba2aae40506eb3cd6739dcdb4397
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-configure-unit-tests-to-target-an-earlier-version-of-the-net-framework"></a>Nasıl yapılır: Birim Testlerini .NET Framework'ün Önceki Sürümünü Hedefleyecek Şekilde Yapılandırma
Microsoft Visual Studio test projesi oluşturduğunuzda, .NET Framework'ün en son sürüm varsayılan olarak hedef olarak ayarlanır. Visual Studio'nun önceki sürümlerden testi projelerini yükseltme yöntemini seçerseniz, ayrıca, bunlar .NET Framework'ün en son sürümünü hedefleyecek şekilde yükseltilir. Proje özelliklerini düzenleyerek, açıkça .NET Framework'ün önceki sürümlerinde projeyi yeniden hedefleyebilirsiniz.  
  
 .NET Framework'ün belirli sürümlerini hedefleyen test projeleri birim oluşturabilirsiniz. Hedeflenen sürüm 3.5 veya sonrasını olmalıdır ve bir istemci sürümü olamaz. Visual Studio belirli sürümlerini hedefleyen birim testleri için aşağıdaki temel destek sağlar:  
  
-   Birim testi projelerini oluşturabilir ve bunları belirli bir .NET Framework sürümü için hedef.  
  
-   Yerel makinenizde Visual Studio'dan belirli bir .NET Framework sürümünü hedefleyen birim testleri çalıştırabilirsiniz.  
  
-   MSTest.exe komut istemini kullanarak belirli bir .NET Framework sürümünü hedefleyen birim testleri çalıştırabilirsiniz.  
  
-   Birim testleri bir yapı aracısını bir yapının parçası olarak çalıştırabilirsiniz.  
  
 **SharePoint uygulamalarını test etme**  
  
 Yukarıda listelenen özellikleri de, yazma birim testleri ve Visual Studio kullanarak SharePoint uygulamaları için tümleştirme testleri sağlar. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Visual Studio kullanarak SharePoint uygulamaları geliştirmek için bkz: nasıl [SharePoint çözümleri oluşturma](/office-dev/office-dev/create-sharepoint-solutions), [oluşturma ve hata ayıklama SharePoint çözümlerini](/office-dev/office-dev/building-and-debugging-sharepoint-solutions) ve [doğrulama ve hata ayıklama SharePoint kodunu](/office-dev/office-dev/verifying-and-debugging-sharepoint-code).  
  
 **Sınırlamaları**  
  
 .NET Framework'ün önceki sürümlerini kullanmak üzere test projelerinizi yeniden hedeflediğinizde aşağıdaki sınırlamalar uygulanır:  
  
-   .NET Framework 3.5 çoklu sürüm desteği yalnızca birim testleri içeren test projeleri için desteklenir. .NET Framework 3.5, kodlanmış UI veya yük testi gibi diğer test türlerini desteklemiyor. Yeniden hedefleme test türleri için birim testleri dışında engellendi.  
  
-   .NET Framework'ün önceki bir sürümünde hedeflenen testleri yürütülmesi yalnızca varsayılan ana bilgisayar bağdaştırıcısı tarafından desteklenir. ASP.NET ana bilgisayar bağdaştırıcısı tarafından desteklenmiyor. ASP.NET Geliştirme Sunucusu bağlamında çalışacak şekilde ASP.NET uygulamaları .NET Framework'ün geçerli sürümüyle uyumlu olması gerekir.  
  
-   .NET Framework 3.5 çoklu sürüm desteği testlerini çalıştırdığınızda, veri koleksiyonu desteği devre dışı. Visual Studio komut satırı araçlarını kullanarak kod kapsamı çalıştırabilirsiniz.  
  
-   .NET Framework 3.5 kullanan birim testleri uzak makinede çalıştıramazsınız.  
  
-   Framework'ün önceki istemci sürümleri için birim testleri hedefleyemez.  
  
### <a name="re-targeting-to-a-specific-version-of-the-net-framework-for-visual-basic-unit-test-projects"></a>Belirli bir .NET Framework sürümü için Visual Basic birim testi projelerini için yeniden hedefleme  
  
1.  Yeni bir Visual Basic birim testi projesi oluşturun. Üzerinde **dosya** menüsünde seçin **yeni** ve ardından **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  Altında **yüklü şablonlar**, genişletin **Visual Basic**. Seçin **Test** ve ardından **Test projesi** şablonu.  
  
3.  İçinde **adı** metin kutusunda, Visual Basic için bir ad test projesi ve ardından **Tamam**.  
  
4.  Çözüm Gezgini'nde seçin **özellikleri** yeni Visual Basic test projesinin kısayol menüsünden.  
  
     Visual Basic test projeniz için özellikleri görüntülenir.  
  
5.  Üzerinde **derleme** sekmesini seçin **Gelişmiş derleme seçenekleri** aşağıdaki çizimde gösterildiği gibi.  
  
     ![Gelişmiş derleme seçenekleri](../test/media/howtoconfigureunittest35frameworka.png "HowToConfigureUnitTest35FrameworkA")  
  
6.  Kullanım **hedef Framework'ü (tüm yapılandırmaları)** hedef framework değiştirmek için aşağı açılan liste **.NET Framework 3.5** veya belirtme çizgisi B aşağıdaki çizimde gösterildiği gibi sonraki bir sürümü. Bir istemci sürümü belirtilmemelidir.  
  
     ![Aşağı listesi; hedef framework açılan & #45](../test/media/howtoconfigureunitest35frameworkstepb.png "HowToConfigureUniTest35FrameworkStepB")  
  
### <a name="re-targeting-to-a-specific-version-of-the-net-framework-for-visual-c-unit-test-projects"></a>Belirli bir .NET Framework sürümü için Visual C# birim testi projelerini için yeniden hedefleme  
  
1.  Yeni bir Visual C# birim testi projesi oluşturun. Üzerinde **dosya** menüsünde seçin **yeni** ve ardından **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  Altında **yüklü şablonlar**, genişletin **Visual C#**. Seçin **Test** ve ardından **Test projesi** şablonu.  
  
3.  İçinde **adı** metin kutusunda, bir ad için Visual C# test projesi ve ardından **Tamam**.  
  
4.  Çözüm Gezgini'nde seçin **özellikleri** , yeni Visual C# test projesinin kısayol menüsünden.  
  
     Visual C# test projeniz için özellikleri görüntülenir.  
  
5.  Üzerinde **uygulama** sekmesini seçin **hedef framework** ve ardından **.NET Framework 3.5** veya sonraki bir sürümünü gösterilen hedef framework.as değiştirmek için aşağı açılan listeden Aşağıdaki çizimde. Bir istemci sürümü belirtilmemelidir.  
  
     ![Aşağı listesi; hedef framework açılan & #45](../test/media/howtoconfigureunittest35frameworkcsharp.png "HowToConfigureUnitTest35FrameworkCSharp")  
  
### <a name="re-targeting-to-a-specific-version-of-the-net-framework-for-ccli-unit-test-projects"></a>Belirli bir .NET Framework sürümü için hedefleme C + yeniden +/ CLI birim testi projelerini  
  
1.  Yeni bir C++ birim testi projesi oluşturun. Üzerinde **dosya** menüsünde, select **yeni** ve ardından **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
    > [!WARNING]
    >  İçin yapı C + +/ CLI birim testlerini .NET framework'ün önceki bir sürümü için Visual C++ için karşılık gelen Visual Studio sürümünü kullanmanız gerekir. Örneğin, .NET Framework 3.5 hedeflemek için yüklemelisiniz [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)] ve [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)] Service Pack 1.  
  
2.  Altında **yüklü şablonlar**, genişletin **Visual C ++**. Seçin **Test** ve ardından **Test projesi** şablonu.  
  
3.  İçinde **adı** metin kutusunda, Visual C++ için bir ad test projesi ve ardından **Tamam**.  
  
4.  Çözüm Gezgini'nde seçin **projeyi** yeni Visual C++ test projenizden.  
  
5.  Çözüm Gezgini'nde bellekten Visual C++ test projesi seçin ve ardından **Düzenle \<proje adı > .vcxproj**.  
  
     .Vcxproj dosya Düzenleyicisi'nde açılır.  
  
6.  Ayarlama `TargetFrameworkVersion` sürüm 3.5 veya sonraki bir sürümde `PropertyGroup` etiketli `"Globals"`. Bir istemci sürümü belirtilmemelidir:  
  
    ```  
    <PropertyGroup Label="Globals">  
        <TargetName>DefaultTest</TargetName>  
        <ProjectTypes>{3AC096D0-A1C2-E12C-1390-A8335801FDAB};{8BC9CEB8-8B4A-11D0-8D11-00A0C91BC942}</ProjectTypes>  
        <ProjectGUID>{CE16D77A-E364-4ACD-948B-1EB6218B0EA3}</ProjectGUID>  
        <TargetFrameworkVersion>3.5</TargetFrameworkVersion>  
        <Keyword>ManagedCProj</Keyword>  
        <RootNamespace>CPP_Test</RootNamespace>  
      </PropertyGroup>  
  
    ```  
  
7.  .vcxproj dosyasını kaydedip kapatın.  
  
8.  Çözüm Gezgini'nde Seç **projeyi yeniden yükle** , yeni Visual C++ test projesinin kısayol menüsünden.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Oluşturma ve var olan kod için birim testleri çalıştırma](http://msdn.microsoft.com/en-us/e8370b93-085b-41c9-8dec-655bd886f173)   
 [SharePoint çözümleri oluşturma](/office-dev/office-dev/create-sharepoint-solutions)   
 [Derleme ve SharePoint çözümlerini hata ayıklama](/office-dev/office-dev/building-and-debugging-sharepoint-solutions)   
 [Gelişmiş derleyici Ayarları iletişim kutusu (Visual Basic)](../ide/reference/advanced-compiler-settings-dialog-box-visual-basic.md)