---
title: JavaScript bellek | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- dominators, memory analyzer (JavaScript)
- memory leaks (JavaScript)
- heap memory, JavaScript
- leaks, memory (JavaScript)
- snapshots, memory analyzer (JavaScript)
- JavaScript Memory Analyzer
- analyzing memory, JavaScript
- memory analyzer, JavaScript
ms.assetid: 78f8532b-7b4e-4b50-b8b7-68ca0926dd4e
caps.latest.revision: 54
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d0d1d45caa7f5bfe275cd851711dfbc9a8186d74
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49814954"
---
# <a name="javascript-memory"></a>JavaScript bellek
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

JavaScript bellek Çözümleyicisi, bellek kullanımını anlamak ve JavaScript kullanarak Windows için oluşturulan Store uygulamalarında bellek sızıntılarını bulmanıza yardımcı olması için Visual Studio'da kullanılabilir. Windows Phone Store ve Windows Store uygulamaları için desteklenen uygulamalarıdır.  
  
 JavaScript bellek Çözümleyicisi bunları sizin için neler yapabileceğini:  
  
- Hızlı bir şekilde bellek kullanım sorunlarını uygulamanızda en alakalı verileri vurgulayarak bulmanıza yardımcı olur.  
  
   İki anlık görüntü arasındaki farkları gösteren ve daha ayrıntılı görünüm bağlantıları verilmektedir anlık görüntü özetleri, bu verileri elde edersiniz.  
  
- Önceller, türleri ve kökleri sorunlarını gidermeye yardımcı olmak için görünümler sağlar.  
  
- JavaScript yığın verileri eyleme dönüştürülebilir olmayan bilgisini azaltın.  
  
   Uygulama kodunuzda doğrudan oluşturulmaz nesneleri otomatik olarak filtrelenir. Ayrıca, verileri nesne adına göre filtreleyebilirsiniz.  
  
  Çalışan bir uygulamayı bir bellek sızıntısı tanımlama işleminde size yol gösterir bir öğretici için bkz [izlenecek yol: bir bellek sızıntısını bulma (JavaScript)](../profiling/walkthrough-find-a-memory-leak-javascript.md).  
  
  Bu konuda:  
  
  [JavaScript bellek Çözümleyicisi'ni çalıştırmak](#Run)   
  [Bellek kullanımını denetleyin](#Check)   
  [Bir bellek sızıntısı Ayır](#Isolate)   
  [Dinamik bellek kullanım özetini görüntüle](#LiveMemory)   
  [Anlık görüntü özetini görüntüle](#SnapshotSummary)   
  [Anlık görüntü ayrıntılarını görüntüle](#SnapshotDetails)   
  [Anlık görüntü farkı görüntüleme](#SnapshotDiff)   
  [Görünüm nesneleri Katla](#FoldObjects)   
  [Veri tanımlayıcıya göre filtrele](#Filter)   
  [Nesne ağacında bir nesne bulunamadı](#ShowInRootsView)   
  [Paylaşılan Görünüm nesne başvuruları](#References)   
  [Yerleşik nesnelerini Göster](#BuiltInValues)   
  [Tanılama oturumu dosyaları Kaydet](#Save)   
  [Kaynak kodu ile bellek kullanımı verileri ilişkilendirme](#JSConsoleCommands)   
  [Bellek sorunlarını tanımlamaya yönelik ipuçları](#Tips)  
  
##  <a name="Run"></a> JavaScript bellek Çözümleyicisi'ni çalıştırmak  
 Çalışan bir Windows Store app Visual Studio'da açık olduğunda bellek Çözümleyicisi'ni kullanabilirsiniz, veya çalıştıran bir bilgisayarda yüklü [!INCLUDE[win8](../includes/win8-md.md)] veya üzeri.  
  
#### <a name="to-run-the-memory-analyzer"></a>Bellek Çözümleyicisi'ni çalıştırmak için  
  
1.  Visual Studio'yu açın.  
  
2.  Uygulama içinde Visual Studio'dan çalıştırıyorsanız, **hata ayıklamayı Başlat** listesini **standart** araç, projeniz için hata ayıklama hedefi seçin: bir ya da Windows Phone öykünücüsü veya bir Windows Store uygulaması **Yerel makine**, **simülatör**, veya **uzak makine**.  
  
     Bu seçenekler hakkında daha fazla bilgi için bkz. [Visual Studio'dan uygulamaları çalıştırma](../debugger/run-store-apps-from-visual-studio.md).  
  
3.  Menü çubuğunda, **hata ayıklama**, **performans Profiler...** .  
  
     Varsayılan olarak, geçerli başlangıç projesini analiz edilir. Analiz hedefi değiştirmek istiyorsanız, seçin **değiştirme hedefi**.  
  
     ![Çözümleme hedefi Değiştir](../profiling/media/js-tools-target.png "JS_Tools_Target")  
  
     Çözümleme hedefi için aşağıdaki seçenekler kullanılabilir:  
  
    -   **Başlangıç projesi**. Geçerli başlangıç projesini analiz eder. Uzak makinede uygulama çalıştırıyorsanız, bu seçenek varsayılandır seçmeniz gerekir.  
  
    -   **Uygulamayı çalıştıran**. Çalışan uygulamalar listesinden bir Windows Store uygulaması seçmenizi sağlar. Uzak makinede uygulama çalıştırırken bu seçeneği kullanamazsınız.  
  
         Kaynak koduna erişiminiz yoksa, bilgisayarınızda çalışan uygulamalar için bellek kullanımını analiz etmek için bu seçeneği kullanın.  
  
    -   **Uygulama yüklü**. Çözümlemek istediğiniz bir yüklenen Windows Store app seçmenizi sağlar. Uzak makinede uygulama çalıştırırken bu seçeneği kullanamazsınız.  
  
         Kaynak koduna erişiminiz yoksa, bilgisayarınızda yüklü uygulamalar bellek kullanımını analiz etmek için bu seçeneği kullanın. Yalnızca kendi uygulama geliştirme dışında herhangi bir uygulama bellek kullanımını analiz etmek istediğinizde bu seçeneği de yararlı olabilir.  
  
4.  Gelen **kullanılabilir Araçları**seçin **JavaScript belleği** onay kutusunu işaretleyin ve ardından **Başlat**.  
  
5.  Bellek Çözümleyicisi'ni başlattığınızda, Visual Studio ETW Collector.exe çalıştırmak için izninizi bir kullanıcı hesabı denetimi penceresiyle isteyebilir. Seçin **Evet**.  
  
     Uygulamayla ilgili bellek kullanım senaryolarını test etmek ve bellek grafı görüntülemek için aşağıdaki bölümlerde açıklandığı gibi etkileşim kurun.  
  
6.  Visual Studio için Alt + Sekme tuşuna basarak geçin.  
  
7.  Bellek Çözümleyicisi toplama verilerini görüntülemek için seçin **yığın anlık görüntüsü Al**. Bkz: [bir anlık görüntü özeti görüntülemek](#SnapshotSummary) bu konuda.  
  
##  <a name="Check"></a> Bellek kullanımını denetleyin  
 JavaScript bellek Çözümleyicisi'nde farklı görünümleri kullanarak bellek sızıntılarını tanımlamak deneyebilirsiniz. Uygulama bellek sızıntısına yol zaten şüpheleniyorsanız bakın [bir bellek sızıntısı yalıtmak](#Isolate) için önerilen bir iş akışı.  
  
 Bir uygulamada bellek sızıntılarını belirlemenize yardımcı olması için aşağıdaki görünümleri kullanın:  
  
-   [Dinamik bellek kullanım özetini görüntüleyin](#LiveMemory). Bellek kullanım grafiği, bellek kullanımındaki ani artışlar veya belirli eylemler sonuçları bellek kullanımını sürekli olarak artan aramak için kullanın. Yığın anlık için dinamik Bellek Kullanım Özeti görünümünü kullanın. Anlık görüntüler bir koleksiyon bellek kullanım grafiğinin altında görünür.  
  
    > [!TIP]
    >  Bir anlık görüntüsünü almak, bellek kullanımı bir ani değişiklik görürsünüz. Anlık görüntü özetleri daha doğru bir göstergesi büyüme için kullanın.  
  
-   [Bir anlık görüntü özeti görüntülemek](#SnapshotSummary). Sırasında veya sonrasında profil oluşturma oturumunu bir bellek anlık görüntüsü özet bilgileri görüntüleyebilirsiniz. Anlık görüntü ayrıntılarını ve anlık görüntü fark görünümleri bağlanmak için anlık görüntü özetleri kullanın.  
  
    > [!TIP]
    >  Genellikle, anlık görüntü fark görünümleri bellek sızıntılarını en kullanışlı bilgi sağlar.  
  
-   [Anlık görüntü ayrıntılarını görüntüleme](#SnapshotDetails). Tek bir anlık görüntü için ayrıntılı bellek kullanım verileri gösterir.  
  
-   [Anlık görüntü farkı görüntüleme](#SnapshotDiff). Anlık görüntü arasındaki fark değerlerini gösterir. Bu görünümler, nesnenin farklarını boyutu ve nesne sayısını gösterir.  
  
##  <a name="Isolate"></a> Bir bellek sızıntısı Ayır  
 JavaScript bellek Çözümleyicisi daha etkili bir şekilde kullanmanıza yardımcı olabilecek bir iş akışı adımları sağlar. Aşağıdaki adımları uygulamanız bir bellek sızıntısı olduğunu şüpheleniyorsanız yararlı olabilir. Çalışan bir uygulamayı bir bellek sızıntısı tanımlama işleminde size yol gösterir bir öğretici için bkz [izlenecek yol: bir bellek sızıntısını bulma (JavaScript)](../profiling/walkthrough-find-a-memory-leak-javascript.md).  
  
1. Uygulamanızı Visual Studio'da açın.  
  
2. JavaScript bellek Çözümleyicisi'ni çalıştırın. Daha fazla bilgi için bkz. [JavaScript bellek Çözümleyicisi'ni çalıştırmak](#Run).  
  
3. Uygulamanızı test etmek istediğiniz senaryoyu çalıştırın. Örneğin, senaryo belirli bir sayfa yüklendiğinde veya uygulama başlatıldığında büyük bir DOM Mutasyon gerektirebilir.  
  
4. Senaryo 1-4 birkaç kez yineleyin.  
  
   > [!TIP]
   >  Birkaç kez test senaryosu tekrarlayarak başlatma iş koşullarda filtrelenebilir olmamasını sağlamaya yardımcı olabilir.  
  
5. Visual Studio (Alt + Sekme tuşuna basın) geçin.  
  
6. Seçerek temel yığın anlık görüntüsünü alma **yığın anlık görüntüsü Al**.  
  
    Aşağıdaki çizimde, bir temel anlık görüntü örneği gösterilmektedir.  
  
    ![Temel anlık görüntü](../profiling/media/js-mem-leak-workflow-baseline.png "JS_Mem_Leak_Workflow_Baseline")  
  
   > [!TIP]
   >  Anlık görüntü zamanlama üzerinde daha kesin denetim için kullandığınız [kaynak kodu bellek kullanım verileri ile ilişkilendirmek](#JSConsoleCommands) kodunuzda komutu.  
  
7. Uygulamanıza geçin ve (yineleme yalnızca bir kez) Test senaryosu yineleyin.  
  
8. Visual Studio'ya geçiş yapın ve ikinci bir anlık görüntüsünü alın.  
  
9. Uygulamanıza geçin ve (yineleme yalnızca bir kez) Test senaryosu yineleyin.  
  
10. Visual Studio'ya geçiş yapın ve üçüncü bir anlık görüntüsünü alın.  
  
     Aşağıdaki resimde, ikinci ve üçüncü bir anlık görüntü örneği gösterilmektedir.  
  
     ![İkinci ve üçüncü anlık görüntü](../profiling/media/js-mem-leak-workflow.png "JS_Mem_Leak_Workflow")  
  
     Bu iş akışında bir taban çizgisi, ikinci ve üçüncü anlık görüntü yararlanarak daha kolay bellek sızıntılarını ile ilişkili olmayan değişiklikleri filtreleyebilirsiniz. Örneğin, üstbilgiler ve altbilgiler bazı değişiklikler, bellek kullanımı oluşturur ancak bellek sızıntılarını ilgisiz olabilir bir sayfasında güncelleştirme gibi beklenen değişiklikleri olabilir.  
  
11. Üçüncü anlık görüntüden bir bağlantısını fark görünümlerden birini seçin:  
  
    - Fark yığın boyutu (sol bağlantı yığın boyutu altında). Bağlantı metni, önceki anlık görüntüye yığın boyutu ve yığın boyutu geçerli anlık görüntü arasındaki farkı gösterir.  
  
    - Fark nesne sayısı (sağ bağlantı altındaki nesne sayısı). Bağlantı metni iki değer gösterilir (örneğin, +1858 /-1765): ilk değeri önceki anlık görüntüye bu yana eklenen yeni nesneler sayısıdır ve ikinci değer nesnelerin önceki anlık görüntüye beri kaldırılan sayısıdır.  
  
      Bu bağlantılar, türleri yığında tutulan boyut veya bağlı olarak hangi bağlantı açtığınız nesne sayısı, sıralı bir fark anlık görüntü Ayrıntıları görünümünü açın.  
  
12. Aşağıdakilerden birini seçin **kapsam** filtre bellek kullanım sorunlarını belirlemenize yardımcı olması için seçenekleri:  
  
    -   **Kalan nesneler anlık görüntü # 2'den**.  
  
    -   **Anlık görüntü #2-#3 arasında eklenen nesneler**  
  
    > [!TIP]
    >  Bellek sızıntılarını araştırmak için önceki anlık görüntüden kalan nesneler filtrelenmiş görünümünü kullanın. Örneğin, farklı nesne sayısı +205 ise /-195, bu görünüm kalan 10 nesneler gösterilir ve bu bellek sızıntıları için olası adaylar değildir.  
  
     Anlık görüntü # 2'den kalan nesneler değişiklik bir görünümünü aşağıda gösterilmiştir.  
  
     ![Anlık görüntü türlerini gösteren fark görünümü](../profiling/media/js-mem-snapshot-diff.png "JS_Mem_Snapshot_Diff")  
  
     Önceki çizimde, iki önceki anlık görüntüden kalan nesneler olduğunu görüyoruz. Bu belirli uygulamanız için beklenen bir davranış olup olmadığını araştırın. Aksi durumda, bir bellek sızıntısı olduğunu gösterebilir.  
  
13. Fark görünümlerinde nesneler burada bunları atık olarak toplanmış olmasını önleyen, bir genel nesne köklü olmayan görmek için bir nesne için kısayol menüsünü açın ve ardından **kök görünümünde göster**. Tek bir nesne (veya bazı nesneler) tarafından başvurulduğu için çok sayıda nesne bellekte tutulur küresel nesneye kökü.  
  
14. Kalan nesneler görünümü içinde çok fazla nesne varsa, daha fazla bellek sızıntısı ortaya çıktığını dönem yalıtmak ve ardından üç anlık görüntüleri yeniden girme deneyin. Daha fazla bellek sızıntısı yalıtmak için kullanın [kaynak kodu ile bellek kullanımı verileri ilişkilendirmek](#JSConsoleCommands), [kaynak kodu ile bellek kullanımı verileri ilişkilendirmek](#JSConsoleCommands)ve diğer bellek kullanım verilerini bellek Çözümleyicisi'nde kullanılabilir.  
  
##  <a name="LiveMemory"></a> Dinamik bellek kullanım özetini görüntüle  
 Dinamik bellek kullanımı Özet görünümü, çalışmakta olan uygulamayla ve tüm anlık görüntü Özet kutucuğunu koleksiyonu için bir bellek kullanımı grafiği sağlar. Bu görünümde, Özet bilgileri analiz etme ve diğer görünümlerle gezinme anlık görüntü alma gibi temel görevleri gerçekleştirebilirsiniz. Veri toplamayı durdurduğunuzda, bellek grafikte kaybolduktan ve yalnızca gördüğünüz [bir anlık görüntü özeti görüntülemek](#SnapshotSummary) görünümü.  
  
 Bellek grafik özel bayt sayısı, yerel bellek ve JavaScript yığın içeren uygulamanın işlem belleğini canlı bir görünümünü gösterir. Bellek grafik işlem bellek kaydırılabilir bir görünümüdür. İşte bu şekilde görünür:  
  
 ![JavaScript bellek Çözümleyicisi bellek grafikte](../profiling/media/js-mem-memory-graph.png "JS_Mem_Memory_Graph")  
  
 Uygulama kodunuz için eklediğiniz kullanıcı işaretlerini (bkz [kaynak kodu ile bellek kullanımı verileri ilişkilendirmek](#JSConsoleCommands)), ters bir üçgen kodun o bölümünü ulaşıldığında belirtmek için bellek kullanımı grafiğinde görünür.  
  
 Bazı bellek grafikte gösterilen bellek JavaScript çalışma zamanı tarafından ayrılır. Uygulamanızda bu bellek kullanımını kontrol edemezsiniz. Grafikte gösterilen bellek kullanımı, ilk anlık ne zaman sağlar ve her ek anlık görüntü için en düşük düzeyde artırır.  
  
##  <a name="SnapshotSummary"></a> Anlık görüntü özetini görüntüle  
 Uygulamanızın bellek kullanımını geçerli durumu anlık tercih **yığın anlık görüntüsü Al** bellek grafiğinden. Her iki dinamik bellek kullanımı özeti (uygulama çalışırken) görüntülenen bir anlık görüntü Özet kutucuğu ve anlık görüntü özeti (app durdurulduğunda), JavaScript yığın ve daha ayrıntılı bilgi için bağlantılar hakkında bilgi sağlar. İki veya daha fazla anlık görüntüsünü kullanıyorsanız, bir anlık görüntü verilerini, önceki anlık görüntüyle karşılaştırarak ek bilgi sağlar.  
  
> [!NOTE]
>  JavaScript bellek Çözümleyicisi her anlık görüntü önce bir çöp toplama zorlar. Bu, çalıştırmaları arasında daha tutarlı sonuçlar alınması yardımcı olur.  
  
 Burada, birden çok anlık görüntülerini çekerken anlık görüntü özetinin bir örnek verilmiştir.  
  
 ![Anlık görüntü özeti](../profiling/media/js-mem-snapshot-summary.png "JS_Mem_Snapshot_Summary")  
  
 Anlık görüntü Özet şunları içerir:  
  
-   Anlık görüntü başlık ve zaman damgası.  
  
-   Olası sorunları sayısı (mavi Bilgi simgesi ile işaretlenmiştir). Bu sayı varsa, olası bellek sorunlarını için DOM'a ekli olmayan düğümleri gibi tanımlar Türler görünümü olası sorunları vurgulamak için sorun türü tarafından sıralanan anlık görüntü sayısı bağlar. Bir araç ipucu, sorunun açıklamasını gösterir.  
  
-   Yığın boyutu. Bu sayı, DOM öğeleri ve JavaScript çalışma zamanı altyapısı için JavaScript yığınını ekler nesneleri içerir. Türler görünümü anlık görüntünün yığın boyutu bağlar.  
  
-   Fark yığın boyutu. Bu değer, geçerli anlık görüntü öbek boyutunu ve önceki anlık görüntüye yığın boyutu arasındaki farkı gösterir. Bellek azaltma varsa değeri yukarı ok bellek artış olduğunda kırmızı veya yeşil bir ok tuşunu takip eder. Yığın boyutu anlık görüntüler arasında değişmediğinden, metin göreceğiniz **değişiklik** yerine bir sayı. İlk anlık görüntü için metni görürsünüz **temel**. Anlık görüntü farkı türleri görünümünü fark yığın boyutu bağlantılar  
  
-   Nesne sayısı. Bu sayaç yalnızca uygulama ve JavaScript çalışma zamanı tarafından oluşturulan yerleşik nesneleri filtreler oluşturulan nesneleri gösterir. Anlık görüntü ayrıntılarını türleri görünümünü nesne sayısı bağlar.  
  
-   Fark nesne sayısı. Bu iki değer gösterilir: ilk değeri önceki anlık görüntüye beri; eklenen yeni nesneler sayısıdır. ve ikinci değer nesnelerin önceki anlık görüntüye beri kaldırılan sayısıdır. Örneğin, çizim 1,859 nesneleri eklendi ve anlık görüntü # 1'den beri 1,733 nesneleri kaldırıldı gösterir. Bunu indirildi, bu bilgileri kırmızı bir ok toplam nesne sayısı arttığında ise veya yeşil bir ok tuşunu takip eder. Nesne sayısı değişmediğinden, metin göreceğiniz **değişiklik** yerine bir sayı. İlk anlık görüntü için metni görürsünüz **temel**. Anlık görüntü farkı türleri görünümünü fark nesne sayısı bağlantılar  
  
-   Anlık görüntünün alınma zamanını ekranında ekran görüntüsü.  
  
##  <a name="SnapshotDetails"></a> Anlık görüntü ayrıntılarını görüntüle  
 Anlık görüntü ayrıntılarını görünümlerde her anlık görüntü için bellek kullanımı hakkında ayrıntılı bilgileri görüntüleyebilirsiniz.  
  
 Anlık görüntü Özet görünümünden anlık görüntü ayrıntılarını görmek için bir bağlantıyı seçin. Örneğin, yığın boyutu bağlantı türleri görünümü ayrıntıları varsayılan olarak açık anlık görüntü açar.  
  
 Bu örnekte türler görünümü tutulan boyuta göre sıralayarak bellek kullanım verileri ile bir anlık görüntü ayrıntılı olarak gösterilmiştir.  
  
 ![Anlık görüntü ayrıntılarını görüntüleyin, olası sorunları gösteren](../profiling/media/js-mem-snapshot-details.png "JS_Mem_Snapshot_Details")  
  
 Anlık görüntü Ayrıntıları görünümünde, araç çubuğundan bir seçenek belirleyerek tür, kök veya DOMINATOR bellek kullanım verileri gözden geçirebilirsiniz:  
  
- **Türleri**. Nesne türüne göre gruplandırılmış yığındaki nesneleri örnek sayısı ve toplam boyutunu gösterir. Varsayılan olarak, bu örnek sayısına göre sıralanır.  
  
  > [!TIP]
  >  Genellikle, nesne yığını üzerindeki fark görünümlerinde türlerinin en kullanışlı bir bellek sızıntısı tanımlamaya yönelik görünümleridir; Bu görünüm sağlayan bir **kapsam** sol nesneler üzerinde belirlemenize yardımcı olması için filtre.  
  
- **Kökler**. Alt başvurular aracılığıyla kök nesnelerden nesnelerin hiyerarşik bir görünümü gösterir. Varsayılan olarak, alt düğümler ile büyük en üstünde tutulan boyut sütuna göre sıralanır.  
  
- **Önceller**. Özel diğer nesnelerin referansları sahip yığındaki nesnelerin bir listesini gösterir. Önceller tutulan boyuta göre sıralanır.  
  
  > [!TIP]
  >  Bir DOMINATOR bellekten kaldırdığınızda, nesneyi tutuyor tüm belleği geri kazanın. Tam nesne başvuru zinciri araştırabilirsiniz çünkü birkaç uygulama için tutulan bellek boyutları açıklamak Önceller görünümü yardımcı olabilir.  
  
  Üç görünümün tümü benzer değer türleri göster:  
  
- **Tanımlayıcıları**. En iyi nesneyi tanımlayan ad. Örneğin, bir kullanılıyorsa, HTML öğeleri için kimliği öznitelik değeri, anlık görüntü ayrıntılarını gösterir.  
  
- **Tür**. Nesne türü (örneğin, HTML bağlantı öğesine veya div öğesi).  
  
- **Boyutu**. Nesne boyutu, başvurulan tüm nesnelerin boyutunu içermez.  
  
- **Tutulan boyut**. Ayrıca nesne boyutu başka bir üst öğeye sahip tüm alt öğe nesnelerinin boyutu. Pratik amacıyla, bu nesne silerseniz belirtilen miktarda bellek geri kazanmak için nesne tarafından tutulan bellek miktarıdır.  
  
- **Sayısı**. Nesne örneği sayısı. Bu değer yalnızca türleri Görünümü'nde görünür.  
  
##  <a name="SnapshotDiff"></a> Anlık görüntü farkı görüntüleme  
 JavaScript bellek Çözümleyicisi'nde bir anlık görüntüsüne karşı anlık görüntü fark görünümlerinde önceki anlık görüntüye karşılaştırabilirsiniz.  
  
 Anlık görüntü Özet görünümünde iki veya daha fazla anlık görüntü kazandıktan sonra fark yığın boyutu veya fark nesne sayısı bağlantıları seçerek fark anlık görüntü ayrıntılarını görüntüleyebilirsiniz.  
  
 Fark bilgisi türleri, kök ve önceller hakkında görüntüleyebilirsiniz. Anlık görüntü diff iki anlık görüntü arasındaki yığına eklenen nesneleri gibi bilgileri gösterir.  
  
 Bu resimde bir anlık görüntü farkı türleri görüntüle  
  
 ![Anlık görüntü türlerini gösteren fark görünümü](../profiling/media/js-mem-snapshot-diff.png "JS_Mem_Snapshot_Diff")  
  
 Anlık görüntü fark penceresinde Önceller, türleri ve kökleri görünümleri aynıdır [anlık görüntü ayrıntılarını görüntüleme](#SnapshotDetails) penceresi. Anlık görüntü diff anlık görüntü ayrıntılarla bu ek değerler olarak aynı bilgileri gösterir:  
  
- **Boyut farkı**. Boyutunu dahil değil önceki anlık görüntünün boyutuna ve nesnenin geçerli anlık görüntü boyutu arasındaki fark nesnelerine başvuru.  
  
- **Tutulan boyut farkı**. Önceki anlık görüntüdeki geçerli anlık görüntü nesnesinin tutulan boyut tutulan boyutu arasındaki fark. Tutulan boyut nesne boyutu artı boyutu, başka bir üst öğeye sahip tüm alt nesneleri içerir. Pratik amacıyla tutulan boyut nesnesi silerseniz belirtilen miktarda bellek geri kazanmak için nesne tarafından tutulan bellek miktarıdır.  
  
  Anlık görüntü arasındaki fark bilgilerini filtrelemek için aşağıdakilerden birini seçin: **kapsam** fark görünümleri üstündeki filtreleri.  
  
- **Kalan nesneler gelen anlık görüntü sayısı\<numarası >**. Bu filtre yığına eklenen ve temel anlık görüntü ve önceki anlık görüntüye kıyasla yığın kaldırılır nesneler arasındaki farkı gösterir. Anlık görüntü özeti +205 gösterir. Örneğin, /-195 nesne sayısı bu filtre gösterir, on nesneleri eklendi ancak kaldırılmaz.  
  
  > [!TIP]
  >  Bu filtrede en yararlı bilgiler göstermek için açıklanan adımları izleyin. [bir bellek sızıntısı yalıtmak](#Isolate).  
  
- **Nesneler arasında eklenen anlık görüntü sayısı\<numarası > ve #\<numarası >**. Bu filtre, önceki anlık görüntüden yığına eklenen tüm nesneleri gösterir.  
  
- **Anlık görüntüsündeki tüm nesneler #\<numarası >**. Bu filtre ayarı herhangi bir nesne yığını üzerindeki filtre değil.  
  
  Geçerli eşleşmeyen nesne başvuruları göstermek için **kapsam** filtre, select **eşleşmeyen başvuruları göster** ayarlar listesinde ![ayarları bırakma&#45;bellek Çözümleyicisi listede aşağı ](../profiling/media/js-mem-settings.png "JS_Mem_Settings") bölmesinde sağ üst köşesindeki. Bu ayarı etkinleştirirseniz, eşleşmeyen başvuruları gri metinle görüntülenir.  
  
> [!TIP]
>  Adımları izlemenizi öneririz [bir bellek sızıntısı yalıtmak](#Isolate) ve kalan nesneler **kapsam** bellek sızıntısına yol açan nesneleri tanımlamaya yardımcı olmak için filtre uygulayın.  
  
##  <a name="FoldObjects"></a> Görünüm nesneleri Katla  
 Türleri ve Önceller görünümlerde mi (Bu, varsayılan görünüm Önceller sekmesinde) kullanıcıların önceller içine Katlanmış nesneleri görüntülemek seçebilirsiniz. Bu görünümü seçildiğinde yalnızca önceller nesnelerin üst düzey görünümünde gösterilir. (Genel olmayan nesnelerin alt öğeleri olan nesneler, üst düzey görünümde gizlenir.) Bazı uygulamalar için bu verilerdeki gürültü azaltarak, hangi nesnelerin bir bellek sızıntısı neden olan açıklık getirebilirsiniz.  
  
 Nesnelerin görünümünü DOMINATOR tarafından geçiş yapmak için **DOMINATOR göre nesneleri Katla** düğmesi. ![Kendi önceller nesneleri Katlama](../profiling/media/js-mem-fold-objects.png "JS_Mem_Fold_Objects")  
  
 Önceller hakkında daha fazla bilgi için bkz. [anlık görüntü ayrıntılarını görüntüleme](#SnapshotDetails).  
  
##  <a name="Filter"></a> Veri tanımlayıcıya göre filtrele  
 Önceller ve türleri görünümlerde belirli tanımlayıcılar için arama yaparak veri çıkışı filtreleyebilirsiniz. Tanımlayıcı için aranacak adını yazmanız yeterlidir **tanımlayıcı filtresi** metin kutusunda sağ üst köşedeki. Yazmaya başladığınızda, yazılan karakter içermeyen tanımlayıcıları filtrelenir.  
  
 Her görünüm kendi filtresini bulunduğundan, filtrenin başka bir görünüme geçiş yaptığınızda korunmaz.  
  
##  <a name="ShowInRootsView"></a> Nesne ağacında bir nesne bulunamadı  
 Belirli bir nesnesi için ilişki türleri ve Önceller görünümlerde görebilirsiniz `Global` nesne. Nesneleri kökü için `Global` nesne atık olarak toplanmış olmayacak. Aracılığıyla aramaya gerek kalmadan bilinen bir nesne kök görünümünde kolayca bulabilirsiniz `Global` nesne ağacının. Bunu yapmak için Önceller bir nesne için kısayol menüsünü açın veya Görünüm yazın ve ardından **kök görünümünde göster**.  
  
##  <a name="References"></a> Paylaşılan Görünüm nesne başvuruları  
 Türleri ve Önceller görünümlerinde alt bölmesinde paylaşılan başvuruları görüntüleyen bir nesne başvuru listesini içerir. Üst bölmede bir nesneyi seçtiğinizde nesnenin başvuru listesini o nesneyi işaret eden tüm nesneleri görüntüler.  
  
> [!NOTE]
>  Döngüsel başvurular bir yıldız işareti (*) ve bilgi araç ipucu ile gösterilir ve genişletilemez. Aksi takdirde, bunlar başvuru ağacı walking ve bellek koruma nesneleri tanımlayan engeller.  
  
 Eşdeğer nesneleri tanımlamak Ek Yardım isterseniz, seçin **görüntülemek nesne kimlikleri** ayarlar listesinde ![ayarları bırakma&#45;bellek Çözümleyicisi listede aşağı](../profiling/media/js-mem-settings.png "JS_Mem_Settings ") üst bölmede sağ üst köşesindeki. Bu seçenek nesne kimlikleri nesne adları yanındaki görüntüler **tanımlayıcıları** listesi (tüm görünümlerde, yalnızca nesne başvuru listesini kimlikleri gösterilir). Aynı Kimliğe sahip paylaşılan başvuruları nesnelerdir.  
  
 Aşağıdaki çizimde gösterilen kimliklerle seçili öğe için nesne başvuru listesini gösterir.  
  
 ![Nesne başvuruları görüntülenen kimlikleri](../profiling/media/js-mem-shared-refs.png "JS_Mem_Shared_Refs")  
  
##  <a name="BuiltInValues"></a> Yerleşik nesnelerini Göster  
 Varsayılan olarak, uygulamanızı oluşturduğunuz nesneleri Önceller ve türleri görünümlerini göster. Bu filtre gereksiz bilgileri inceleyin ve uygulama ile ilgili sorunları yalıtmak yardımcı olur. Ancak, bazen uygulamanız için JavaScript çalışma zamanının oluşturduğu tüm nesneleri görüntülemek için yararlı olabilir.  
  
 Bu nesneleri görüntülemeyi tercih **yerleşik olanları göster** ayarlar listesinde ![ayarları bırakma&#45;bellek Çözümleyicisi listede aşağı](../profiling/media/js-mem-settings.png "JS_Mem_Settings") üst sağ Köşe bölmesi.  
  
##  <a name="Save"></a> Tanılama oturumu dosyaları Kaydet  
 Tanılama anlık görüntü özetler ve bunların ilişkili Ayrıntılar görünümleri .diagsession dosyaları olarak kaydedilir. **Çözüm Gezgini** tanılama oturumları klasöründe önceki tanılama oturumları görüntüler. İçinde **Çözüm Gezgini**, önceki oturum açma veya kaldırabilir veya dosyalarını yeniden adlandırın.  
  
##  <a name="JSConsoleCommands"></a> Kaynak kodu ile bellek kullanımı verileri ilişkilendirme  
 Bir bellek sorunu olan kod bölümünün yalıtmaya yardımcı olması için aşağıdaki yöntemleri kullanın:  
  
- Sınıf adları ve kimlikler için ayrıntıları ve değişiklik görünümleri DOM öğeleri arayın.  
  
- Dize değerleri ayrıntıları ve kaynak kodu ile ilişkilendirilmiş olabilir fark görünümleri arayın.  
  
- Kullanım [nesne ağacında bir nesneyi bulmak](#ShowInRootsView) nesne ağacın komutu. Bu, ilişkili kaynak kodunu tanımlamak için yardımcı.  
  
- Bellek Çözümleyicisi komutlar kaynak kodunuza ekleyin.  
  
  Kaynak kodunuzu aşağıdaki komutları kullanabilirsiniz:  
  
- `console.takeHeapSnapshot` JavaScript bellek Çözümleyicisi'nde görüntülenen yığın anlık görüntüsünü alır. Bu komut biridir [JavaScript Konsolu komutları](../debugger/javascript-console-commands.md).  
  
- `performance.mark` Uygulama çalışırken, Özet görünümü bellek grafik zaman çizelgesinde görüntülenen bir kullanıcı işareti (ters üçgeni) ayarlar. Bu komut, olay açıklayan ve bellek grafikteki bir araç ipucu olarak görünür bir dize bağımsız değişkeni alır. Bu açıklama 100 karakterden uzun olmamalıdır.  
  
> [!TIP]
>  Kullanım `console.takeHeapSnapshot` bellek kullanım senaryoları yinelenen analiz hızlandırmak için.  
  
 Uygulamanıza bunları eklemek ve uygulama dışında JavaScript bellek Çözümleyicisi'ni çalıştırın, bu komutları bir özel durum. Bununla birlikte, komutları kullanmadan önce mevcut olup olmadığını sınayabilirsiniz. (Komutlar erken oturumu başlangıç aşamasında yok.) Güvenli bir şekilde çağırıp çağırmayacağınızı denetlenecek `takeHeapSnapshot`, bu kodu kullanın:  
  
```javascript  
if (console && console.takeHeapSnapshot) {  
    console.takeHeapSnapshot();  
}  
```  
  
 Güvenli bir şekilde çağırıp çağırmayacağınızı denetlenecek `performance.mark`, bu kodu kullanın:  
  
```javascript  
if (performance && performance.mark) {  
    performance.mark("message_string");  
}  
  
```  
  
 İşte birkaç kullanıcı işaretlerini ve araç ipucu, seçili kullanıcı işareti bir bellek grafiği `performance.mark` dize bağımsız değişkeni "oluşturulan verileri için" ayarlayın:  
  
 ![Bir profili işareti kullanarak](../profiling/media/js-mem-performance-marks.png "JS_Mem_Performance_Marks")  
  
##  <a name="Tips"></a> Bellek sorunlarını tanımlamaya yönelik ipuçları  
  
-   Açıklanan iş akışı izleyin [bir bellek sızıntısı yalıtmak](#Isolate) ve **kalan nesneler gelen anlık görüntü sayısı\<numarası >** bellek sızıntıları için olası adaylar tanımlamak üzere bir fark görünümünde filtre.  
  
-   Kullanım [nesne ağacında bir nesneyi bulmak](#ShowInRootsView) nesneyi bellek hiyerarşi içinde nereye başvurulan görmek için. Atık olarak toplanmış yüklenmesini önleyen genel nesne için bir nesnenin nasıl kökü kökleri görüntüler.  
  
-   Bir bellek sorunu nedenini belirlemek zor olduğunda, (örneğin, Önceller ve türleri) çeşitli görünümler özellikle bir nesne (veya bazı nesneler) belirlemenize yardımcı olması için commonalities için aramak için kullanın görünen diğer nesnelerin pek başvuruları içerebilir Görünüm.  
  
-   Kullanıcı için yaygın bir nedeni, bellek sorunları olan yeni bir sayfada, gittikten sonra bellekte yanlışlıkla korunur nesneleri arayın. Örneğin:  
  
    -   Yanlış kullanımından dolayı [URL'si. CreateObjectUrl](http://msdn.microsoft.com/library/windows/apps/hh453196.aspx) işlevi bu soruna neden olabilir.  
  
    -   Bazı nesneler sağlayabilir bir `dispose` yöntemi ve öneriler için kullanın. Örneğin, çağırmalıdır `dispose` üzerinde bir [WinJS.Binding.List](http://msdn.microsoft.com/library/windows/apps/Hh700774.aspx) listenin çağırırsanız `createFiltered` yöntemi ve ardından bir sayfadan ayrılmak gidin.  
  
    -   Bir veya daha fazla olay dinleyicileri kaldırmanız gerekebilir. Daha fazla bilgi için bkz. [görünümü DOM olayı dinleyicilerini](../debugger/view-dom-event-listeners.md).  
  
-   İkinci bölümü izleyin [bu videoyu](http://channel9.msdn.com/Events/Build/2013/3-316) JavaScript bellek Çözümleyicisi hakkında derleme 2013 konferansına ait.  
  
-   Okuma [Windows Store apps bellekte yönetme](http://msdn.microsoft.com/magazine/jj651575.aspx).  
  
-   Kod sorunları yalıtmak için geçici olarak değiştirmeyi düşünün. Örneğin, aşağıdakileri yapabilirsiniz:  
  
    -   Bellek Çözümleyicisi için komutları kullanın `console.takeSnapshot` ve `performance.mark`. (Bkz [kaynak kodu ile bellek kullanımı verileri ilişkilendirmek](#JSConsoleCommands).)  
  
         Yığın anlık görüntüsü el ile yararlanarak ayıramazsınız sorunlarını gidermeye yardımcı olmak için bu komutları kullanabilirsiniz.  
  
    -   Bir test nesnesi oluşturma ve JavaScript bellek Çözümleyicisi görünümlerde türler görünümü gibi izleme. Örneğin, belirli bir nesne veya öğenin atık olarak toplanmış olup olmadığını görmek için başka bir nesne için çok büyük bir nesne ekleyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Bellek sızıntısını bulma (JavaScript)](../profiling/walkthrough-find-a-memory-leak-javascript.md)



