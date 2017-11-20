---
title: "Nasıl yapılır: bir kısayol menü öğesini SharePoint projelerine ekleme | Microsoft Docs"
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
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
ms.assetid: bb251fe9-f1bf-4ddd-9359-4b7f78fbd50f
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0e327a716fc77dbc8dd3515c092dcd32c2da5158
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-shortcut-menu-item-to-sharepoint-projects"></a>Nasıl yapılır: Bir Kısayol Menü Öğesini SharePoint Projelerine Ekleme
  Herhangi bir SharePoint projesine bir kısayol menü öğesi ekleyebilirsiniz. Bir kullanıcı bir proje düğümünde tıklattığında menü öğesi görünür **Çözüm Gezgini**.  
  
 Aşağıdaki adımlar, bir proje uzantısı zaten oluşturduğunuzu varsayalım. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
### <a name="to-add-a-shortcut-menu-item-to-sharepoint-projects"></a>Bir kısayol menü öğesini SharePoint projelerine ekleme  
  
1.  İçinde <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> yöntemi, <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> uygulaması, tanıtıcı <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> olayı *projectService* parametresi.  
  
2.  Olay işleyicisi için <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> olay, yeni bir ekleme <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> nesnesini <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectMenuItemsRequestedEventArgs.ActionMenuItems%2A> veya <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectMenuItemsRequestedEventArgs.AddMenuItems%2A> olay bağımsız değişken parametre koleksiyonu.  
  
3.  İçinde <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> yeni için olay işleyicisini <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> nesne, bir kullanıcı kısayol menü öğesi tıkladığında yürütmek istediğiniz görevleri gerçekleştirin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde, SharePoint Proje düğümler bir kısayol menü öğesi eklemek gösterilmiştir **Çözüm Gezgini**. Kullanıcı bir proje düğümüne sağ tıklatır ve tıklar **yazma iletisi çıkış penceresine** menü öğesi, Visual Studio içinde bir ileti görüntüler **çıkış** penceresi. Bu örnek iletiyi görüntülemek için SharePoint Proje hizmeti kullanır. Daha fazla bilgi için bkz: [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md).  
  
 [!code-csharp[SPExtensibility.ProjectExtension.Menu#1](../sharepoint/codesnippet/CSharp/projectmenu/extension/projectitemextensionmenu.cs#1)]
 [!code-vb[SPExtensibility.ProjectExtension.Menu#1](../sharepoint/codesnippet/VisualBasic/projectmenu/extension/projectitemextensionmenu.vb#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek, bir sınıf kitaplığı projesi aşağıdaki derlemeler başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Uzantısını dağıtma  
 Uzantıyı dağıtmak için oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint projelerini genişletme](../sharepoint/extending-sharepoint-projects.md)   
 [Nasıl yapılır: bir SharePoint proje uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [Nasıl yapılır: SharePoint projelerine özellik ekleme](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)  
  
  