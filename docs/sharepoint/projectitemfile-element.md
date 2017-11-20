---
title: "Projectıtemfile öğesi | Microsoft Docs"
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
helpviewer_keywords: ProjectItemFile element
ms.assetid: 68d44d31-625a-4f02-b998-463ac0ffb2ef
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 023d2f64dc3f05d518add1cd4bf6c3415f435985
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="projectitemfile-element"></a>ProjectItemFile Öğesi
  SharePoint için dağıtıldığında ile proje öğesi eklemek için özellik öğesi dosyası gibi bir SharePoint dosyayı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProjectItemFile Source = "Name of the file"  
    Target = "Deployment path of the file"  
    Type = "Type of deployment for the file" />  
```  
  
## <a name="type"></a>Tür  
 **ProjectItemFileType**  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**Kaynak**|Gerekli **xs: String** özniteliği.<br /><br /> Proje öğesi ile dağıtmak için dosyanın adı.|  
|**Hedef**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> Dosya SharePoint üzerinde dağıtım kök klasörüne görelidir dağıtılacağı yolu. Dağıtım kök klasörü tarafından belirtilen dağıtım türü tarafından belirlenir **türü** özniteliği. Varsa **hedef** özniteliği belirtilmezse, belirtilen ada sahip bir klasöre dosya dağıtılacak **kaynak** özniteliği.<br /><br /> Açıklamaları için daha fazla bilgi için bkz **dağıtım yolu** ve **dağıtım kök** SharePoint özelliklerini proje öğelerinde [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md).|  
|**Türü**|Gerekli **xs: String** özniteliği.<br /><br /> Dosyası için dağıtım türü. Olası değerler hakkında daha fazla bilgi için açıklama için bkz. **dağıtım türü** SharePoint Proje öğeleri özelliği [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Dosyaları](../sharepoint/files-element.md)|SharePoint için dağıtıldığında ile SharePoint proje öğesi eklenecek dosyaları belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle başvuru SharePoint dosyaları **Projectıtemfile** öğeleri özellik öğesi dosyaları (Elements.xml), liste tanımları (Schema.xml) için şema dosyaları ve Web Bölümleri (.webpart) için Web Bölümü tanım dosyalarını içerir.  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint proje öğesi şema başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  