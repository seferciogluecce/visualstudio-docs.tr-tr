---
title: "SafeControl öğesi | Microsoft Docs"
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
helpviewer_keywords: SafeControl element
ms.assetid: e7c61749-fc73-412c-be30-4af5ff2a9fd2
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8d9651c320e574c8db9fcafcb6e98f13e45eac1d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="safecontrol-element"></a>SafeControl Öğesi
  Bir ASPX denetimi veya SharePoint sitesinde herhangi bir ASPX sayfasında erişmek herhangi bir kullanıcı için güvenli olarak tasarlanmış Web bölümünü temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<SafeControl Assembly = "Name of assembly that contains the safe control"  
    IsSafe = "true/false"  
    IsSafeAgainstScript = "true/false"  
    Name = "Name of this safe control entry"  
    Namespace = "Namespace of the safe control"  
    TypeName = "Type of the safe control" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**Derleme**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> ASPX denetimi veya Web bölümünün tanımlandığı derleme adı. Varsayılan olarak, bu öznitelik kullanır **$SharePoint.Project.AssemblyFullName$** parametredir derleme adı. Daha fazla bilgi için bkz: [değiştirilebilir parametreler](../sharepoint/replaceable-parameters.md).|  
|**IsSafe**|İsteğe bağlı **xs:boolean** özniteliği.<br /><br /> ASPX denetim veya Web Bölümü güvenilmeyen kullanıcıların erişim güvenli olup olmadığını belirtir.|  
|**IsSafeAgainstScript**|İsteğe bağlı **xs:boolean** özniteliği.<br /><br /> Güvenilmeyen kullanıcıların görüntüleyebilir veya ASPX denetim veya Web Bölümü özelliklerini Düzenle olup olmadığını belirtir.|  
|**Ad**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> Bu güvenli denetim girdisi koleksiyonundaki adı.|  
|**Namespace**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> Ad alanı ASPX denetim ya da Web Bölümü.|  
|**TypeName**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> ASPX denetim veya Web Bölümü türü adı.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[SafeControls](../sharepoint/safecontrols-element.md)|ASPX denetimleri ve SharePoint sitesindeki herhangi bir ASPX sayfasında erişmek herhangi bir kullanıcı için güvenli olarak tasarlanmış Web Bölümleri koleksiyonunu temsil eder.|  
  
## <a name="remarks"></a>Açıklamalar  
 Güvenli denetimler hakkında daha fazla bilgi için bkz: [sağlama paketleme ve dağıtım bilgileri proje öğelerinde](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint proje öğesi şema başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Paketleme ve dağıtım bilgileri proje öğeleri sağlama](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
  