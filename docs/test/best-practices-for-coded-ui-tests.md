---
title: Visual Studio'da kodlanmış UI testleri için en iyi yöntemler
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests, best practices
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d158d3d0fade2b44cf819cf40209a901534a18ad
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36283282"
---
# <a name="best-practices-for-coded-ui-tests"></a>Kodlanmış UI testleri için en iyi yöntemler

Bu konuda geliştirme kodlanmış UI testleri için bazı öneriler açıklanmaktadır.

## <a name="best-practices"></a>Önerilen uygulamalar

Esnek bir kodlanmış UI testi oluşturmak için aşağıdaki kılavuzları kullanın.

-   Kullanım **kodlanmış UI Test derleyicisini** mümkün olduğunda.

-   Değişiklik yapmayın *UIMap.Designer.cs* dosyasını doğrudan. Dosyayı değiştirirseniz, değişiklikleri dosyaya yazılır.

-   Testinizi kaydedilen yöntemler dizisi olarak oluşturun. Bir yöntem kayıt hakkında daha fazla bilgi için bkz: [oluşturma kodlanmış UI testleri](../test/use-ui-automation-to-test-your-code.md).

-   Kaydedilen her yöntem, tek sayfa, form veya iletişim kutusu üzerinde işlem yapmalıdır. Her yeni sayfa, form veya iletişim kutusu için yeni bir test yöntemi oluşturun.

-   Bir yöntem oluştururken anlamlı bir yöntem adı yerine varsayılan adı kullanın. Anlamlı bir ad yöntemin amacını tanımlamaya yardım eder.

-   Mümkün olduğunda, kaydedilen her yöntem 10'dan az eylemlerine sınırlayın. Modüler bu yaklaşım UI değişirse bir yöntemini değiştirmek kolaylaştırır.

-   Her onaylama kullanarak oluşturduğunuz **kodlanmış UI Test derleyicisini**, bu da otomatik olarak ekler bir onay yöntemi *UIMap.Designer.cs* dosya.

-   Kullanıcı Arabirimi (UI) değişirse, test yöntemleri veya onay yöntemlerini yeniden kaydedin veya varolan bir test yönteminin etkilenen bölümlerini yeniden kaydedin.

-   Ayrı bir oluşturma <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> her test altındaki uygulamanızı modülde dosyası. Daha fazla bilgi için bkz: [birden çok UI eşlemesi bulunan büyük uygulamaları sınama](../test/testing-a-large-application-with-multiple-ui-maps.md).

-   Kullanıcı Arabirimi denetimlerini oluşturduğunuzda test uygulamada anlamlı adlar kullanın. Anlamlı adları kullanarak otomatik olarak oluşturulan denetim adları büyük netlik ve kullanılabilirlik sağlar.

-   API ile kodlayarak onaylar oluşturuyorsanız, parçasında her onay için bir yöntem oluşturma <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfının *UIMap.cs* dosya. Onaylama işlemi yürütmek için test yönteminden bu yöntemi çağırın.

-   Doğrudan API ile kodlama yapıyorsanız, özellikleri ve yöntemleri oluşturulan sınıfların kullanmak *UIMap.Designer.cs* , olabildiğince kodunuzda dosya. Bu sınıfların çalışmanızı yapacak daha kolay ve daha güvenilir ve daha üretken olmanıza yardımcı olur.

Kodlanmış UI testleri, kullanıcı arabiriminde birçok değişiklikler otomatik olarak uyarlayın. Örneğin, bir kullanıcı Arabirimi öğesi konum veya renk değiştiyse, çoğu zaman kodlanmış UI testi yine doğru öğeyi bulur.

Testi sırasında bir arama özellikleri kümesi kullanarak UI denetimleri test çerçevesi tarafından bulunur. Arama özellikleri tarafından oluşturulan tanımları her denetim sınıfına uygulanan **kodlanmış UI Test derleyicisini** içinde *UIMap.Designer.cs* dosya. Arama özellikleri özellik adları ve denetim gibi tanımlamak için kullanılan özellik değerlerini ad-değer çiftleri içeren <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.FriendlyName%2A>, <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.Name%2A>, ve <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.ControlType%2A> denetiminin özellikleri. Arama özellikleri değişmeden varsa, kodlanmış UI testi denetimi kullanıcı Arabiriminde başarıyla bulun. Arama özellikleri değiştirilirse, kodlanmış UI testleri denetimleri ve windows kullanıcı Arabiriminde bulmak için buluşsal yöntemler uyguladığı bir akıllı eşleşme algoritması bulunur. UI değiştiğinde, bunlar bulunduğundan emin olmak için önceden tanımlanmış öğelerin arama özelliklerini değiştirmek mümkün olabilir.

## <a name="if-your-user-interface-changes"></a>Kullanıcı arabiriminiz değişirse

Kullanıcı arabirimleri sık geliştirme sırasında değiştirin. Bu değişikliklerin etkisini azaltmak için bazı yöntemler şunlardır:

-   Bu denetim başvuran kayıtlı yöntemi bulun ve kullanmanız **kodlanmış UI Test derleyicisini** bu yöntem için eylemleri yeniden kaydetmek için. Varolan eylemlerin üzerine yazma yöntemi için aynı adı kullanabilirsiniz.

-   Bir denetimin artık geçerli olmayan bir onaylama varsa:

    -   Onaylamayı içeren yöntemi silin.

    -   Bu yöntem çağrısı test yönteminden kaldırın.

    -   Yeni bir onaylama çapraz hedef düğmesini UI denetiminin üzerine sürükleyerek ekleyin, UI haritasını açın ve yeni onayı ekleyin.

Kodlanmış UI testlerini nasıl kaydedileceği hakkında daha fazla bilgi için bkz: [kodunuzu test etmek için kullanım UI Otomasyonu](../test/use-ui-automation-to-test-your-code.md).

## <a name="if-a-background-process-needs-to-complete-before-the-test-can-continue"></a>Önce test tamamlamak için bir arka plan işlemi sahipseniz geçebilirsiniz

Sonraki UI eylemiyle devam etmeden önce bir işlem sonlanana kadar beklemeniz gerekebilir. Kullanabileceğiniz bunun için <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.WaitForReadyLevel%2A> aşağıdaki örnekte olduğu gibi test, devam etmeden önce beklenecek:

```csharp
// Set the playback to wait for all threads to finish
Playback.PlaybackSettings.WaitForReadyLevel = WaitForReadyLevel.AllThreads;

// Press the submit button
this.UIMap.ClickSubmit();

// Reset the playback to wait only for the UI thread to finish
Playback.PlaybackSettings.WaitForReadyLevel = WaitForReadyLevel.UIThreadOnly;
```

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>
- <xref:Microsoft.VisualStudio.TestTools.UITesting>
- [UI otomasyonunu kullanarak kodunuzu test etme](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md)
- [Birden çok UI eşlemesi bulunan büyük uygulamaları sınama](../test/testing-a-large-application-with-multiple-ui-maps.md)
- [Kodlanmış UI testleri ve eylem kayıtları için desteklenen yapılandırmalar ve platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)