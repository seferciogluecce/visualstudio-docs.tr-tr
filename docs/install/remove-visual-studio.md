---
title: Visual Studio 2017 Kaldır | Microsoft Docs
description: Tamamen Visual Studio, adım adım bilgisayarınızdan öğrenin.
ms.custom: ''
ms.date: 09/12/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
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
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e72482dce3df2ceaa5d5131838ce08b13a05cd90
ms.sourcegitcommit: c5e72875206b8c5737c29d5b1ec7b86eec747303
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/17/2018
ms.locfileid: "49382772"
---
# <a name="remove-visual-studio"></a>Visual Studio Kaldır

Siz işlemi yıkıcı hatayla karşılaşırsanız ve onarmak ya da Visual Studio'yu kaldırın, çalıştırabileceğiniz `InstallCleanup.exe` aracı yükleme dosyalarını ve tüm yüklü örnekler Visual Studio 2017'in ve ürün bilgileri kaldırmak için. Bu araç çalışıyor durumunda son çare olarak yapılması onarma veya kaldırma işlemi başarısız oldu ve özellikler, diğer Visual Studio yüklemeleri ya da onarılması için gereken diğer ürünleri kaldırabilirsiniz.

Aşağıdaki yönergeler aşağıdaki davranış farklı komut satırı anahtarları ile aracını çalıştırabilirsiniz:

| Anahtar | Davranış |
| ------ | -------- |
| `-i`   | Diğer bir anahtara geçirilir ve yalnızca ana yükleme dizini ve ürün bilgilerini kaldırır. Bu anahtar varsayılandır. Bu çalıştırdıktan sonra aynı sürümü yeniden yüklemek istiyorsanız, tercih, davranıştır `InstallCleanup.exe` aracı. |
| `-f`   | Bu anahtarın belirtilmesi, ana yükleme dizini, ürün bilgileri ve diğer Visual Studio yüklemeleri veya diğer ürünleri ile paylaşılan yükleme dizininin dışına yüklü çoğu özelliği kaldırır. Bu davranış, Visual Studio, daha sonra yeniden yüklemeden kaldırmak istiyorsanız, tercih edilir. |

1. Visual Studio Yükleyicisi’ni kapatın.
2. Bir yönetici komut istemi açın. Bir yönetici komut istemi açmak için şu adımları izleyin:
   * Tıklayın **Başlat** menüsü
   * Tür **cmd**.
   * **Komut İstemi**'ne sağ tıklayın ve ardından **Yönetici olarak çalıştır**'a tıklayın.
3. Tam yolunu yazın `InstallCleanup.exe` yardımcı programı ve istediğiniz herhangi bir komut satırı anahtarı geçirin. Varsayılan olarak, yardımcı program yolu aşağıdaki gibidir:
   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```

Bulunamadı, `InstallCleanup.exe` - Visual Studio yükleyicisi dizini altında bulunan her zaman `%ProgramFiles(x86)%\Microsoft Visual Studio` -yönergelerini izleyin [Visual Studio yükleme](install-visual-studio.md) ve iş yükü seçimi ekran görüntülendiğinde, Kapat Pencere ve önceki adımları tekrar uygulayın.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio 2017'yi Yükleme](install-visual-studio.md)
* [Visual Studio 2017 güncelleştirmesi](update-visual-studio.md)
* [Visual Studio 2017'yi Değiştirme](modify-visual-studio.md)
* [Visual Studio 2017'yi kaldırın](uninstall-visual-studio.md)
