---
title: UML Genişletilebilirlik Modellemesi için API Başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML - extending
- UML API
- UML model, API
ms.assetid: 2b2ffe93-c358-4d28-a5e5-3d0474629b58
caps.latest.revision: 11
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: 7109c85781c6a69e9b2db9f1f8734b9f2d1efc46
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49301342"
---
# <a name="api-reference-for-uml-modeling-extensibility"></a>UML Genişletilebilirlik Modellemesi için API Başvurusu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio ile oluşturma modelleri okumak ve değiştirmek için program kodu yazabilirsiniz. API Başvurusu, bu konuda yardımcı olacak sınıflar hakkında bilgi sağlar. Daha fazla bilgi için görev odaklı altındaki konulara bakın [genişletmek UML modellerini ve diyagramları](../modeling/extend-uml-models-and-diagrams.md). Visual Studio'nun hangi sürümlerinin UML modellerini desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="assemblies"></a>Derlemeleri  
  
|Derleme|Bunu yapmak sağlar|  
|--------------|--------------------------------|  
|Microsoft.VisualStudio.UML.Interfaces.dll'yi|-Okuyun ve IUseCase IAssociation ve benzeri gibi model öğelerini değiştirin.<br />-Öğeleri arasındaki ilişkileri gidin.<br /><br /> Ad alanları ve türler, UML belirtiminde tanımlanmış karşılık gelir.|  
|Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll|-Yeni örneklerini model öğeleri oluşturma<br />-Erişim ve şekilleri ve diyagramları değiştirin.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [UML modellerini ve diyagramları genişletme](../modeling/extend-uml-models-and-diagrams.md)   
 [Visual Studio için Modelleme SDK'sı için API Başvurusu](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)



