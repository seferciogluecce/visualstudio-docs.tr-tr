---
title: "Visual Studio 2017 kaldırma | Microsoft Docs"
description: "Visual Studio, adım adım kaldırmayı öğrenin."
ms.custom: 
ms.date: 09/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- uninstall
- uninstall Visual Studio
- remove
- remove Visual Studio
- cleanup
- cleanup Visual Studio
- clean up
- clean up Visual Studio
ms.assetid: 9c81a777-9c95-4934-b517-c60c6dc78799
author: heaths
ms.author: heaths
manager: erickn
ms.openlocfilehash: 7a93922bd33b3e5aa42d4bb271369d2d9b0a0c3d
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="remove-visual-studio"></a>Visual Studio Kaldır

Yıkıcı hatayla karşılaşan ve onarmak veya Visual Studio'yu kaldırmak, çalıştırabilirsiniz `InstallCleanup.exe` aracı yükleme dosyalarını ve ürün bilgileri kaldırmak için. Bu araç çalışır durumda değilse son çare olarak yapılması onarma veya kaldırma işlemi başarısız oldu ve özellikler, diğer Visual Studio yüklemeleri ya da onarılması gereken diğer ürünleri kaldırabilirsiniz.

Aşağıdaki yönergeleri aşağıdaki davranış ile farklı komut satırı anahtarları ile aracını çalıştırabilirsiniz:

| Anahtar | Davranış |
| ------ | -------- |
| `-i`   | Başka bir anahtarı iletilir ve yalnızca ana yükleme dizini ve ürün bilgileri kaldırır, bu anahtarı varsayılan değerdir. Bu davranış, çalıştırdıktan sonra aynı sürümünü yeniden yüklemek istiyorsanız, tercih edilir `InstallCleanup.exe` aracı. |
| `-f`   | Bu anahtarın belirtilmesi ana yükleme dizini, ürün bilgilerini ve diğer Visual Studio yüklemeler veya diğer ürünleri ile paylaşılan yükleme dizini dışındaki yüklenen çoğu özellikleri kaldırır. Bu davranış, daha sonra yeniden yüklemeden Visual Studio kaldırmak istiyorsanız, tercih edilir. |

1. Visual Studio Yükleyicisi’ni kapatın.
2. Bir yönetici komut istemi açın. Bir yönetici komut istemi açmak için şu adımları izleyin:
   * Üzerinde **Başlat** menüsünde tıklatın **çalıştırmak** (Start + R).
   * Tür **cmd**.
   * **Komut İstemi**'ne sağ tıklayın ve ardından **Yönetici olarak çalıştır**'a tıklayın.
3. Tam yolunu yazın `InstallCleanup.exe` yardımcı programı ve istediğiniz hangi komut satırı anahtarı geçirin. Varsayılan olarak, yardımcı program yolu aşağıdaki gibidir:
   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```

Bulamadı, `InstallCleanup.exe` Visual Studio yükleyicisi dizini altında - her zaman bulunan `%ProgramFiles(x86)%\Microsoft Visual Studio` -yönergelerini izleyin [Visual Studio yükleme](install-visual-studio.md) ve iş yükünü seçme ekranı görüntülendiğinde, Kapat Pencere ve yukarıdaki yeniden adımları izleyin.

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sorun giderme ipuçları için sayfa. Ürün sorunları bize de bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) aracı Visual Studio IDE içinde veya üzerinde bir öneri bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579). Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun. Bize ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio) (gerektiren bir [GitHub](https://github.com/) hesabı).

## <a name="see-also"></a>Ayrıca bkz.
* [Visual Studio 2017 yükleyin](install-visual-studio.md)
* [Visual Studio 2017 güncelleştir](update-visual-studio.md)
* [Visual Studio 2017 değiştirme](modify-visual-studio.md)
* [Visual Studio 2017 kaldırma](uninstall-visual-studio.md)