---
title: Mac için Visual Studio'yu yükleyin
description: Mac ve platformlar arası geliştirme için gereken ek bileşenleri için Visual Studio yükleme hakkında yönergeler.
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.openlocfilehash: f6ec6a446b68c848885e2c08804bc49a0cf1941b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49934619"
---
# <a name="setup-and-install-visual-studio-for-mac"></a>Kurulum ve Mac için Visual Studio yükleme

## <a name="setup"></a>Kurulum

Başlangıç yerel geliştirme için Visual Studio Mac için orada karşıdan yüklerken platformlar arası birkaç şey yükleyin ve hazırlık ayarlanan uygulamalardır.

Visual Studio'da iOS ile çalışmak için şu bilgilere ihtiyacınız vardır:

* bir Mac ile macOS Sierra 10.12 veya üzeri
* Xcode 8.3 veya üzeri. En son kararlı sürüme genellikle önerilir.
* Bir Apple kimliği Bir Apple kimliği yoksa, yeni bir hesap oluşturabilirsiniz https://appleid.apple.com. Yükleme ve Xcode ile imzalamak için bir Apple Kimliği gereklidir.

## <a name="install"></a>Yükleme

1. Mac için Visual Studio'yu indirin [https://visualstudio.microsoft.com/](https://visualstudio.microsoft.com/)

2. Yükleyici paketini indirdikten sonra tıklayın **VisualStudioInstaller.dmg** yükleyici bağlamanız ve ardından çalıştırın logoyu tıklatarak tarafından aşağıdaki görüntüde gösterildiği gibi dosya:

   ![Yükleyici iletişim](media/installer-image1.png)

3. Uyarı iletişim kutusu aşağıdaki görüntüye benzer istenebilir. Bu durumda, tıklayın **açık**:

   ![Uyarı iletişim kutusu](media/installer-image2.png)

4. Yükleyici hangi bileşenlerin yüklenmesi veya güncelleştirilmesi gereken doğrulamak için sisteminizi denetler:

   ![Sisteminizi değerlendiriliyor](media/installer-image3.png)

5. Ardından gizlilik ve lisans koşullarını kabul etmek isteyen uyarı iletişim kutusu ile sunulur. Tuşuna **devam** düğmesini koşullarını kabul etmiş olursunuz:

   ![Lisans iletişim](media/installer-image4.png)

6. Yükleyici, eksik olan ve indirilmesi ve yüklenmesi gereken gerekli bileşenlerin listesini gösterir. Burada indirmek istediğiniz ürünleri seçin:

   ![Öğeleri seçin](media/installer-image5.png)

   Tüm platformlara yüklemek istemiyorsanız, yüklemek için hangi platformların karar vermenize yardımcı olması için aşağıdaki kılavuzu kullanın:

   * **Xamarin kullanarak uygulamaları**:
      - Xamarin.Forms – seçin **Android** ve **iOS** platformlar.
      - iOS yalnızca – seçin **iOS** Platformu (yüklemeniz gerekecek Not [ **Xcode**](https://developer.apple.com/xcode/)).
      - Android yalnızca – seçin **Android** Platformu (ilgili bağımlılıkları da seçmeniz gerekir. Not).
      - Mac yalnızca – seçin **macOS** Platformu (yüklemeniz gerekecek Not [ **Xcode**](https://developer.apple.com/xcode/)).
      - Tam olarak platformlar arası Xamarin uygulamaları – seçin **Android**, **iOS**, ve **macOS** platformlar.
   * **.NET core uygulamaları** – Select **.NET Core** platform.
   * **ASP.NET Core Web uygulamaları** – Select **.NET Core** platform.
   * **Platformlar arası Unity oyun geliştirme** – Mac için Visual Studio dışında yüklenecek hiçbir ek platform gerekiyor Başvurmak [Unity Kurulum Kılavuzu](setup-vsmac-tools-unity.md) Unity uzantının yüklenmesi hakkında daha fazla bilgi.

   Bu yükleme ekranı, sürüm ve tek tek her bileşen boyutunu görüntüler. (.NET Core için) yüklemeleri ek paketler (Android için) söz konusu bileşen için bağımlılıkların bir listesini görüntülemek için bkz her bileşene tıklayın ya da (iOS ve macOS) gerekli ek uygulamaları görüntüleyin:

   ![Android ek bağımlılıklar](media/installer-image6.png)

7. Seçiminizle memnun olduğunuzda seçin **yükleme ve güncelleştirme** yükleme işlemini başlatmak için düğme.

8. Yükleyici, indirme başlar ve yükleme işlemi, seçilen öğeler:

   ![Yükleme başlatılıyor](media/installer-image7.png)

   ![Xamarin.Mac indiriliyor](media/installer-image8.png)

   ![Yükleme sonlandırılıyor](media/installer-image9.png)

9. Yüklemeyi tamamlamak için gereken tek tek bileşenler için gerekli izinlere yükseltmesine istenebilir. Yükleme işlemine devam etmek için yönetici kimlik bilgilerinizi buraya girin:

   ![Yükleyici ile devam etmek için izinleri girin](media/installer-image10.png)

10. Yükleme başarılı olduktan sonra tuşlarına basarak Visual Studio'da uygulamalarınızı geliştirmeye başlayabilirsiniz **Başlat**:

    ![Visual Studio'yu Aç](media/installer-image11.png)

> [!NOTE]
> Yüklemeyin bir platform veya aracı özgün yükleme sırasında (bunu #6. adımda seçimini tarafından) seçerseniz, çalıştırmalısınız [yükleyici](https://visualstudio.microsoft.com/vs/) yeniden bileşen daha sonra eklemek istiyorsanız.


## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>Visual Studio Mac için bir güvenlik duvarı veya proxy sunucusunun arkasına yükleme

Güvenlik duvarının arkasında Mac için Visual Studio'yu yüklemek için belirli uç noktaları, yazılım güncelleştirmeleri ve gerekli araçları indirmeye izin ver için erişilebilir yapılması gerekir.

Şu konumlardan erişime izin vermek için ağ yapılandırın:

* [Visual Studio uç noktaları](/visualstudio/install/install-visual-studio-behind-a-firewall-or-proxy-server)

## <a name="next-steps"></a>Sonraki Adımlar

Mac için Visual Studio yükleme, uygulamalarınız için kod yazmaya olanak tanır. Aşağıdaki kılavuzlarda yazma ve projelerinizi dağıtma sonraki adımlarda size rehberlik sağlanmaktadır.

### <a name="ios"></a>iOS

1. [Hello, iOS](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/)
2. [Cihaz sağlama](https://developer.xamarin.com/guides/ios/getting_started/installation/device_provisioning)(cihazda uygulamanızı çalıştırmak için).


### <a name="android"></a>Android

1. [Xamarin Android SDK Yöneticisi'ni kullanma](https://developer.xamarin.com/guides/android/getting_started/installation/android-sdk/?ide=xs)
2. [Android SDK Emulator](https://developer.xamarin.com/guides/android/getting_started/installation/android-emulator/)
4. [Cihazı Dağıtım için Ayarlama](https://developer.xamarin.com/guides/android/getting_started/installation/set_up_device_for_development/)

### <a name="net-core-apps-aspnet-core-web-apps-unity-game-development"></a>.NET core uygulamaları, ASP.NET Core web uygulamaları, Unity oyun geliştirme

Diğer iş yükleri için başvurmak [iş yükleri](workloads.md) sayfası.
