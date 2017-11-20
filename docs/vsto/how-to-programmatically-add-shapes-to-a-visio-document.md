---
title: "Nasıl yapılır: Visio belgesine program aracılığıyla şekiller ekleme | Microsoft Docs"
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
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
ms.assetid: 29613237-88f5-41a7-9e13-cfa177f41221
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 39843950cb592aa40b11e098f62018a4dc6e2983
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>Nasıl yapılır: Visio Belgesine Program Aracılığıyla Şekiller Ekleme
  Bir şablon asıl alma ve etkin sayfada şekilleri bırakarak Microsoft Office Visio belgesine şekiller ekleyebilirsiniz.  
  
 Daha fazla bilgi için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) yöntemi, [Microsoft.Office.Interop.Visio.Application.ActivePage](http://msdn.microsoft.com/library/office/ff765484.aspx) özelliği ve [Microsoft.Office.Interop.Visio.Page.Drop](http://msdn.microsoft.com/library/office/ff765054.aspx) yöntemi.  
  
## <a name="adding-shapes-to-a-visio-document"></a>Visio belgesine şekilleri ekleme  
  
#### <a name="to-add-shapes-to-a-visio-document"></a>Visio belgesine şekilleri ekleme  
  
-   Belge etkinken, asıl Documents.Masters koleksiyonundan almak ve şekiller etkin belgede bırakın. Dizin veya ana ad kullanarak bir ana alabilirsiniz.  
  
     Aşağıdaki kod örneğinde boş bir Visio belgesi oluşturur ve onunla açılır **temel şekillerin** kalıbı yuvalanmış. Kod birkaç şekiller alır ve bunları etkin sayfada bırakır.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Visio şekilleri ile çalışma](../vsto/working-with-visio-shapes.md)   
 [Nasıl yapılır: program aracılığıyla kopyalama ve yapıştırma şekiller Visio belgelerinde](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)  
  
  