---
title: Waıtstart | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9f111ae1aed079f0c0cc0d94a1d1da7c8557e76
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49285915"
---
# <a name="waitstart"></a>WaitStart
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Waıtstart seçeneği yalnızca profil oluşturucu başlatıldı veya belirtilen sayıda saniye geçtikten döndürmek VSPerfCmd.exe başlangıç alt komut neden olur. Varsayılan olarak, başlangıç komut hemen döndürür. Başlangıç alt komutu, profil oluşturucu başlatma olmadan döndürürse, hata döndürülür. Saniye sayısı belirtilmezse, Start komutunu süresiz olarak bekler.  
  
 Bu profil oluşturucu başlatıldı sağlamak üzere toplu iş dosyalarında Waıtstart seçeneği kullanışlıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Seconds`  
 Başlangıç alt komuttan dönmeden önce beklenecek saniye sayısı.  
  
## <a name="required-options"></a>Gerekli seçenekleri  
 Waıtstart seçeneği yalnızca başlangıç alt komut ile kullanılabilir.  
  
 **Çıkış:** `filename`  
 Çıkış dosyası adını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Bu toplu dosya örnekte Start komutunu profil oluşturucuyu başlatmak 5 saniye bekler.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5  
if not %errorlevel% 0 goto :error_tag  
VSPerfCmd.exe /Launch:TestApp.exe  
goto :end  
:error_tag  
@echo Could not start Profiler!  
@echo Error %errorlevel%  
:end  
```



