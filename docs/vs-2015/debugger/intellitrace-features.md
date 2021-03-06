---
title: IntelliTrace özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IntelliTrace, debugging with events
- IntelliTrace, recording execution history
- debugging [Visual Studio ALM], recording execution history
- IntelliTrace, turn off
- IntelliTrace, navigating event and call history
- IntelliTrace, saving your session
- IntelliTrace, enabling
- IntelliTrace, start debugging
- IntelliTrace, debugging with events and call information
- IntelliTrace, disabling
- IntelliTrace, turn on
- debugging [Visual Studio ALM], IntelliTrace
ms.assetid: 5ccc059c-6097-46b4-9d4b-34236c02d549
caps.latest.revision: 73
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b4443c18b6972d87d49272d33e7d2f33c25277c7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49278557"
---
# <a name="intellitrace-features"></a>IntelliTrace Özellikleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

IntelliTrace olayları için kullanabilir ve, kendi durumunu (çağrı yığınını ve yerel değişken değerleri) yürütmesinde farklı noktalarda incelemenize olanak tanır, uygulama yöntemini çağırır. Yalnızca zamanki gibi hata ayıklamaya başlayın. - IntelliTrace varsayılan olarak açıldı ve IntelliTrace kaydı yeni bilgileri görebilirsiniz **tanılama araçları** penceresinin altında **olayları** sekmesi. Bir olay seçin ve tıklayın **etkinleştirmek geçmiş hata ayıklama** bu olay için kaydedilen Yereller ve çağrı yığınını görmek için.  
  
 Adım adım bir açıklaması için bkz. [izlenecek yol: IntelliTrace'i kullanarak](../debugger/walkthrough-using-intellitrace.md).  
  
 IntelliTrace kullanılabilir Visual Studio Enterprise sürümünde, ancak Visual Studio Professional veya Community sürümlerini içinde değil.  
  
 Intellitrace'in açık olduğunu doğrulamak için açık **Araçlar / Seçenekler / IntelliTrace** seçenekler sayfası. **IntelliTrace'i etkinleştirme** varsayılan olarak işaretlenmelidir.  
  
> [!NOTE]
>  Tüm ayarlar kapsamını **IntelliTrace** seçenekler sayfası olan Visual Studio bir bütün, bunları ayrı projeler veya çözümler. Bu ayarlar bir değişiklik, Visual Studio, tüm hata ayıklama oturumları ve tüm projeler veya çözümlerden tüm örneklerine uygulanır.  
  
##  <a name="ChooseEvents"></a> Intellitrace'in kaydettiği olayları seçin  
 Veya belirli IntelliTrace olaylarının kaydı devre dışı bırakabilirsiniz.  
  
 Hata ayıklama, hata ayıklamayı durdurun. Git **Araçlar / Seçenekler / IntelliTrace / IntelliTrace olayları**. Intellitrace'in kaydedeceği olayları seçin.  
  
##  <a name="GoingFurther"></a> IntelliTrace olaylarını toplamak ve çağrı bilgileri  
 Bu, varsayılan olarak etkin değildir, ancak IntelliTrace yöntemi çağrılarını olaylarla birlikte kaydedebilir. Yöntem çağrıları Git toplanmasını etkinleştirmek için **Araçlar / Seçenekler / IntelliTrace / genel**seçip **IntelliTrace olayları ve çağrı bilgileri**.  
  
 Bu, çağrı yığını geçmişini görmenizi ve kodunuzdaki çağrılar arasında ileri geri adım sağlar. IntelliTrace yöntem adları, yöntemi giriş ve çıkış noktaları ve belirli parametre değerleri ve dönüş değerleri gibi verileri kaydeder.  
  
> [!TIP]
>  Önemli ölçüde gider eklediğinden bu seçenek varsayılan olarak etkin değil. Yalnızca IntelliTrace sağlar, uygulamanızın her yöntem çağrısının müdahale gerekmez, ancak Ayrıca ekranda gösteren veya diske kalıcı söz konusu olduğunda çok daha büyük bir veri ile dağıtılacak içerir.  
>   
>  Intellitrace'in kaydettiği olayları listesi kısıtlayarak performans yükünü azaltabilir ve modül sayısı tutarak en topluyoruz. Daha fazla bilgi için [denetimi ne kadar çağrı bilgilerini Intellitrace'in kaydettiği](../debugger/intellitrace-features.md#ControlCallData).  
  
### <a name="using-the-navigation-gutter"></a>Gezinti kanalını kullanma  
 Görüntülenen gezinti cilt payını sola kod penceresinin kullanabilirsiniz. Gezinti kanalını göremiyorsanız, Git **Araçlar / Seçenekler / IntelliTrace / Gelişmiş**seçip **hata ayıklama modunda Gezinti kanalını görüntüleme**.  
  
 Gezinti cilt payını yöntem çağrıları ve olayları geçmiş hata ayıklama modunda iletir ve geriye doğru gezinmek sağlar. Geçmiş hata ayıklama hakkında daha fazla bilgi için bkz. [geçmiş hata ayıklama](../debugger/historical-debugging.md). Bir dizi komut içerir:  
  
|||  
|-|-|  
|**Hata ayıklayıcı bağlamı buraya Ayarla**|Hata ayıklama bağlamını göründüğü çağrı zaman çerçevesine ayarlayın.<br /><br /> Bu simge yalnızca geçerli çağrı yığını üzerinde görünür.|  
|**Çağıran siteye geri dön**|İşaretçiyi ve hata ayıklama içeriğini geri burada geçerli işlev çağrıldı için taşıyın.<br /><br /> Canlı hata ayıklama modunda iseniz, bu komut geçmiş hata ayıklama açar. Özgün yürütme sonu giderseniz, geçmiş hata ayıklama kapalıdır ve canlı hata ayıklama açıktır.|  
|**Önceki çağrıya veya IntelliTrace olayına Git**|İşaretçiyi ve hata ayıklama içeriğini geri önceki çağrıya veya olaya taşıyın.<br /><br /> Canlı hata ayıklama modunda iseniz, bu komut, geçmiş hata ayıklamayı etkinleştirir.|  
|**Adımı**|Şu anda seçili işleve adım.<br /><br /> Bu komut, yalnızca geçmiş hata ayıklama modunda olduğunda kullanılabilir.|  
|**Sonraki çağrıya veya IntelliTrace olayına gidin**|İşaretçiyi ve hata ayıklama içeriğini sonraki çağrıya veya olaya hangi IntelliTrace verilerinin var taşıyın.<br /><br /> Bu komut, yalnızca geçmiş hata ayıklama modunda olduğunda kullanılabilir.|  
|**Canlı moda Git**|Canlı hata ayıklama modunu döndürür.|  
  
### <a name="search-for-a-line-or-method-in-intellitrace"></a>Bir satır veya yöntemi IntelliTrace içinde Ara  
 Yalnızca yöntem çağrı bilgisi etkinken yöntemleri arama yapabilirsiniz. Belirli bir satır ya da yöntem için IntelliTrace geçmişini arama yapabilirsiniz. Hata ayıklayıcı yürütme durdurulur, ancak bağlam menüsünün görmek için işlev gövdesi içinde sağ tıklayın ve tıklayın **arama için bu satırı, IntelliTrace** veya **arama için bu yöntemi, IntelliTrace**.  
  
###  <a name="ControlCallData"></a> Ne kadar çağrı bilgisi Intellitrace'in kaydettiği denetleme  
 Varsayılan olarak, IntelliTrace, çözümünüz tarafından kullanılan tüm modüller için bilgileri kaydeder. IntelliTrace yalnızca sizi ilgilendiren modüller için çağrı bilgileri kaydetmesini ayarlayabilirsiniz. İçinde **Araçlar / Seçenekler / IntelliTrace / modülleri**, modülleri içerecek şekilde veya IntelliTrace dosyasından dışlanacak modülleri belirtin. IntelliTrace, belirttiğiniz modüllerden oluşturulan olayları toplar ve ilginizi çeken modülleri içinde gerçekleşen yöntem çağrıları.  
  
 Birden çok modül eklemek için dizenin başında veya sonunda * joker karakterini kullanın. Modül isimleri için derleme adlarını değil dosya adlarını kullanın. Dosya yolları kabul edilmez.  
  
 Modül sayısı için en az tutmaya çalışın. Toplanacak verileri daha az olduğundan daha iyi performansı elde edin. Üzerinden geçmek üzere daha az veri olmadığından kullanıcı Arabiriminde daha az gürültü de alırsınız.  
  
##  <a name="SaveSession"></a> IntelliTrace verilerini dosyasına kaydetme  
 IntelliTrace topladığı verileri kaydedebilirsiniz gidip **hata ayıklama / IntelliTrace / IntelliTrace oturumunu Kaydet** hata ayıklama ve bir kesme durumunda uygulamasıdır. Menü öğesi devre dışı bırakılır ve IntelliTrace uygulama hala çalışıyorsa veya hata ayıklama durdurduysanız toplanan verileri kaydetmek mümkün olmayacaktır.  
  
 Otomatik olarak giderek bir dosyaya kaydetmek için IntelliTrace'i yapılandırabilirsiniz **Araçlar / Seçenekler / IntelliTrace / Gelişmiş** seçerek **Store IntelliTrace kayıtlarını bu dizinde**. Alan tükendiğinde eski verilerin üzerine yazılacak IntelliTrace neden oluşturulan bir dosyanın boyutunu Ayarla de yapılandırabilirsiniz. Visual Studio, ne zaman otomatik olarak kaydedilir ve Visual Studio barındırma süreci (vshost.exe) etkinleştirilir her IntelliTrace oturumu için iki dosya oluşturur.  
  
> [!TIP]
>  Disk alanından kazanmak için artık gerekmediğinde dosyaları otomatik olarak kaydetmeyi devre dışı bırakın. Var olan dosyalar silinmez. Her zaman isteğe bağlı dosya için bağlam menüsünden tasarruf sağlayabilirsiniz.  
  
 IntelliTrace verilerini dosyasını kaydettiğinizde, toplanan IntelliTrace her işlem için bir .itrace dosyası alın. Ardından .itrace dosyasını Visual Studio'da giderek açabileceğiniz **dosya / açın / dosya** ve Dosya Aç iletişim kutusundan .itrace dosyasını seçme. Daha fazla bilgi için [kayıtlı IntelliTrace verilerini kullanma](../debugger/using-saved-intellitrace-data.md).  
  
## <a name="blogs"></a>Bloglar  
 [Visual Studio Enterprise 2015'te IntelliTrace](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/intellitrace-in-visual-studio-ultimate-2015.aspx)  
  
 [İzlenecek yol, Live Visual Studio 2015 (metin düzenleyici) IntelliTrace kullanarak hata ayıklama](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/walkthrough-of-live-debugging-using-intellitrace-in-visual-studio-2015-text-editor.aspx)  
  
 [İzlenecek yol, Live Visual Studio 2015 (sosyal kulübü) IntelliTrace kullanarak hata ayıklama](http://blogs.msdn.com/b/visualstudioalm/archive/2000/1/1/walkthrough-of-live-debugging-using-intellitrace-in-visual-studio-2015-social-club.aspx)  
  
 [Visual Studio Enterprise destekler ekleme artık 2015'te IntelliTrace!](http://blogs.msdn.com/b/visualstudioalm/archive/2015/05/14/intellitrace-in-visual-studio-enterprise-2015-now-supports-attach.aspx)  
  
 [IntelliTrace Standalone Collector'ı kullanarak bir windows hizmetini veri topla](http://blogs.msdn.com/b/visualstudioalm/archive/2015/05/14/collect-data-from-a-windows-service-using-the-intellitrace-standalone-collector.aspx)  
  
 [IntelliTrace toplama planını düzenleme](http://blogs.msdn.com/b/visualstudioalm/archive/2015/03/09/editing-the-intellitrace-collection-plan.aspx)  
  
 [Özel TraceSource ve IntelliTrace kullanarak hata ayıklama](http://blogs.msdn.com/b/visualstudioalm/archive/2014/12/17/custom-tracesource-and-debugging-using-intellitrace.aspx)  
  
 [Active Directory hesapları altında çalışan IntelliTrace Standalone Collector ve uygulama havuzları](http://blogs.msdn.com/b/visualstudioalm/archive/2014/12/22/intellitrace-standalone-collector-and-application-pools-running-under-active-directory-accounts.aspx)  
  
## <a name="forums"></a>Forumlar  
 [Visual Studio Debugger](http://go.microsoft.com/fwlink/?LinkId=262263)  
  
## <a name="videos"></a>Videolar  
 [IntelliTrace deneyimi](https://channel9.msdn.com/Series/Visual-Studio-2015-Enterprise-Videos/IntelliTrace-Experience)  
  
 [Microsoft Visual Studio içinde IntelliTrace geçmiş hata ayıklama Ultimate 2015](https://channel9.msdn.com/events/Ignite/2015/BRK3716)





