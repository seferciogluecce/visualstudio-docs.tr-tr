---
title: 'Nasıl yapılır: Şeritte Geliştirici sekmesini gösterme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], tabs
- Developer tab [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fea1b0fa804726cb43bdc5b6d866ceedc186924c
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43780554"
---
# <a name="how-to-show-the-developer-tab-on-the-ribbon"></a>Nasıl yapılır: Şeritte Geliştirici sekmesini gösterme
  Erişim için **Geliştirici** sekmesini bir Office uygulamasının Şerit üzerinde varsayılan olarak görünmez sekmenin gösterileceği şekilde yapılandırmanız gerekir. Örneğin, eklemek istediğiniz sekmenin Göster gerekir bir <xref:Microsoft.Office.Tools.Word.GroupContentControl> Word için belge düzeyi özelleştirmeyi için.  
  
> [!NOTE]  
>  Bu kılavuz, Office 2010 veya yalnızca sonraki uygulamalar için geçerlidir. Bu sekmeyi 2007 Microsoft Office System'da göstermek istiyorsanız, bu konunun aşağıdaki sürümü görmek [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](http://msdn.microsoft.com/library/bb608625(v=vs.90).aspx).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
> [!NOTE]  
>  Erişim yok bir **Geliştirici** sekmesi.  
  
## <a name="to-show-the-developer-tab"></a>Geliştirici sekmesini göstermek için  
  
1.  Bu konu tarafından desteklenen Office uygulamalarından herhangi birini başlatın. Bkz: **geçerlidir:** bu konunun önceki kısımlarında Not.  
  
2.  Üzerinde **dosya** sekmesini, **seçenekleri** düğmesi.  
  
     Aşağıdaki şekil gösterir **dosya** sekmesi ve **seçenekleri** Office 2010'daki düğmesi.  
  
     ![Dosya seçme, Outlook 2010'daki Seçenekler](../vsto/media/vsto-office-file-tab.png "dosyası seçme, Outlook 2010'da seçenekleri")  
  
     Aşağıdaki şekil gösterir **dosya** Office 2013'te sekmesi.  
  
     ![Outlook 2013'te dosya sekmesi](../vsto/media/vsto-office2013-filetab.png "Outlook 2013'te dosya sekmesi")  
  
     Aşağıdaki şekil gösterir **seçenekleri** Office 2013'teki düğmesi.  
  
     ![Outlook 2013 Preview'teki Seçenekler düğmesi](../vsto/media/vsto-office2013-optionsbutton.png "Outlook 2013 Preview'teki Seçenekler düğmesi")  
  
3.  İçinde _ApplicationName_**seçenekleri** iletişim kutusunda **Şeridi Özelleştir** düğmesi.  
  
     Aşağıdaki şekil gösterir **seçenekleri** iletişim kutusu ve **Şeridi Özelleştir** Excel 2010'daki düğmesi. Bu düğmenin konumu bu konunun üstündeki "Aşağıdakilere Uygulanır" bölümünde listelenen tüm diğer uygulamalarda benzerdir.  
  
     ![Şeridi Özelleştir düğmesi](../vsto/media/vsto-office2010-customizeribbonbutton.png "Şeridi Özelleştir düğmesi")  
  
4.  Ana sekmeler listesinde seçin **Geliştirici** onay kutusu.  
  
     Aşağıdaki şekil gösterir **Geliştirici** Word 2010 onay kutusuna ve [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]. Bu onay kutusunun konumu bu konunun üstündeki "Aşağıdakilere Uygulanır" bölümünde listelenen tüm diğer uygulamalarda benzerdir.  
  
     ![Word Seçenekleri iletişim kutusunda Geliştirici onay kutusu](../vsto/media/vsto-office2010-developercheckbox.png "Geliştirici onay kutusuna Word Seçenekleri iletişim kutusu")  
  
5.  Seçin **Tamam** kapatmak için düğme **seçenekleri** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)  
  
  