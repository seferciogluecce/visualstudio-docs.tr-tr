---
title: Idiasymbol::get_hasınlasm | Microsoft Docs
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
- IDiaSymbol::get_hasInlAsm method
ms.assetid: 7001c7cc-1459-4929-851b-a08066a803c6
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3aba3d106dd7787f53b8e1d24a9e9454eebe37fd
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49837171"
---
# <a name="idiasymbolgethasinlasm"></a>IDiaSymbol::get_hasInlAsm
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

İşlev satır içi bütünleştirilmiş kod içerip içermediğini belirten bir bayrak alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT get_hasInlAsm(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pFlag`  
 [out] Döndürür `TRUE` işlevi herhangi bir satır içi derleme; varsa döndürür, aksi takdirde, `FALSE`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simge için mevcut olmadığı anlamına gelir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Gereksinim|Açıklama|  
|-----------------|-----------------|  
|Üst bilgi:|dia2.h|  
|Sürüm:|DIA SDK v8.0|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



