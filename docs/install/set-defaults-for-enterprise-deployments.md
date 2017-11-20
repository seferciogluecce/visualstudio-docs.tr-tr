---
title: "Visual Studio Kurumsal dağıtımlar için varsayılan değerleri ayarlama | Microsoft Docs"
description: "Etki alanı ilkeleri ve diğer yapılandırma işlemleri Visual Studio'nun kurumsal dağıtım için."
ms.date: 05/05/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- gpo
- policy
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 9B7B4608-7A3F-4FF4-BDCE-42D9F7CE6DBA
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: 11bcc331150b1e1ab9a8058b3538bca411345c19
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="set-defaults-for-enterprise-deployments-of-visual-studio"></a>Visual Studio kuruluş dağıtımları için Varsayılanlarını Ayarla

Visual Studio dağıtımını etkileyen kayıt defteri ilkeleri ayarlayabilirsiniz. Bu ilkeler, yeni yükleyici için geneldir ve etkiler:

- Diğer sürümler veya örnekleri paylaşılan bazı paketler yüklendiği
- Burada paketleri önbelleğe alınır
- Tüm paketler olup önbelleğe alınır

Bu ilkeleri kullanılarak bazıları ayarlayabilirsiniz [komut satırı seçenekleri](use-command-line-parameters-to-install-visual-studio.md)makinenizde kayıt defteri değerlerini ayarlayın veya bile bunları kuruluş genelinde Grup İlkesi'ni kullanarak dağıtın.

## <a name="registry-keys"></a>Kayıt defteri anahtarları

Kuruluş varsayılanlarını, Grup İlkesi aracılığıyla veya doğrudan kayıt defterinde kendi denetimini etkinleştirmek için ayarlayabileceğiniz çeşitli konumlardan vardır. Tüm kurumsal ilkeler ayarladığınız durumlarda görmek için Visual Studio sırayla arar; bir ilke değeri sırayla bulunduktan hemen sonra kalan anahtarları göz ardı edilir.

1. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\Setup`
2. `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\Setup`
3. `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\VisualStudio\Setup`(64-bit işletim sistemlerinde)

> [!IMPORTANT]
> Ayarlanmamış ise `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\Setup` anahtarı ve bunun yerine ayarlanmış diğer anahtarları biri, diğer iki anahtarlar 64-bit işletim sistemlerinde ayarlanmalıdır. Bu sorun gelecekteki ürün güncelleştirmede değinilmiştir.

Bazı kayıt defteri değerlerini, bunların kullanılan değilse zaten ayarlanmış ilk kez otomatik olarak ayarlanır. Bu yöntem, sonraki yüklemeler aynı değerlere kullanmanızı sağlar. Bu değerler ikinci kayıt defteri anahtarında depolanır `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\Setup`.

Aşağıdaki kayıt defteri değerlerini ayarlayabilirsiniz:

| **Ad** | **Türü** | **Varsayılan** | **Açıklama** |
| -------- | -------- | ----------- | --------------- |
| `CachePath` | `REG_SZ`veya`REG_EXPAND_SZ` | %ProgramData%\Microsoft\VisualStudio\Packages | Burada paket bildirimleri dizini ve isteğe bağlı, yükü depolanır. Nasıl okumak için [devre dışı bırakmak veya paket önbellek taşıma](disable-or-move-the-package-cache.md) daha fazla bilgi için. |
| `KeepDownloadedPayloads` | `REG_DWORD` | 1. | Hatta yüklendikten sonra paket yükü tutun. Değer dilediğiniz zaman değiştirebilirsiniz. İlkeyi devre dışı bırakmak, tüm önbelleğe alınan paket yükü onarmak veya değiştirmek, örneğin kaldırır. Nasıl okumak için [devre dışı bırakmak veya paket önbellek taşıma](disable-or-move-the-package-cache.md) daha fazla bilgi için. |
| `SharedInstallationPath` | `REG_SZ`veya`REG_EXPAND_SZ` | % ProgramFiles (x86) %\Microsoft Visual Studio\Shared | Visual Studio Örnekleri sürümleri arasında paylaşılan bazı paketler yüklendiği dizin. Değeri dilediğiniz zaman değiştirebilirsiniz, ancak gelecekte yükler yalnızca etkiler. Eski konuma yüklü ürünler taşınmaz gerekir veya doğru şekilde çalışmayabilir. |

> [!IMPORTANT]
> Değiştirirseniz `CachePath` mevcut pakete taşımak gerekir yükler önbelleğe yeni konuma ve emin olun sonra kayıt defteri ilke güvenli şekilde `SYSTEM` ve `Administrators` üzerinde tam denetime sahiptir ve `Everyone` okuma erişimine sahip.
> Varolan önbellek veya onu güvenli hale getirme taşımak için hata gelecekteki yüklemeler sorunlara neden olabilir.

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sorun giderme ipuçları için sayfa. Ürün sorunları bize de bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) aracı Visual Studio IDE içinde veya üzerinde bir öneri bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579). Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun. Bize ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio) (gerektiren bir [GitHub](https://github.com/) hesabı).

## <a name="see-also"></a>Ayrıca bkz.

 * [Visual Studio yükleme](install-visual-studio.md)
 * [Devre dışı bırakmak veya paket önbellek taşıma](disable-or-move-the-package-cache.md)
 * [Visual Studio'yu yüklemek için komut satırı parametreleri kullanma](use-command-line-parameters-to-install-visual-studio.md)