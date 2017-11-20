---
title: Idiaframedata::get_program | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData::get_program method
ms.assetid: 9201409e-b4b1-4e2e-a9f8-d17678ac538b
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a26982c1827b9d9b4a7ed09e8aa3af61c9141c9f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaframedatagetprogram"></a>IDiaFrameData::get_program
Geçerli işlevi çağırmadan önce ayarlayın kayıt hesaplamak için kullanılan program dizesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_program (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Program dize döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` bu özellik desteklenmiyorsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Program dize giriş kurabilmek için yorumlanan makroları dizisidir. Örneğin, tipik yığın çerçevesi program dizesi kullanabilir `"$T0 $ebp = $eip $T0 4 + ^ = $ebp $T0 ^ = $esp $T0 8 + ="`. Biçim burada işleçleri işlenenler izleyin ters Lehçe gösterimidir. `T0`Yığında geçici bir değişkeni temsil eder. Bu örnekte aşağıdaki adımları gerçekleştirir:  
  
1.  YAZMAÇ içeriğini taşımak `ebp` için `T0`.  
  
2.  Ekleme `4` değerine `T0` bir adresi oluşturmak, o adresinden değerini almak ve kayıttaki değeri depolamak için `eip`.  
  
3.  Depolanan adresinden değeri Al `T0` ve değeri kayıttaki depola `ebp`.  
  
4.  Ekleme `8` değerine `T0` ve değeri kayıttaki depola `esp`.  
  
 Program dize CPU ve geçerli yığın çerçevesi tarafından temsil edilen işlevi için ayarlanan çağırma belirli olduğuna dikkat edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md)