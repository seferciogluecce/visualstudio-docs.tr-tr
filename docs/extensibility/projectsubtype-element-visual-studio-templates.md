---
title: "ProjectSubType öğesi (Visual Studio şablonları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#ProjectSubType
helpviewer_keywords:
- ProjectSubType element [Visual Studio Templates]
- <ProjectSubType> element [Visual Studio Templates]
ms.assetid: f6895cd4-3e95-4f0e-aa9e-8c7750f46ed4
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c42cfdd72207fdca7fbbe0b17b0f96f20066f098
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="projectsubtype-element-visual-studio-templates"></a>ProjectSubType Öğesi (Visual Studio Şablonları)
Belirtilen değer kategorisidir içine şablon sınıflandırır `ProjectType` öğesi.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<ProjectSubType >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProjectSubType> SubType </ProjectSubType>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümlerde öznitelik, alt öğeler ve üst öğeler açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Şablon kategorilere ayırır ve nasıl ya da görüntüler tanımlar **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
 Bu değer, şablon kategorisidir belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 `ProjectSubType`bir isteğe bağlı bir alt öğenin `TemplateData`.  
  
 `ProjectSubType` Öğesi bir alt kategori sağlar [ProjectType](../extensibility/projecttype-element-visual-studio-templates.md) öğesi. Bu değer içerebilir:  
  
-   `SmartDevice-NETCFv1`: Belirtir, şablon hedefleri [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] sürüm 1.0.  
  
-   `SmartDevice-NETCFv2`: Belirleyen tempalate hedefleri [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] sürüm 2.0.  
  
 Bir şablon içeriyorsa bir `ProjectType` değerini bir öğesiyle `Web`, `ProjectSubType` öğesi şablonunun programlama dilini belirtir. Bu öğe aşağıdaki değerlere sahip olabilir:  
  
-   `CSharp`: Belirtir şablon oluşturduğu bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Web projesi veya öğesi.  
  
-   `VisualBasic`: Belirtir şablon oluşturduğu bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Web projesi veya öğesi.  
  
## <a name="example"></a>Örnek  
 Meta veriler için bir proje şablonu için aşağıdaki örnekte bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aygıt uygulama hedefleme [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] sürüm 2.0.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic device template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <ProjectSubType>SmartDevice-NETCFv2</ProjectSubType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [ProjectType öğesi (Visual Studio şablonları)](../extensibility/projecttype-element-visual-studio-templates.md)