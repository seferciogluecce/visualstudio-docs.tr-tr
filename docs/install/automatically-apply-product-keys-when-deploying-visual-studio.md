---
title: "Visual Studio'yu dağıtırken ürün anahtarlarını otomatik olarak Uygula | Microsoft Docs"
ms.custom: 
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 157ef18baa38169790fe528fd3358fbea8ff6196
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="automatically-apply-product-keys-when-deploying-visual-studio"></a>Visual Studio'yu dağıtırken ürün anahtarlarını otomatik olarak Uygula
Ürün anahtarınızı program aracılığıyla Visual Studio dağıtımını otomatik hale getirmek için kullanılan bir komut dosyasının parçası olarak uygulayabilirsiniz. Bir ürün anahtarı bir aygıtta program aracılığıyla Visual Studio veya bir yükleme tamamlandıktan sonra bir yükleme sırasında ya da ayarlayabilirsiniz.

## <a name="apply-the-license-after-installation"></a>Yüklemeden sonra lisans Uygula
 Kullanarak bir yüklü olan sürümü Visual Studio ürün anahtarıyla etkinleştirebilirsiniz `StorePID.exe` sessiz modda hedef makinelere yardımcı programı. `StorePID.exe`Visual Studio 2017 aşağıdaki varsayılan konuma yükler bir yardımcı programdır: <br> `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE`

 Çalıştırma `StorePID.exe` yükseltilmiş ayrıcalıklarla ya da kullanarak System Center aracı veya yükseltilmiş bir komut istemi. Ürün anahtarı ve Microsoft ürün kodu (MPC) ile izleyin.

>[!IMPORTANT]
> Ürün anahtarı tireler dahil ettiğinizden emin olun.

 ```
 StorePID.exe [product key including the dashes] [MPC]
 ```

 Visual Studio 2017 bir MPC 08860 biri olan bir kuruluş için lisans uygulamak için bir komut satırı aşağıdaki örnekte bir ürün anahtarı `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE`, varsayılan yükleme konumu varsayar:

 ```cmd
 "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 08860
 ```

 Aşağıdaki tabloda her Visual Studio sürümü için MPC kodlarını listeler:

| Visual Studio sürümü                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2017        | 08860 |
| Visual Studio Professional 2017      | 08862 |
| Visual Studio Test Uzmanı 2017 | 08866 |

Varsa `StorePID.exe` başarıyla döndürür ürün anahtarı geçerli bir `%ERRORLEVEL%` 0. Hatayla karşılaştığında hata koşulu bağlı olarak aşağıdaki kodlarından birini döndürür:

| Hata                     | Kod |
|---------------------------|------|
| `PID_ACTION_SUCCESS`      | 0    |
| `PID_ACTION_NOTINSTALLED` | 1.    |
| `PID_ACTION_INVALID`      | 2    |
| `PID_ACTION_EXPIRED`      | 3    |
| `PID_ACTION_INUSE`        | 4    |
| `PID_ACTION_FAILURE`      | 5    |
| `PID_ACTION_NOUPGRADE`    | 6    |

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sorun giderme ipuçları için sayfa. Ürün sorunları bize de bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) aracı Visual Studio IDE içinde veya üzerinde bir öneri bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579). Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun. Bize ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio) (gerektiren bir [GitHub](https://github.com/) hesabı).

## <a name="see-also"></a>Ayrıca Bkz.
 * [Visual Studio yükleme](../install/install-visual-studio.md)
 * [Visual Studio çevrimdışı yüklemesini oluşturma](../install/create-an-offline-installation-of-visual-studio.md)