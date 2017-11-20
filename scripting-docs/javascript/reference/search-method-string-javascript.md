---
title: "search yöntemi (dize) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: search
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: search method
ms.assetid: 1cae0fbc-3319-4327-ba4e-d5fa2c4a9ba0
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 730fb1604147b56fc5ab1e312bf7a6dfb5487a5a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="search-method-string-javascript"></a>search Yöntemi (Dize) (JavaScript)
İlk eşleşmesinin bir normal ifade araması bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
stringObj.search(rgExp)   
```  
  
## <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. `String` Nesne veya arama yapmak, değişmez dize değeri.  
  
 `rgExp`  
 Gerekli. Örneği bir **normal ifade** normal ifade deseni ve geçerli bayrakları içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir eşleşme bulunamazsa, **arama** yöntemi, ilk eşleşmeyi oluştuğu dizesinin başından uzaklık belirten bir tamsayı değeri döndürür. Eşleşme yoksa -1 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıca ayarlayabilirsiniz `i` duyarsız arama neden bayrağı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **arama** yöntemi.  
  
```JavaScript  
var src = "is but a Dream within a dream";  
var re = /dream/;  
var pos = src.search(re);  
document.write(pos);  
document.write("<br/>");  
  
re = /dream/i;  
pos = src.search(re);  
document.write(pos);  
  
// Output:   
// 24   
// 9  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Exec yöntemi (normal ifade)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [match yöntemi (dize)](../../javascript/reference/match-method-string-javascript.md)   
 [Normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [replace yöntemi (dize)](../../javascript/reference/replace-method-string-javascript.md)   
 [test yöntemi (normal ifade)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Normal ifade programlama (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)