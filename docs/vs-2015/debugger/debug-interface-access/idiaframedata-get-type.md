---
title: Idiaframedata::get_type | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_type method
ms.assetid: efca38b5-c479-4d0a-a164-f903f25c5509
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: abae285ebbb8401f399095101432b52e36baaab1
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49885778"
---
# <a name="idiaframedatagettype"></a>IDiaFrameData::get_type
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Derleyici özel çerçeve türünü alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_type (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Bir değer döndürür [StackFrameTypeEnum numaralandırması](../../debugger/debug-interface-access/stackframetypeenum.md) derleyici özgü çerçeve türünü belirten sabit listesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` varsa bu özelliği desteklenmiyor. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md)   
 [StackFrameTypeEnum Numaralandırması](../../debugger/debug-interface-access/stackframetypeenum.md)



