---
title: 'Hata: Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi uzak bilgisayardaki farklı bir kullanıcı olarak çalışıyor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e2bdc731b65a8d451b6882914e8bed1abca2139b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31482028"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>Hata: Uzak bilgisayardaki Microsoft Visual Studio Uzaktan Hata Ayıklama İzleyicisi farklı kullanıcı olarak çalışıyor.
Uzaktan hata ayıklama yapmaya çalışırken, aşağıdaki hata iletisini alabilirsiniz:  
  
 Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi uzak bilgisayardaki farklı bir kullanıcı olarak çalışıyor.  
  
## <a name="cause"></a>Sebep  
 Bu ileti doğrulaması yok modda hata ayıklama ve msvsmon başlatan kullanıcının Visual Studio çalıştıran kullanıcının olmadığında oluşur.  
  
## <a name="solution"></a>Çözüm  
 Güvenli ve en iyi uzaktan bir hata ayıklama İzleyicisi (msvsmon.exe) çalıştırmak için Visual Studio ile aynı kullanıcı hesabı altında çözümüdür. Yapamıyorsanız, sahip olan bir hesabın altında uzaktan hata ayıklama İzleyicisi çalıştırabilirsiniz **hata ayıklamak herhangi bir kullanıcının** seçeneği uzaktan hata ayıklama İzleyicisi'nde seçili **seçenekleri** iletişim kutusu.  
  
> [!CAUTION]
>  Diğer kullanıcıların bağlanma izni verme yanlışlıkla yanlış uzaktan hata ayıklama oturumu için bağlanma olasılığı sağlar. Hata ayıklamayı **doğrulaması yok** modu hiçbir zaman güvenli değildir ve dikkatli kullanılmalıdır.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)