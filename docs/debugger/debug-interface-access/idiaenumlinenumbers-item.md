---
title: Idiaenumlinenumbers::Item | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumLineNumbers::Item method
ms.assetid: 08efbeaf-22f7-49e9-96a8-bb906dfe4fd8
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ee969a4451e8301bc8c110c71f6de18badfede4f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumlinenumbersitem"></a>IDiaEnumLineNumbers::Item
Bir satır sayısı bir dizin yoluyla alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Item (   
   DWORD            index,  
   IDiaLineNumber** lineNumber  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 dizin  
 [in] Dizin [Idialinenumber](../../debugger/debug-interface-access/idialinenumber.md) alınacak nesne. Aralıktaki 0 dizinidir `count`-1, burada `count` tarafından döndürülen [Idiaenumlinenumbers::get_Count](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md) yöntemi.  
  
 lineNumber  
 [out] Döndürür bir [Idialinenumber](../../debugger/debug-interface-access/idialinenumber.md) istediğiniz satır numarasını temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [Idialinenumber](../../debugger/debug-interface-access/idialinenumber.md)