---
title: Çağrı yığınının görsel haritasını oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
ms.assetid: d6a72e5e-f88d-46fc-94a3-1789d34805ef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9fe3471f7165cf48f62dee3ca657e78fbfafd273
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49837405"
---
# <a name="create-a-visual-map-of-the-call-stack-while-debugging-in-visual-studio-enterprise"></a>Visual Studio Enterprise'da hata ayıklama sırasında çağrı yığınının görsel haritasını oluşturma
Hata ayıklarken çağrı yığınını görsel olarak izlemek için bir kod Haritası oluşturun. Hataları bulmaya odaklanabilmeniz amacıyla kodun ne yaptığını izlemek için harita üzerine not alabilirsiniz.

 Şunları yapmanız gerekir:

-   [Visual Studio Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

-   Visual C#, Visual Basic, C++, JavaScript veya X ++ gibi hatalarını ayıklayabileceğiniz kod

Bir kod Haritası hızlı bir bakış şu şekildedir:

 ![Kod haritalarına çağrı yığınları ile hata ayıklama](../debugger/media/debuggermap_overview.png "DebuggerMap_Overview")

 Bkz.

- [Video: (kanal 9) kod Haritası hata ayıklayıcı Tümleştirmesi ile görsel olarak hata ayıklama](http://go.microsoft.com/fwlink/?LinkId=293418)

- [Çağrı yığınını eşleme](#MapStack)

- [Kodla ilgili notlar alın](#MakeNotes)

- [Sonraki çağrı yığını ile eşlemeyi güncelleyin](#UpdateMap)

- [Eşlemeye ilgili kodu ekleyin](#AddRelatedCode)

- [Eşlemeyi kullanarak hataları bulun](#FindBugs)

- [SORU- CEVAP](#QA)

  Komutlar ve kod haritaları ile çalışırken kullanabileceğiniz eylemler için bilgi [göz atma ve yeniden düzenleme kod eşlemeleri](../modeling/browse-and-rearrange-code-maps.md).

##  <a name="MapStack"></a> Çağrı yığınını eşleme

1.  Hata ayıklama başlatılamıyor. (Klavye: **F5**)

2.  Uygulamanız Kesme moduna girdiğinde ya da bir işleve sonra seçin **kod Haritası**. (Klavye: **Ctrl** + **Shift** + **`**)

     ![Çağrı yığınını eşleme başlatmak için kod Haritası seçin](../debugger/media/debuggermap_choosecodemap.png "DebuggerMap_ChooseCodeMap")

     Geçerli çağrı yığını yeni bir kod haritası üzerinde turuncu renkte görüntülenir:

     ![Bkz: kod haritasında çağrı yığınını](../debugger/media/debuggermap_seeundocallstack.png "DebuggerMap_SeeUndoCallStack")

     Hata ayıklamaya devam et sırasında haritada otomatik olarak güncelleştirecektir. Bkz: [harita sonraki çağrı yığınıyla Güncelleştir](#UpdateMap).

##  <a name="MakeNotes"></a> Kodla ilgili notlar alın
 Kodda neler olduğunu izlemek için açıklamalar ekleyin. Bir açıklamaya yeni bir satır eklemek için basın **üst karakter + Return**.

 ![Kod haritasında çağrı yığını için açıklama ekleme](../debugger/media/debuggermap_addcomment.png "DebuggerMap_AddComment")

##  <a name="UpdateMap"></a> Sonraki çağrı yığını ile eşlemeyi güncelleyin
 Uygulamanızı sonraki kesme noktasına kadar çalıştırın veya bir işleve adımlayın. Eşleme yeni bir çağrı yığını ekler.

 ![Sonraki çağrı yığını ile güncelleştirme kod Haritası](../debugger/media/debuggermap_addclearcallstack.png "DebuggerMap_AddClearCallStack")

##  <a name="AddRelatedCode"></a> Eşlemeye ilgili kodu ekleyin
 Artık bir harita - ne sonraki kendinizi? Görselle çalışıyorsanız C# veya Visual Basic, alanlar, özellikler ve kodda neler olduğunu izlemek için diğer yöntemler gibi öğeleri ekleyin.

 Kod tanımını görmek için bir yöntemi çift tıklayın ya da yöntem için kısayol menüsünü kullanın. (Klavye: tuşuna basın ve harita yöntemi seçin **F12**)

 ![Kod haritasında bir yöntem için kod tanımı Git](../debugger/media/debuggermap_gotocodedefinition.png "DebuggerMap_GoToCodeDefinition")

 Haritada izlemek istediğiniz öğeleri ekleyin.

 ![Çağrı yığınını kod Haritası üzerinde bir yöntemi alanları gösterin](../debugger/media/debuggermap_showfields.png "DebuggerMap_ShowFields")

> [!NOTE]
>  Varsayılan olarak, öğeleri haritaya ekleme sınıfı, ad alanı ve derlemeye gibi üst düğümleri gruplandırma ekler. Bu kullanışlı olmakla birlikte, eşleme özelliğini kullanarak bu devre dışı bırakarak basit tutabildiğiniz **üst öğeleri dahil** düğmesine basarak veya harita araç çubuğunda **CTRL** öğeleri eklediğinizde.

 ![Metoda çağrı yığınını kod haritasında ilgili alanları](../debugger/media/debuggermap_showedfields.png "DebuggerMap_ShowedFields")

 Hangi yöntemlerin aynı alanları kullandığını kolayca görebilirsiniz. En son eklenen öğeler yeşil görünür.

 Daha fazla kod görmek için haritayı oluşturmaya devam edin.

 ![Bir alanı kullanan yöntemlerine bakın: çağrı yığınını kod Haritası](../debugger/media/debuggermap_findallreferences.png "DebuggerMap_FindAllReferences")

 ![Çağrı yığınını kod haritasında bir alanı kullanan yöntemleri](../debugger/media/debuggermap_foundallreferences.png "DebuggerMap_FoundAllReferences")

##  <a name="FindBugs"></a> Eşlemeyi kullanarak hataları bulun
 Kodunuzu görselleştirmeniz, hataları daha hızlı şekilde bulmanıza yardımcı olabilir. Örneğin, bir çizim programında bir hata araştırdığınızı varsayın. Bir çizgi çizip geri almayı denediğinizde, başka bir çizgi çizinceye kadar hiçbir şey olmaz.

 Kesme noktaları ayarlamak için `clear`, `undo`, ve `Repaint` yöntemleri, hata ayıklamayı başlatmak ve bunun gibi bir harita oluşturur:

 ![Başka bir çağrı yığınını kod Haritası eklemek](../debugger/media/debuggermap_addpaintobjectcallstack.png "DebuggerMap_AddPaintObjectCallStack")

 Harita çağrısında tüm kullanıcı hareketlerine dikkat edin `Repaint`, dışında `undo`. Yaramamasının nedeni `undo` hemen işe yaramaz.

 Hatayı düzeltip programı çalıştırmaya devam sonra eşleme yeni çağrısından ekler `undo` için `Repaint`:

 ![Yeni yöntemi çağrısı için çağrı yığınını kod haritasında eklemek](../debugger/media/debuggermap_addnewcallforrepaint.png "DebuggerMap_AddNewCallForRepaint")

##  <a name="QA"></a> SORU- CEVAP

- **Aramaların tümü haritada görünmez. Neden?**

   Varsayılan olarak, yalnızca kendi kodunuzu harita üzerinde görüntülenir. Harici kodu görmek için de açın **çağrı yığını** penceresi:

   ![Çağrı yığını penceresini kullanarak dış kod görüntüleme](../debugger/media/debuggermap_callstackmenu.png "DebuggerMap_CallStackMenu")

   ya da devre dışı **yalnızca benim kodumu etkinleştir** Visual Studio hata ayıklama seçeneklerinde:

   ![Seçenekler iletişim kutusunu kullanarak dış Kodu Göster](../debugger/media/debuggermap_debugoptions.png "DebuggerMap_DebugOptions")

- **Haritanın değiştirilmesi kodu etkiler mi?**

   Haritanın değiştirilmesi kodu herhangi bir şekilde etkilemez. Haritadaki herhangi bir şeyi rahatça yeniden adlandırabilir, taşıyabilir veya kaldırabilirsiniz.

- **Bu ileti ne anlama gelir: "diyagram kodu daha eski bir sürümünü temel alıyor olabilir"?**

   Kod, haritayı son güncelleştirmenizden sonra değişmiş olabilir. Örneğin, harita üzerindeki bir çağrı artık kodda bulunmayabilir. İletiyi kapatın ve haritayı yeniden güncelleştirmeden önce çözümü yeniden oluşturmayı deneyin.

- **Haritanın düzenini nasıl denetlerim?**

   Açık **Düzen** menüsünü harita araç çubuğunda:

  -   Ekran düzenini değiştirin.

  -   Eşlemeyi otomatik olarak yeniden düzenleme durdurmak için devre dışı **otomatik olarak hata ayıklama sırasında Düzen**.

  -   Öğeleri eklediğinizde, eşlemeyi olabildiğince az yeniden düzenlemek için devre dışı **artan düzen**.

- **Ben haritayı başkalarıyla paylaşabilir miyim?**

   Haritayı dışarı aktarabilir, Microsoft Outlook'unuz varsa başkalarına gönderebilir veya çözümünüze kaydedebilir, böylece Team Foundation sürüm denetimine iade edebilirsiniz.

   ![Paylaşım çağrı yığınını kod Haritası başkalarıyla](../debugger/media/debuggermap_sharewithothers.png "DebuggerMap_ShareWithOthers")

- **Eşlemeyi otomatik olarak yeni çağrı yığınları eklemesini nasıl durdururum?**

   Seçin ![düğmesi &#45; Show çağrı yığınını kod haritasında otomatik olarak](../debugger/media/debuggermap_automaticupdateicon.gif "DebuggerMap_AutomaticUpdateIcon") harita araç çubuğunda. Geçerli çağrı yığınını eşlemeye el ile eklemek için basın **Ctrl** + **Shift** + **`**.

   Eşleme, hata ayıklarken eşlemede varolan çağrı yığınlarını vurgulamaya devam edecektir.

- **Öğe simgeleri ve okları ne anlama gelir?**

   Bir öğe hakkında daha fazla bilgi almak için fare işaretçisini üzerine taşıyın ve öğenin ipucuna bakın. Ayrıca bakabilirsiniz **gösterge** her simgenin ne anlama geldiğini öğrenebilirsiniz.

   ![Çağrı yığınını kod Haritası simgeleri ne anlama gelir? ](../debugger/media/debuggermap_showlegend.png "DebuggerMap_ShowLegend")

  Bkz.

- [Çağrı yığınını eşleme](#MapStack)

- [Kodla ilgili notlar alın](#MakeNotes)

- [Sonraki çağrı yığını ile eşlemeyi güncelleyin](#UpdateMap)

- [Eşlemeye ilgili kodu ekleyin](#AddRelatedCode)

- [Eşlemeyi kullanarak hataları bulun](#FindBugs)

## <a name="see-also"></a>Ayrıca Bkz.
 [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md) [kullanmak kod eşlemeleri uygulamalarınızda hata ayıklamak için](../modeling/use-code-maps-to-debug-your-applications.md) [kod kullanarak olası sorunları bulma harita Çözümleyicileri](../modeling/find-potential-problems-using-code-map-analyzers.md) [göz atma ve yeniden düzenleme kod eşlemeleri](../modeling/browse-and-rearrange-code-maps.md)