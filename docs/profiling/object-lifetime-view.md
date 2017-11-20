---
title: "Nesne ömrü görünümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.objectlifetime
helpviewer_keywords:
- lifetime, objects
- Objects Lifetime view
- profiling tools reports, Lifetime view
- performance reports, objects lifetime view
- profiling tools, Lifetime view
ms.assetid: d0501fdd-4b3a-4e74-b6ac-51d950a2e15b
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b60a28d7422125a745cf1b088891b2675da0bc8a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="object-lifetime-view"></a>Nesne Ömrü Görünümü
Nesne ömrü görünümü kullanılabilir **ayrıca .NET nesne yaşam verisi toplama** Performans oturumunu özellik sayfalarında karşılaştırılır.  
  
 Çöp toplayıcı, [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] ayırma ve sürüm, uygulamanız için bellek yönetir. Atık toplayıcının performansını optimize etmek için, yönetilen yığın üç nesle ayrılır: 0, 1 ve 2. Çöp toplayıcı çalışma zamanının yeni nesneler kuşak 0 depolar. Koleksiyonları varlığını sürdürmesini nesneleri yükseltilmiş ve nesil 1 ve 2 depolanır.  
  
 Çöp toplayıcı, tüm nesil nesnelerin ayırmasını kaldırma bellek geri kazanır. Profili uygulama tarafından oluşturulan nesneleri için nesne ömrü görünümü sayısına ve boyutuna nesneleri ve bunların kazanılır nesil görüntüler.  
  
## <a name="general"></a>Genel  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Sınıf adı**|Ayrılmış türünün sınıfı adı.|  
|**İşlem kimliği**|Çalıştırma profili oluşturma, işlem kimliği.|  
|**İşlem adı**|İşlemin adı.|  
|**Modül adı**|İşlevi içeren modülü adı.|  
|**Modül yolu**|İşlevi içeren modülü yolu.|  
  
## <a name="instance-data"></a>Örnek veri  
 Örnek veri profil çalıştırma ve nesneleri çöp toplayıcı tarafından serbest nesil oluşturulan nesneleri türünün sayısını gösterir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Örnekleri**|Bu tür nesneler ayrılmasını sayısı.|  
|**Toplam örnek %**|Profil çalışma yapılan ayırmaları sayısı toplam yüzdesi.|  
|**Toplanan 0 örnekleri gen**|Kuşak atık toplama algoritması 0 serbest türdeki örneklerin sayısı.|  
|**Toplanan 1 örnekleri gen**|Çöp toplama algoritması 1. nesil serbest türdeki örneklerin sayısı.|  
|**Toplanan 2 örnekleri gen**|Çöp toplama algoritması 2. nesil serbest türdeki örneklerin sayısı.|  
|**Sonunda Canlı örnekleri**|Profil oluşturma sonuna kadar deallocated değil türün örneklerinin sayısını çalıştırın.|  
  
## <a name="size-byte-data"></a>Veri boyutu (bayt)  
 Boyutu (bayt) veri profil çalıştırma ve nesneleri serbest her oluşturma iadesi bellek miktarını oluşturulan nesneleri türü boyutunu gösterir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ayrılan toplam bayt sayısı**|Türündeki tüm örnekler için bayt toplam sayısı.|  
|**Toplam bayt sayısı %**|Bu tür örnekleri için ayrılan ayrılmış profil Çalıştır bayt sayısı toplam yüzdesi.|  
|**Toplanan 0 bayt gen**|Nesil atık toplama algoritması 0 serbest tür örneklerini boyutu.|  
|**Toplanan 1 bayt gen**|Çöp toplama algoritması 1. nesil serbest tür örneklerini boyutu.|  
|**2 bayt toplanan gen**|Çöp toplama algoritması 2. nesil serbest tür örneklerini boyutu.|  
  
## <a name="large-object-heap-data"></a>Büyük nesne yığın verileri  
 .NET bellek ayırıcısı standart yönetilen yığınından ayrı bir konumda çok büyük nesneleri yönetir. Büyük nesne yığın veri sayısını ve boyutunu bu konumda yönetiliyordu nesne türü gösterir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Toplanan büyük nesne yığın örnekleri**|Bu tür büyük nesne yığın içinde bulunan ve profil toplanan örnek sayısı çalıştırın.|  
|**Büyük nesne yığın bayt toplanan**|Bu tür örneklerinin büyük nesne yığın içinde bulunan ve Çalıştır profil toplanan bayt cinsinden boyutu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)