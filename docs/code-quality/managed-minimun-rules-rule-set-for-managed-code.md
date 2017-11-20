---
title: "Yönetilen kod için yönetilen Minimum kurallar kural kümesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ac5ec4db1fe36d7e92c4f9062f8d0c28bae2263e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="managed-minimum-rules-rule-set-for-managed-code"></a>Yönetilen kod için yönetilen Minimum kurallar kural kümesi
En önemli sorunları, kodunuzda olası güvenlik açıklarını, uygulama çökme (Crash) ve diğer önemli mantığı ve tasarım hataları gibi yönetilen Minimum kurallar odaklanır. Projeler için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|Atılabilir alanlara sahip olan türler atılabilir olmalıdır|  
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|Boş Sonlandırıcıları kaldırın|  
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|Atılabilen alanlar atılmalıdır|  
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|ValueType.Equals geçersiz kılma üzerinde eşittir işlecini aşırı yükleme|