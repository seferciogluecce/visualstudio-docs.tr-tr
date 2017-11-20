---
title: "JSON.parse işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: JSON.parse
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- parse JSON method
- JSON.parse method
ms.assetid: 20f00d31-5ab5-4c3c-ab49-2534fc39a9b4
caps.latest.revision: "41"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d66aee32a191c8cc1879c9436788c196c05e7bd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsonparse-function-javascript"></a>JSON.parse İşlevi (JavaScript)
JavaScript Object Notation (JSON) dizesini bir nesneye dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
JSON.parse(text [, reviver])  
```  
  
## <a name="parameters"></a>Parametreler  
 `text`  
 Gerekli. Geçeri JSON dizesi.  
  
 `reviver`  
 İsteğe bağlı. Sonuçları dönüştüren bir işlev. Bu işlev, nesnenin her üyesi için çağırılır. Eğer bir üye iç içe nesneler içeriyorsa, iç içe nesneler üst nesneden önce dönüştürülür. Her üye için aşağıdaki gerçekleşir:  
  
-   Varsa `reviver` üye değeri geçerli bir değer dönüştürülmüş değeriyle değiştirilir döndürür.  
  
-   Varsa `reviver` aldığı, aynı değeri üye değişiklik döndürür.  
  
-   Varsa `reviver` döndürür `null` veya `undefined`, üye silinir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir nesne veya dizi.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Bu işlev neden olursa bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ayrıştırıcı hatası (gibi "SCRIPT1014: geçersiz karakter"), giriş metni JSON söz dizimi ile uyumlu değil. Hatayı düzeltmek için, aşağıdakilerden birini yapın:  
  
-   Değiştirme `text` JSON söz dizimi ile uyum sağlamak için bağımsız değişken. Daha fazla bilgi için bkz: [BNF sözdizim gösterimi](http://go.microsoft.com/fwlink/?LinkId=125203) JSON nesnelerinin.  
  
     Örneğin yanıt pure JSON yerine JSONP biçimindeyse yanıt nesnesinde bu kodu deneyin:  
  
    ```JavaScript  
    var fixedResponse = response.responseText.replace(/\\'/g, "'");  
    var jsonObj = JSON.parse(fixedResponse);  
    ```  
  
-   Olduğundan emin olun `text` bağımsız değişkeni seri duruma getirildi JSON uyumlu bir uygulama tarafından gibi `JSON.stringify`.  
  
-   Çalıştırma `text` gibi bir JSON Doğrulayıcı değişkeninde [JSLint](http://www.jslint.com/) sözdizimi hataları belirlemenize yardımcı olması için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `JSON.parse` bir JSON dizesinde nesneye dönüştürülemiyor.  
  
```JavaScript  
var jsontext = '{"firstname":"Jesper","surname":"Aaberg","phone":["555-0100","555-0120"]}';  
var contact = JSON.parse(jsontext);  
document.write(contact.surname + ", " + contact.firstname);  
document.write(contact.phone[1]);  
// Output:  
// Aaberg, Jesper  
// 555-0100  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örneği kullanarak bir dizi JSON dizeye dönüştürür `JSON.stringify`ve kullanarak bu dize bir diziye dönüştürür `JSON.parse`.  
  
```JavaScript  
var arr = ["a", "b", "c"];  
var str = JSON.stringify(arr);  
document.write(str);  
document.write ("<br/>");  
  
var newArr = JSON.parse(str);  
  
while (newArr.length > 0) {  
    document.write(newArr.pop() + "<br/>");  
}  
  
// Output:  
// ["a","b","c"]  
// c  
// b  
// a  
```  
  
## <a name="example"></a>Örnek  
 `reviver` İşlevi International Organization JSON gösterimi Standardization (ISO) tarih dizeleri için Eşgüdümlü Evrensel Saat (UTC) biçimine dönüştürmek için kullanılan genellikle `Date` nesneleri. Bu örnekte `JSON.parse` bir tarih ISO biçimli dize seri durumdan çıkarılamadı. `dateReviver` İşlev döndürür `Date` nesneleri gibi ISO biçimlendirilmiş üyeleri için tarih dizeleri.  
  
```JavaScript  
var jsontext = '{ "hiredate": "2008-01-01T12:00:00Z", "birthdate": "2008-12-25T12:00:00Z" }';  
var dates = JSON.parse(jsontext, dateReviver);  
document.write(dates.birthdate.toUTCString());  
  
function dateReviver(key, value) {  
    var a;  
    if (typeof value === 'string') {  
        a = /^(\d{4})-(\d{2})-(\d{2})T(\d{2}):(\d{2}):(\d{2}(?:\.\d*)?)Z$/.exec(value);  
        if (a) {  
            return new Date(Date.UTC(+a[1], +a[2] - 1, +a[3], +a[4],  
                            +a[5], +a[6]));  
        }  
    }  
    return value;  
};  
  
// Output:  
// Thu, 25 Dec 2008 12:00:00 UTC  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JSON.stringify işlevi](../../javascript/reference/json-stringify-function-javascript.md)   
 [toJSON yöntemi (tarih)](../../javascript/reference/tojson-method-date-javascript.md)   
 [Hub şablon örnek uygulama (Windows mağazası)](http://code.msdn.microsoft.com/Hub-template-sample-with-4b70002d)