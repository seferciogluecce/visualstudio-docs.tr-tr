---
title: "Modelleri ve diyagramları diğer Visual Studio sürümlerinde okuma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: models, versions of Visual Studio
ms.assetid: 46eee279-a9e4-4742-a024-5bd2cf032b86
caps.latest.revision: "20"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: 704c69efa4e0495a1a4aa7545fa6ba100488afe9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>Diğer Visual Studio sürümlerindeki modelleri ve diyagramları okuma
Bir model oluşturmayı desteklemiyor Visual Studio sürümünde bir model açtığınızda model salt okunur modunda açılır. Bu modda diyagramları düzenini değiştirebilirsiniz ancak modeli değiştiremezsiniz.  
  
 Model oluşturma Visual Studio'nun hangi sürümleri desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="obtaining-access-to-a-model-and-diagrams"></a>Bir Model ve diyagramları erişim elde etme  
 Bir bağımlılık diyagramı okumak için ilk modelleme projesi açmak için Visual Studio'yu kullanın ve sonra diyagramında açın.  
  
 Bu nedenle, bir bağımlılık diyagramı okumak istiyorsanız, bunu oluşturulduğu modelleme projesi için erişim izni de olmalıdır. Bunu aşağıdakilerden projeden erişerek yapabilirsiniz [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)], veya proje dosyalarının bir kopyasını alma.  
  
> [!NOTE]
>  Bu kodu uygulanmaz eşlemeleri ve .NET sınıf diyagramları koddan oluşturulan. Bu diyagramları modelleme projesine bağımsız olarak görüntülenebilir.  
  
 Bir bağımlılık diyagramı okumak için en düşük gereksinim duyduğunuz dosyaları kümesini şu şekildedir:  
  
-   İki okumak, örneğin, istediğiniz diyagram için dosya diyagram **MyDiagram.classdiagram ve MyDiagram.classdiagram.layout**.  
  
    > [!NOTE]
    >  Bağımlılık diyagramları için de adlı dosyayı olmalıdır *Diyagramım***. layerdiagram.suppressions**.  
  
-   Modelleme Proje dosyası (**MyModel.modelproj**)  
  
-   Kök model dosyası (**ModelDefinition\MyModel.uml**)  
  
-   Şemada başvurulan herhangi bir paket için paket dosyaları (**ModelDefinition\MyPackage.uml**)  
  
## <a name="changes-that-you-can-make-in-read-only-mode"></a>Salt okunur modda yaptığınız değişiklikler  
 Bir model oluşturmayı desteklemiyor Visual Studio sürümünde bir model ve onun diyagramlarını açarsanız modeli değiştiremezsiniz. Diğer bir deyişle, öğeleri ve diyagramlarda veya model Gezgini'nde görüntülenen ilişkileri değiştiremezsiniz. Ancak, bazı değişiklikler diyagramları düzene yapabilirsiniz:  
  
-   Şekiller ve bağlayıcılar diyagramda yeniden düzenleyin.  
  
-   Şekilleri genişletme ve daraltma.  
  
 Bu değişiklikleri kaydedebilirsiniz. Değişikliklerinizi diğer kullanıcılar için görünür yapmak istiyorsanız, en az güncelleştirilmiş göndermelidir **.layout** dosyaları.  
  
##  <a name="RelatedTopics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Bağımlılık diyagramları: başvuru](../modeling/layer-diagrams-reference.md)|Bir katman diyagramı varolan ya da önerilen bir mimari yapısını gösterir. Kod yazıldığında otomatik olarak bir katman diyagramı karşı doğrulanabilir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulamanız için model oluşturma](../modeling/create-models-for-your-app.md)