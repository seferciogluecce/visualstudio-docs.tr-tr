---
title: "Başvuru öğesi (Visual Studio şablonları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#Reference
helpviewer_keywords:
- Reference element [Visual Studio templates]
- <Reference> element [Visual Studio templates]
ms.assetid: 852772ea-c324-42e9-8c8a-6d565414a109
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2f25b39178141f3e3a40899645a0a1af6c8417ab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="reference-element-visual-studio-templates"></a>Reference Öğesi (Visual Studio Şablonları)
Öğe bir projeye eklendiğinde eklemek için derleme başvurusu belirtir.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Başvuruları >  
 \<Başvuru >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Reference>  
    <Assembly> ... </Assembly>  
</Reference>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümlerde öznitelik, alt öğeler ve üst öğeler açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Derleme](../extensibility/assembly-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Bu derleme başvurusu projelerine ekleme için şablonu kullanan bir derleme hakkındaki bilgileri belirtir. Mutlaka bir tane `Assembly` öğesinde her `Reference` öğesi.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Başvuruları](../extensibility/references-element-visual-studio-templates.md)|Şablon projelerine ekler derleme başvurularını gruplandırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `Reference`gerekli bir alt öğesidir `References`.  
  
 `Reference` Ve `References` öğeleri sahip .vstemplate dosyaları yalnızca kullanılabilir bir `Type` öznitelik değerini `Item`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek gösterilmektedir `TemplateContent` bir öğe şablonu öğesidir. Bu XML System.dll ve System.Data.dll derleme başvurularını ekler.  
  
```  
<TemplateContent>  
    <References>  
        <Reference>  
            <Assembly>  
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>  
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
    </References>  
    ...  
</TemplateContent>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)