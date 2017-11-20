---
title: "Nasıl yapılır: dağıtma ve bir SharePoint çözümünü yerel bir SharePoint sitesine yayımlama | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, deploying
ms.assetid: 73f8d6a9-4c64-4bba-ae0e-9474baf8df26
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4959334c9d6949e199ad18934e69ea46e1172b55
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site"></a>Nasıl yapılır: Bir SharePoint Çözümünü Yerel bir SharePoint Sitesine Dağıtma ve Yayımlama
  Dağıtabilir veya SharePoint çözümleri geliştirme bilgisayarınızda yerel bir SharePoint server yayımlama. Dağıtım işlemi .wsp dosyasını SharePoint sunucusuna kopyalar, çözüm yükler ve özellikleri etkinleştirir. Yayımlama işlemi yalnızca .wsp dosyasını SharePoint sunucusuna kopyalar ve yükler. SharePoint'te etkinleştirmek için el ile etkinleştirmeniz gerekir.  
  
## <a name="to-deploy-a-sharepoint-solution-to-the-local-sharepoint-server"></a>Bir SharePoint çözümünü yerel SharePoint sunucusuna dağıtmak için  
  
1.  İçinde **Çözüm Gezgini**, dağıtmak istediğiniz projesini seçin.  
  
2.  Menü çubuğunda seçin **yapı**, **çözümü Dağıt**.  
  
     .Wsp dosyası oluşturulur ve yerel SharePoint sunucu üzerinde yüklü. Ayrıca, özellikleri etkinleştirilir.  
  
## <a name="to-publish-a-sharepoint-solution-to-a-local-sharepoint-server"></a>Bir SharePoint çözümünü yerel SharePoint sunucusuna yayımlamak için  
  
1.  İçinde **Çözüm Gezgini**, yayımlama ve ardından istediğiniz SharePoint proje için kısayol menüsünü açın **Yayımla**.  
  
2.  İçinde **Yayımla** iletişim kutusunda, seçin **dosya sistemi Yayımla** seçenek düğmesi.  
  
3.  İçinde **hedef konumu** metin kutusunda, yerel bir yol girin ve ardından **Yayımla** düğmesi.  
  
     Visual Studio'da yayımlama ilerleme görünür **çıkış** penceresi. İşlem tamamlandığında, çözüm (.wsp) dosyasını yerel SharePoint sunucusuna yüklenir. Ancak, bunu hala SharePoint'te kullanılacak etkinleştirilmesi gerekir. Çözüm dosyası zaten varsa, bir hata oluşur ve mevcut dosyanın üzerine yazmak isteyip istemediğinizi sorar. Paket yükseltme hakkında daha fazla bilgi için Uzak paketlerinde yükseltme bölümüne bakın [nasıl yapılır: dağıtma, yayımlama ve uzak bir sunucudaki SharePoint çözümlerini yükseltme](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: dağıtma, yayımlama ve uzak bir sunucudaki SharePoint çözümlerini yükseltme](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)   
 [SharePoint çözüm paketleri oluşturma](../sharepoint/creating-sharepoint-solution-packages.md)   
 [Nasıl yapılır: bir SharePoint çözüm paketini özelleştirme](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)   
 [Nasıl yapılır: ekleme ve kaldırma özellikler ve öğeler bir paket için paket Tasarımcısını kullanarak](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)  
  
  