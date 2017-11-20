---
title: "Birim testi ile birim testleri Oluştur komutu yöntemi saplamalar oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: unit testing, create unit tests
ms.assetid: 5D625021-BA96-48A5-9453-3EF6F0943466
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.openlocfilehash: 7e69218700314224f67094486cfd381ac1460995
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="create-unit-test-method-stubs-with-the-create-unit-tests-command"></a>Birim testi yöntemi saplamalar ile birim testleri Oluştur komutu oluşturun.

Visual Studio **birim testleri oluşturma** komutu birim test yöntemi saplamalar oluşturma olanağı sağlar. Bu özellik, bir test projesi, test sınıfı ve içerdiği test yöntemi saplama kolay yapılandırmasını sağlar. 

## <a name="availability-and-extensions"></a>Kullanılabilirlik ve uzantıları

**Birim testleri oluşturma** menü komutu:

* Community, Professional ve Enterprise sürümleri, Visual Studio 2015 kullanılabilir ve üzerinde desteklenir.

* .NET Framework hedefleyen yalnızca C# kod destekler.

* Olan [Genişletilebilir](#extend-framework)ve mstest'i, mstest'i V2, NUnit, xUnit biçimi testlerinde yayma destekler.

## <a name="get-started"></a>Kullanmaya başlayın

Başlamak için bir yöntem, bir tür veya bir ad alanı test, kısayol menüsünü açın ve seçmek istediğiniz proje Kod düzenleyicisinde seçin **birim testleri oluşturma**. Bu açılır **birim testleri oluşturma** iletişim burada yeni birim testleri oluşturma seçeneklerini seçilebilir.

![Create birim testleri komutu kullanma](media/createunittestcommand.png)

## <a name="setting-unit-test-traits"></a>Birim testi özellikleri ayarlama

Bu testleri çalıştırmayı planlıyorsanız, test Otomasyonu işleminin bir parçası olduğundan, başka bir test projesi (yukarıdaki iletişim ikinci seçeneği) oluşturulan test sahip düşünebilirsiniz ve nitelikler birim testi için test ayarı birimi. Bu, daha kolay eklemek veya bu belirli sınamalar sürekli tümleştirme veya sürekli dağıtım ardışık düzen parçası olarak dışlamak olanak tanır. Nitelikler aşağıda gösterildiği gibi meta veriler için birim testi doğrudan ekleyerek ayarlanır. 

![Birim testi özellikleri ayarlama](media/createunittest.png)

<a name="extend-framework"></a>
## <a name="using-third-party-unit-test-frameworks"></a>Üçüncü şahıs birim test çerçevelerini kullanarak

Visual Studio ile birim testleri için test framework kullanarak oluşturduğunuz kolayca olabilir. Yüklemek için diğer test çerçevelerini ekleyin, seçin **Araçlar | Uzantılar ve güncelleştirmeler**.
Genişletme **çevrimiçi**, **Visual Studio Galerisi**, **Araçları**ve seçin **test**. 

![Üçüncü taraf test çerçevelerini kullanarak](media/createunittestfx.png)

Test framework uzantıları Visual Studio Market'te bulunabilir kullanılabilir:

* [Test oluşturucuları için NUnit uzantısı](https://marketplace.visualstudio.com/items?itemName=NUnitDevelopers.TestGeneratorNUnitextension)
* [Test oluşturucuları için xUnit.net uzantısı](https://marketplace.visualstudio.com/items?itemName=BradWilson.xUnitnetTestExtensions)

## <a name="when-should-i-use-this-feature"></a>Bu özellik ne zaman kullanmalıyım?

Bu özelliği kullanmak birim testleri oluşturmak gereken zaman, ancak özellikle mevcut kodunuzu sınarken çok az olan veya hiç test kapsamı ve belge yok. Diğer bir deyişle, söz konusu olduğunda sınırlı veya var olmayan kodu belirtimi. Etkili bir şekilde benzer bir yaklaşım uygular [akıllı birim testleri](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/19/introducing-smart-unit-tests.aspx) kod gözlemlenen davranışını niteleyen.

Ancak, bu özellik burada Geliştirici bazı kodlar yazarak başlar ve birim uzmanlık testi bootstrap kullanan durumunuz için eşit oranda geçerlidir. Kodlama nsg'lerin, geliştirici hızla (ile uygun test sınıfı ve uygun test projesi) saplama birim test yöntemi için belirli bir kod oluşturmak isteyebilirsiniz. 

## <a name="more-information"></a>Daha fazla bilgi

Blog gönderisine bakın [birim testi "Oluşturmak ile birim testleri" yöntemi saplamalar oluşturma](https://blogs.msdn.microsoft.com/visualstudioalm/2015/03/06/creating-unit-test-method-stubs-with-create-unit-tests/).

Daha fazla birim testi blog gönderileri bulunabilir [burada](https://blogs.msdn.microsoft.com/visualstudioalm/tag/unit-testing/).