---
title: Visual Studio araç kutusu penceresi
ms.date: 01/18/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.toolbox.general
- vs.toolbox
helpviewer_keywords:
- Toolbox [Visual Studio]
- custom controls [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5772445bcfb201aef9a4248a77e28193429c9528
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924401"
---
# <a name="toolbox"></a>Araç Kutusu

**Araç kutusu** penceresi Visual Studio projelerine ekleyebileceğiniz denetimler görüntüler. Araç kutusunu açmak için seçin **araç kutusu** üzerinde **görünümü** menüsü.

![Araç penceresi](media/toolbox.png)

Kullanmakta olduğunuz ve yeniden boyutlandırma ve yerleştirmenize Tasarımcı yüzeyine başka denetimler sürükleyip bırakabilirsiniz.

Araç kutusu, Tasarımcı görünümü bir XAML dosyasının gibi tasarımcı görünümleri ile birlikte görüntülenir. **Araç kutusu** geçerli Tasarımcısı'nda kullanılabilen denetimleri görüntüler. İçinde arama yapabilirsiniz **araç kutusu** öğelere daha fazla filtrelemek için.

> [!NOTE]
> Bazı proje türleri için **araç kutusu** öğeler gösterilmeyebilir.

Projenizi denetimleri araç kutusunda görünür kümesini de etkiler hedefleyen .NET Framework sürümü. Projenizi projenin özellik sayfalarından farklı bir .NET Framework sürümünü hedefleyecek şekilde ayarlayabilirsiniz. ' Nde proje düğümüne seçin **Çözüm Gezgini**ve ardından menü çubuğunda, **proje** > **projectname özellikleri**. Üzerinde **uygulama** için sekmesinde, kullanın **hedef Framework'ü** açılır.

## <a name="manage-the-toolbox-window-and-its-controls"></a>Araç kutusu penceresini ve denetimlerini yönetme

Varsayılan olarak **araç kutusu** Visual Studio IDE'nin sol tarafında daraltılmış ve imleci üzerine taşındığında görüntülenir. Sabitleyebilmeniz için **araç kutusu** (tıklayarak **PIN** , araç çubuğundaki simgesini) açık kalması taşıdığınızda imleç. Ayrıca kaldıracağınızı **araç kutusu** penceresi ve ekran üzerinde herhangi bir yere sürükleyin. Yerleştirme, çıkarmaya gizleme ve **araç kutusu** alt araç çubuğunun sağ tıklayıp seçeneklerden birini seçerek.

Öğeleri yeniden düzenleyebilir bir **araç kutusu** sekmesinde veya bağlam menüsünde aşağıdaki komutları kullanarak özel sekme ve öğeleri ekleyin:

- **Öğeyi yeniden adlandır** -seçili öğeyi yeniden adlandırır.

- **Tümünü Göster** -tüm olası denetimleri (geçerli Tasarımcı için geçerli olanları değil) gösterir.

- **Liste görünümü** -denetimleri dikey listesini gösterir. Denetimleri yatay olarak işaretlenmemişse, görünür.

- **Seç öğeleri** -açılır **araç kutusu öğelerini Seç** iletişim kutusunda görünen öğeler belirtebilirsiniz böylece **araç kutusu**. Göstermek veya seçerek ya da onay kutusunu temizleyerek bir öğeyi gizler.

- **Öğeleri alfabetik olarak Sırala** -öğeleri ada göre sıralar.

- **Araç çubuğunu sıfırlama** -varsayılan yükler **araç kutusu** ayarları ve öğeleri.

- **Sekme Ekle** -yeni bir ekler **araç kutusu** sekmesi.

- **Yukarı Taşı** -seçili öğeyi yukarı taşır.

- **Aşağı Taşı** -seçili öğeyi aşağı taşır.

## <a name="create-and-distribute-custom-toolbox-controls"></a>Oluşturma ve özel araç kutusu denetimleri dağıtma

Oluşturabileceğiniz özel **araç kutusu** denetimleri, temel alan bir proje şablonu ile başlayan [Windows Presentation Foundation](../../extensibility/creating-a-wpf-toolbox-control.md) veya [Windows Forms](../../extensibility/creating-a-windows-forms-toolbox-control.md). Ardından, özel denetim için kodunuza dağıtmak veya kullanarak Web'de Yayımlama [araç kutusu denetimleri yükleyici](http://download.microsoft.com/download/8/3/6/836657BD-9CCB-4ED4-B9D2-FB769473B284/TCI_whitepaper.docx).

## <a name="help-on-toolbox-tabs"></a>Araç kutusu sekmelerindeki Yardım

Kullanılabilir bazıları hakkında daha fazla bilgi aşağıdaki konularda **araç kutusu** sekmeleri:

- [Araç Kutusu, Veri Sekmesi](../../ide/reference/toolbox-data-tab.md)
- [Araç Kutusu, Bileşenler Sekmesi](../../ide/reference/toolbox-components-tab.md)
- [Araç Kutusu, HTML Sekmesi](../../ide/reference/toolbox-html-tab.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Araç kutusu öğelerini, WPF bileşenlerini seçme](choose-toolbox-items-wpf-components.md)