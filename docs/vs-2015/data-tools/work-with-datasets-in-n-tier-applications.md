---
title: N katmanlı uygulamalarda veri kümeleriyle çalışmak | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- datasets [Visual Basic], n-tier applications
- multi-tier database applications
- DataSet project [VS n-tier applications]
- distributed applications [VS n-tier applications]
- data [Visual Basic], n-tier applications
- TableAdapters, n-tier applications
- n-tier applications
- tiers, n-tier applications
- typed datasets, n-tier applications
- multiple tier applications
ms.assetid: f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 61f3686488a460ef4c7091521c2165f575e76fa6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694960"
---
# <a name="work-with-datasets-in-n-tier-applications"></a>N katmanlı uygulamalarda veri kümeleriyle çalışma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [n katmanlı uygulamalarda veri kümeleriyle çalışmak](https://docs.microsoft.com/visualstudio/data-tools/work-with-datasets-in-n-tier-applications).  
  
  
N katmanlı veri uygulamaları * olan birden çok mantıksal katmana ayrılmış veri odaklı uygulamaları (veya *katmanları*). Diğer bir deyişle, bir n katmanlı veri uygulaması birden çok proje, veri erişim katmanında, iş mantığı katmanı ve sunu katmanı her kendi projesi içinde ayrılmış bir uygulamadır. Daha fazla bilgi için [N katmanlı veri uygulamalarına genel bakış](../data-tools/n-tier-data-applications-overview.md).  
  
 Türü belirtilmiş datasets ayrı projelere Tableadapter'lar ve veri kümesi sınıfları oluşturulabilir olacak şekilde geliştirilmiştir. Bu hızlı bir şekilde uygulama katmanları ayırmak ve n katmanlı veri uygulamaları oluşturma olanağı sağlar.  
  
 N katmanlı destek türü belirtilmiş veri kümelerinde, n katmanlı bir tasarım uygulaması mimarisi yinelemeli geliştirilmesini sağlar. Ayrıca el ile kod birden fazla projeye ayrı gereksinimini ortadan kaldırır. Veri katmanı kullanarak dışarı tasarlamaya başlayabilir [oluşturma ve yazılan veri kümelerini düzenleme](../data-tools/creating-and-editing-typed-datasets.md). Uygulama mimarisi, n katmanlı bir tasarım almaya hazır olduğunuzda, ayarlama **DataSet projesi** ayrı bir projeye veri kümesi sınıfı oluşturmak için bir veri kümesi özelliği.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Veri kümeleri ile TableAdapter’ları farklı projelere ayırma](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)  
 Üretilen veri kümesi sınıfını oluşturulan TableAdapter sınıfları içeren projenin dışına ve yeni bir proje içinde taşımayı açıklar.  
  
 [N katmanlı uygulamalarda TableAdapter’lara kod ekleme](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)  
 Kod için bir n katmanlı TableAdapter eklenebilir bir parçalı sınıf oluşturmayı açıklar.  
  
 [N katmanlı uygulamalarda veri kümelerine kod ekleme](../data-tools/add-code-to-datasets-in-n-tier-applications.md)  
 Kod bir n katmanlı veri kümesi için eklenebilir bir parçalı sınıf oluşturmayı açıklar.  
  
 [N Katmanlı bir veri kümesine doğrulama ekleme](../data-tools/add-validation-to-an-n-tier-dataset.md)  
 Verileri değiştirme üzerinde doğrulama gerçekleştirmek için kodunuzu nereye eklemeniz gerektiğini açıklar.  
  
 [İzlenecek yol: bir N katmanlı veri uygulaması oluşturma](../data-tools/walkthrough-creating-an-n-tier-data-application.md)  
 Türü belirtilmiş veri kümesi oluşturma ve birden çok projelere TableAdapter ve veri kümesi kodunu ayırmak için adım adım yönergeler sağlar.  
  
 [İzlenecek yol: Bir N katmanlı bir veri uygulamasına doğrulama ekleme](http://msdn.microsoft.com/library/b35d072c-31f0-49ba-a225-69177592c265)  
 N katmanlı veri uygulaması izlenecek yolda oluşturulan uygulamaya doğrulama eklemek için adım adım yönergeler sağlar.  
  
## <a name="reference"></a>Başvuru  
 <xref:System.Data.DataSet>  
  
 <xref:System.Data.TypedTableBase%601>  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [N katmanlı veri uygulamalarına genel bakış](../data-tools/n-tier-data-applications-overview.md)  
  
 [Hiyerarşik güncelleştirme](../data-tools/hierarchical-update.md)  
  
 [Visual Studio'da veri kümesi araçları](../data-tools/dataset-tools-in-visual-studio.md)  
  
 [Visual Studio'da verilere erişime](../data-tools/accessing-data-in-visual-studio.md)  
  
 [TableAdapter genel bakış](../data-tools/tableadapter-overview.md)  
  
 [LINQ to SQL ile N Katmanı ve Uzak Uygulamalar](http://msdn.microsoft.com/library/854a1cdd-53cb-45f5-83ca-63962a9b3598)
