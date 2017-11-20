---
title: "SccIsMultiCheckoutEnabled işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccIsMultiCheckoutEnabled
helpviewer_keywords: SccIsMultiCheckoutEnabled function
ms.assetid: 6721639d-e475-4766-81b5-ee40a280fc70
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6ca1f26078a590ae2034218c5df4a74b66fa2449
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sccismulticheckoutenabled-function"></a>SccIsMultiCheckoutEnabled işlevi
Bu işlev, kaynak denetim eklentisi bir dosyada birden çok kullanıma izin verip vermediğini denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccIsMultiCheckoutEnabled(  
   LPVOID pContext,  
   LPBOOL pbMultiCheckout  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 pbMultiCheckout  
 [out] Birden çok kullanıma bu proje için (birden çok kullanıma desteklenir sıfır olmayan anlamına gelir) etkinleştirilip etkinleştirilmeyeceğini belirtir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Denetimi başarısız oldu.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 IDE dosyaları aynı anda birden fazla kullanıcı tarafından kullanıma alınabilen varsa belirlemek için iki denetimler yapar. İlk olarak, kaynak denetim sistemi birden çok kullanıma desteklemesi gerekir. Kaynak Denetim eklentisi Bu yetenek başlatma sırasında belirterek belirtebilirsiniz `SCC_CAP_MULTICHECKOUT`. Bundan sonra ikinci bir onay IDE geçerli projenin birden çok kullanıma destekleyip desteklemediğini belirlemek için bu işlevi çağırır. Seçili proje için birden çok kullanıma destekleniyorsa, başarılı bir eklenti döndürür kod ve ayarlar `pbMultiCheckout` için sıfır olmayan (`TRUE`) veya `FALSE`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)