---
title: "İade takım projesi ilkeleriyle kod kalitesini arttırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code quality, using check-in policies
- team-based development, enhancing code quality
ms.assetid: 0ab72c33-148a-4a8a-a7bf-046995514c84
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5b421f5512e51d83e7f6e4edfbbe2869a1484200
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="enhancing-code-quality-with-team-project-check-in-policies"></a>Takım Projesi İade İlkeleriyle Kod Kalitesini Arttırma
Team Foundation sürüm denetimi (TFVC'yi) kullandığınızda, takım projeleriniz için iade ilkeleri oluşturabilirsiniz. zorlamak için daha iyi bir kod ve daha verimli grup geliştirme bu sağlama yöntemleri. İade ilkeleri, takım projesi düzeyinde ayarlamak ve kod iade edilmesi için izin verilmeden önce Geliştirici bilgisayarlarda zorlanan kurallardır.  
  
 Bu takım projesi iade ilkeleri belirtebilirsiniz:  
  
-   **Derlemeler**: derleme sırasında oluşturulan yapı sonları yeni iade önce düzeltilmesi gereken gerektirir.  
  
-   **Değişiklik kümesi açıklamalarını**: kullanıcıların değişiklikler iade edilirken açıklamaları sağlaması gerekir.  
  
-   **Kod çözümleme**: Kod Analizi iade önce çalıştırmanızı gerektirir.  
  
-   **İş öğeleri**: iş öğelerinin biri veya daha fazla onay-ilişkilendirilmiş olmasını gerektirir.  
  
> [!IMPORTANT]
>  İade ilkelerini kullanmak için bağlanmanız gerekir [!INCLUDE[vststfsLong](../code-quality/includes/vststfslong_md.md)].  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|Destekleyici İçerik|  
|----------|------------------------|  
|**Oluşturma ve iade ilkelerini kullanma:** takım projesi ayarlarını kullanarak iade ilkeleri oluşturma [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)].|[Kalite kapıları ayarlama ve uygulama](http://msdn.microsoft.com/Library/bdc5666e-6cf0-45b2-a0a1-133c3f61e852)|  
|**Oluşturma ve kod çözümleme iade ilkelerini kullanma:** standart kod çözümleme kurallarını kümesinden seçebilir veya özel bir grup oluşturabilirsiniz.|[Oluşturma ve kod çözümleme iade ilkelerini kullanma](../code-quality/creating-and-using-code-analysis-check-in-policies.md)|  
  
## <a name="related-tasks"></a>İlgili görevleri  
  
|Görev|Destekleyici İçerik|  
|----------|------------------------|  
|**Geliştirme ortamınızı ayarlama:** oluşturun veya kodu değiştirmeden önce uygun kaynak kod kullanarak geliştirme ve test ortamları ayarlamanız gerekir. Veritabanları ile çalışıyorsanız, ayrıca bunların çevrimdışı gösterimi erişiminiz olmalıdır.|[Geliştirme ortamları ayarlama](http://msdn.microsoft.com/en-us/7b686610-d379-4ca0-9608-73ef0e576e3a)|  
|**Kod çözümleme geliştirme işlemde kullanın:** takım üyeleri geliştirme bilgisayarlarında Kod Analizi çalıştırın. Visual Studio'da geliştiriciler yapılandırmak ve kod projeleri için kod çözümleme çalıştırır çalıştırmak, görüntülemek ve sorunları çözümlemek çalıştırır tarafından bulunan ve Uyarılar için iş öğelerini oluşturabilir.|[Uygulama kalitesini analiz etme](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)|  
|**Birim testleri oluşturma ve çalıştırma:** birim testleri, C#, Visual Basic .NET ve C++ projelerine sınıfların yöntemler mantık hataları aramak için hızlı bir şekilde geliştiriciler ve sınayıcılar verin. Birim testi bir kez oluşturulabilir ve hiçbir hata sunulan emin olmak için her kaynak kodda değiştiğinde çalıştırın.|[Kodunuza birim testi](../test/unit-test-your-code.md)|  
|**İş öğeleri ve hataları izleme:** iş öğelerini izlemek ve iş ve bilgi takım projenizin hakkında yönetmek için kullanabilirsiniz. Bir iş öğesi bir veritabanı olduğundan bu kayıt [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] atama ve iş ilerlemesini izlemek için kullanır. Farklı türlerde iş öğeleri çalışma, müşteri gereksinimleri, ürün hataları ve geliştirme görevleri gibi farklı türlerde izlemek için kullanabilirsiniz.|[İzleme çalışma ve iş akışı &#91;Yönet; yeniden yönlendirilen &#93;](http://msdn.microsoft.com/en-us/d2d8637d-0ef8-4ca3-874e-a04713344032)|  
  
## <a name="external-resources"></a>Dış kaynaklar  
  
### <a name="guidance"></a>Kılavuz  
 [Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: iç test etme](http://go.microsoft.com/fwlink/?LinkID=255188)