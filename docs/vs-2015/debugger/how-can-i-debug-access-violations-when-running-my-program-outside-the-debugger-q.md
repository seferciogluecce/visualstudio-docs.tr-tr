---
title: Kendi Programımı Hata Ayıklayıcı Dışında Çalıştırırken Erişim İhlallerinde Nasıl Hata Ayıklayabilirim? | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.access
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 486b981311d93a93866622ccf80b6eabdee748ff
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49290764"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Kendi Programımı Hata Ayıklayıcı Dışında Çalıştırırken Erişim İhlallerinde Nasıl Hata Ayıklayabilirim?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Sorun açıklaması  
 Kendi programımı Visual Studio ortamında düzgün çalışıyor, ancak bu tek başına Windows işletim sistemiyle birlikte çalıştırabilir, erişim ihlali üretir. Bu sorunu nasıl hata ayıklaması yapabilirsiniz?  
  
## <a name="solution"></a>Çözüm  
 Ayarlama [Just-ın-time hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md) seçenek ve erişim ihlali gerçekleşene kadar tek başına programınızı çalıştırın. Ardından **erişim ihlali** iletişim kutusu, tıklayabilirsiniz **iptal** hata ayıklayıcıyı başlatmak için.  
  
 Bilgi Bankası makalesi Q133174, ayrıca bkz: "Konusunda bir genel koruma (GP) hata oluştuğu bulun." MSDN Kitaplığı CD'sindeki veya arama tabanı makalelerini bulabilirsiniz [ http://support.microsoft.com/ ](http://support.microsoft.com/).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Yerel Kodda Hata Ayıklama](../debugger/debugging-native-code.md)



