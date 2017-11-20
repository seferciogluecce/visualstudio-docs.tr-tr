---
title: "Aç dosya komutunu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: file.openfile
helpviewer_keywords:
- Open File command
- File.OpenFile command
- of command
ms.assetid: a51a83fc-e3c6-4fa2-8882-8b7b6c0a6406
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f7b1576ce7c34e953c45d7b303190a00d77e86cc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="open-file-command"></a>Dosya Aç Komutu
Varolan bir dosyayı açar ve bir düzenleyicide belirtmenize olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.OpenFile filename [/e:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Gerekli. Tam veya kısmi yol ve dosya adı dosyayı açın. Boşluk içeren yollar tırnak işaretleri içine alınmalıdır.  
  
## <a name="switches"></a>Anahtarlar  
 / e:`editorname`  
 İsteğe bağlı. Dosya açılacak düzenleyicinin adı. Bağımsız değişken belirtildi, ancak hiçbir Düzenleyici adı sağlanan **birlikte Aç** iletişim kutusu görüntülenir.  
  
 / E:`editorname` bağımsız değişkeni açık ile iletişim kutusunda tırnak işaretleri içine göründükleri gibi Düzenleyici adları söz dizimini kullanır.  
  
 Örneğin, bir dosyayı kaynak kod düzenleyicisinde açmak için aşağıdaki / e: için girersiniz`editorname` bağımsız değişkeni.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yol girin gibi otomatik tamamlama doğru yolun ve dosya adı bulmaya çalışır.  
  
## <a name="example"></a>Örnek  
 Bu örnek stil dosyasını "Test1.css" Kaynak Kod Düzenleyicisi'nde açar.  
  
```  
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Komut penceresi](../../ide/reference/immediate-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)