---
title: Idiaenumsourcefiles::Next | Microsoft Docs
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
- IDiaEnumSourceFiles::Next method
ms.assetid: 83bf6317-ff39-4c5c-8987-cba34e7a6983
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab70bb42228451d6683dcebfb5ec3ebd6f7e8a32
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49897322"
---
# <a name="idiaenumsourcefilesnext"></a>IDiaEnumSourceFiles::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Belirtilen bir sabit listesi sırası kaynak dosyalarında sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Next (   
   ULONG            celt,  
   IDiaSourceFile** rgelt,  
   ULONG*           pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 celt  
 [in] Alınacak Numaralandırıcı kaynak dosya sayısı.  
  
 http://msdn.microsoft.com/library/default.asp?url=/library/en-us/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp  
 [out] İle doldurulacak bir dizi [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md) istenen kaynak dosyalarını temsil eden nesneleri.  
  
 pceltFetched  
 [out] Kaynak dosyalarının getirilen bir numaralandırıcı döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` daha fazla kaynak dosya yoksa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumsourcefiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [Idiasession::findlinesbylinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)



