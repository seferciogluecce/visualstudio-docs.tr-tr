---
title: Olay açıklamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 09f61652-7e16-4bb0-8055-f61a84bf384e
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ed2b4ccb50a40ce9820c2170b4994a6559ad7f3d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49217346"
---
# <a name="event-descriptions"></a>Olay Açıklamaları
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Her olay türüne belirli bir amacı vardır.  
  
## <a name="events-and-the-reasons-for-their-use"></a>Olayları ve bunların kullanılması için nedenler  
  
|Olay|Açıklama|  
|-----------|-----------------|  
|Belge olayları etkinleştirme|Hata ayıklama altyapısı (DE) veya belge öne getirmek IDE istediğinde gerçekleşir.|  
|Bağlı kesme noktası veya kesme noktası hata olayları|Gönderilen bir kesme noktası bağlı olduğunu veya ne zaman bir kesme noktası bağlanamıyor ve bir hata döndürdü.|  
|İlişkisiz bir kesme noktası olayları|İlişkili bir kesme noktası koddan keser ortaya çıkar.|  
|Olayları durdurabilirsiniz|Kullanıcı kodunda belirtilen bir noktada durdurmak isteyip istemediğinizi belirlemek için IDE gönderdi.|  
|Kesme noktası olayları|Bir kod veya veri kesme noktası isabet edildiğinde gerçekleşir.|  
|Belge metin olayları|Bir belgenin metni değiştiğinde oluşur. Bu olayları aracılığıyla gönderilmez `IDebugEventCallBack2::Event` yöntemi.|  
|Altyapı olayları oluşturma|Altyapının oluşturulduğunda gönderilir.|  
|Giriş noktası olayları|Hata ayıklanan programa başlatma kodunu çalıştırın ya da kendi ilk kullanıcı giriş noktası sınırına gönderilir.|  
|Özel durum olayları|Çalışan bir program ulaştığında bir özel durum gönderilir.|  
|İfade değerlendirme tam olayları|Zaman uyumsuz bir ifade değerlendirme işlemi tamamlandıktan sonra gönderilir.|  
|Sembol etkinlik bulun|Bir modül için sembolleri Bul kullanıcıdan DE gerektiğinde gönderilir.|  
|Tam olay yükle|Yalnızca ilk program yükleme tamamlandıktan ve programı çalıştırmak üzere ilk kodudur gönderilir.|  
|İleti olayları|Kullanıcılara gönderilen iletileri gönderilir.|  
|Modül yükleme olayları|Yeni bir modül yüklendiğinde veya kaldırılmış gönderilir.|  
|Çıkış dizesi olayları|Programın hata ayıklama çıkışını yazdığında gönderilir.|  
|Oluşturma ve yok etme olayları|Visual Studio IDE hataları ayıklanmakta olan program durumunu izlemek için oluşturma veya yok etme işlemleri, programlar, özellikleri, oturumları ve iş parçacıkları duyurmaktan gönderdi.|  
|Adım Tamamlandı olayları|Bir adım tamamlandıktan sonra gönderilir.|  
|İş parçacığı adı değişikliği olayları|Kullanıcı bir iş parçacığı adı değiştiğinde gönderilir.|  
|Program adı değişikliği olayları|Kullanıcı bir program adı değiştiğinde gönderilir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olayları Gönderme](../../extensibility/debugger/sending-events.md)

