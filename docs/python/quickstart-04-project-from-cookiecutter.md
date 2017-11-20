---
title: "Hızlı Başlangıç: Visual Studio'da Cookiecutter şablondan bir Python projeleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7bbb71c-fa07-42e8-bef9-0b9cf6dd628a
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: a877ea77a854659372bfc73b9ef85bc8c81d3be4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="quickstart-create-a-project-from-a-cookiecutter-template"></a>Hızlı Başlangıç: Proje Cookiecutter Şablondan Oluştur

Seçtiğiniz sonra [Python desteği Visual Studio 2017 yüklü](installation.md), GitHub için yayımlanan birçok bir Cookiecutter şablondan yeni bir proje oluşturmak kolaydır. [Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) şablonları bulmak, şablon seçenekleri giriş ve projeler ve dosyaları oluşturmak için bir grafik kullanıcı arabirimi sağlar. Visual Studio 2017 ile eklemiştir ve Visual Studio'nun önceki sürümleri ayrı olarak yüklenebilir.

1. Bu Hızlı Başlangıç için önce burada gösterilen Cookiecutter şablonu için gereken Python paketlerini içerir Anaconda3 Python dağıtımı yükleyin. Visual Studio yükleyicisi, belirleyin **Değiştir**, seçeneklerini genişletin **Python geliştirme** sağ tarafında ve select "Anaconda3" (32 bit veya 64 bit). Yükleme Internet hızınıza bağlı olarak biraz zaman alabilir ancak bu gerekli paketleri yüklemek için en basit yolu olduğunu unutmayın.

1. Visual Studio'yu başlatın.

1. Seçin **Dosya > Yeni > Cookiecutter gelen...** . Bu komut, burada şablonları göz atabilirsiniz Visual Studio'da bir pencere açılır. 

    ![Cookiecutter şablondan yeni proje](media/projects-from-cookiecutter1.png)

1. "Microsoft/python-sklearn-sınıflandırıcı-cookiecutter" şablonu seçili sonra seçin **sonraki**. (İşlemi ilk kez Cookiecutter kullandığınızda birkaç dakika sürebilir.)

1. Sonraki adımda, yeni projede için bir konum ayarlamak **oluşturmak için** alan sonra select **oluşturma**.

    ![İkinci adım Cookiecutter kullanarak, proje özelliklerini ayarlama](media/projects-from-cookiecutter2.png)

1. İşlem tamamlandığında, "Dosyaları başarıyla oluşturuldu." iletisini görürsünüz Komutu seçin **Çözüm Gezgini'nde açık** projeyi açın.

1. CTRL + F5 tuşuna basın veya seçin **hata ayıklama > hata ayıklama olmadan Başlat** programı çalıştırmak için. 

    ![Python sklearn sınıflandırıcı cookiecutter şablon proje çıktısı](media/projects-from-cookiecutter4.png)


## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışma](vs-tutorial-01-01.md)

## <a name="see-also"></a>Ayrıca Bkz.

- [Cookiecutter uzantısını kullanarak](cookiecutter.md)
- [Varolan bir Python yorumlayıcısı için bir ortam oluşturma](python-environments.md#creating-an-environment-for-an-existing-interpreter).
- [Python desteği Visual Studio 2015 ve daha önce yükleme](installation.md).
- [Konumları yüklemek](installation.md#install-locations).