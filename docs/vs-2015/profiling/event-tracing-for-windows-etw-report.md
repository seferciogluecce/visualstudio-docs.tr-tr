---
title: Windows (ETW) raporu için olay izleme | Microsoft Docs
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
- Event tracing for Windows profiling report
- ETW profiling report
ms.assetid: 81e88162-b88a-40b6-8b85-a232c8096a47
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 627caa20d53bbb93c6c4477c3323dda57a37d9f0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49194788"
---
# <a name="event-tracing-for-windows-etw-report"></a>Windows için Olay İzleme (ETW) Raporu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bir performans oturumu içinde kaydedilen ETW olayları için olay izleme Windows (ETW) raporu listeler [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] profil oluşturma araçları. ETW verilerini bir ikili (.etl) dosyasında toplanır.  
  
> [!NOTE]
>  ETW raporları görüntüleyemez [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] arabirimi.  
  
-   ETW profil oluşturma araçları kullanarak toplama hakkında bilgi için [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] arabirim için bkz: [nasıl yapılır: veri toplamak için olay izleme Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).  
  
-   Kullanarak ETW veri toplama hakkında bilgi için [VSPerfCmd](../profiling/vsperfcmd.md) komut satırı araçları görmek [olayları](../profiling/events-vsperfcmd.md).  
  
-   Kullanarak ETW raporu oluşturma **VSReport / Summary: ETW** komutu. Daha fazla bilgi için [VSPerfReport](../profiling/vsperfreport.md).  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Zaman damgası**|Olay gerçekleştiğinde tanımlar.|  
|**İşlem kimliği**|Olayı oluşturan bir işlemi tanımlar.|  
|**İş parçacığı kimliği**|Olayı oluşturan iş parçacığını tanımlar.|  
|**Açıklama**|Olay sağlayıcısı tanımlar.|  
|**Türü**|Olay türü tanımlar.|  
|**Özellikler**|Olay Özellikleri. Her olay, parantez içine alınmış bir virgülle ayrılmış, ad-değer çiftidir.|



