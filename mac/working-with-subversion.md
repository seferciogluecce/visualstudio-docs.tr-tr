---
title: Subversion ile çalışma
description: Subversion, Mac için Visual Studio kullanarak
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 2400ED9C-6236-4C0A-A3AB-9D7CBE1F0CF4
ms.openlocfilehash: 81c33d426989f9bab3216802aa4e815228e1e82a
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42624184"
---
# <a name="working-with-subversion"></a>Subversion ile çalışma

Subversion tek ana verilerin bir kopyasını merkezi denetlemenizi sağlayan merkezi sürüm denetim sistemidir. Aksine, Git, Subversion deposu denetimi deponun tamamı kopyalama değil, yalnızca o noktasında bir anlık görüntüsünü alır.

Subversion, kullanıcının aynı anda aynı Havuzda çalışmasına izin vermek için bir kopyalama-değiştirme-merge modeli kullanır. Başka bir deyişle, her kullanıcı bunlar birbirinden bağımsız olarak çalıştığı merkezi veri yerel ya da çalışır durumda bir kopyasını oluşturur. Değişiklikleri kopyaları kullanıcılara kronolojik bir biçimde birleştirilir.

Örneğin, kullanıcı A ve B kullanıcısına bir kopyasından uzak depoya ve her Değiştir dosyaları kullanıma olduğunu düşünün. Kullanıcı A, değişikliklerin tamamlanır ve Uzaktan kaydeder. Kullanıcı B işlerini işlemeler önce değişikliklerle birleştirme kullanıcı A'ın değişiklikler uzak, kendi çalışma kopyası güncelleştirmelisiniz.

Aşağıdaki bölümlerde nasıl Subversion Visual Studio'da sürüm denetimi için Mac için kullanılabileceğini keşfedin

Aşağıdaki görüntüde, sürüm denetimi menü öğesi tarafından Mac için Visual Studio tarafından sağlanan seçenekleri gösterir:

![Sürüm denetimi menü öğeleri](media/version-control-svnVersionControlMenu.png)

## <a name="checkout"></a>Kullanıma alma...

Uzak bir Subversion depo kullanmaya başlamadan önce yerel makinenizde bu dizine çalışan bir kopyasını oluşturmak için depoya göz atın.

Kullanma hakkında bilgi edinmek için **kullanıma alma** Mac için Visual Studio özelliği, adımları [bir Subversion deposu ayarlama](set-up-subversion-repository.md) bölümü.

## <a name="update-solution"></a>Güncelleştirme çözümü

Uzak bir depo kullanırken, diğer kullanıcılar dosyaları, eski çalışma kopyanıza yapmadan değiştiriliyor olabilir olduğunu unutmamak önemlidir. Çakışma olasılığına çalışma başlatılmadan önce ve gerçekleştirmeden önce depodan değişiklikleri çözümünüze çekmek için her zaman önerilir. Değişiklikleri çıkarmak için seçin **sürüm denetimi > güncelleştirme çözümünü** menü öğesi.

## <a name="review-solution-and-commit"></a>Gözden geçirme çözüm ve işleme

Dosyalardaki değişiklikler gözden geçirmek için değişiklikleri, sorumluyu günlük kullanın ve aşağıdaki görüntüde gösterildiği gibi her belge sekmelerinde birleştirme:

![Sürüm denetimi sekmeleri](media/version-control-vcTabs.png)

Göz atarak bir projedeki tüm değişiklikleri gözden **sürüm denetimi > İnceleme çözüm ve işleme** menü öğesi:

![Çözümü gözden geçirin](media/version-control-vcStatus.png)

Bu, tüm değişiklikleri geri al, düzeltme eki oluşturma seçeneğine sahip bir proje her dosyanın görüntüleme izin verir veya işleyin.

Dosya uzak depoya kaydetmeye işleme basın..., bir işleme iletisi girin ve Kaydet düğmesi ile onaylayın:


![Dosya işleniyor](media/version-control-svnCommit.png)

Bu değişiklikler burada tüm değişiklikler yeni bir düzeltme oluşturdukları depoya gönderir.
