---
title: "CA1712: numaralandırma değerleri tür adıyla önek kullanmayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1712
- DoNotPrefixEnumValuesWithTypeName
helpviewer_keywords:
- CA1712
- DoNotPrefixEnumValuesWithTypeName
ms.assetid: df0e3a12-67bf-48f1-a10b-2ef60484a5c7
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a7c2ba5f81cadb8940c519174bec7cf76cbf8500
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1712-do-not-prefix-enum-values-with-type-name"></a>CA1712: Numaralandırma değerleri için tür adıyla önek kullanmayın
|||  
|-|-|  
|TypeName|DoNotPrefixEnumValuesWithTypeName|  
|CheckId|CA1712|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Numaralandırma adı numaralandırma türünün adı ile başlayan bir üye içeriyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Tür bilgileri geliştirme araçları tarafından sağlanacak beklendiğinden numaralandırma üyeleri adlarını tür adıyla önek değil.  
  
 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu yeni bir yazılım kitaplığı öğrenmek için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır süreyi azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal gidermek için numaralandırma üyesi türü adı öneki kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek düzeltilmiş sürüm tarafından izlenen yanlış adlandırılmış numaralandırma gösterir.  
  
 [!code-csharp[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/CSharp/ca1712-do-not-prefix-enum-values-with-type-name_1.cs)]
 [!code-cpp[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/CPP/ca1712-do-not-prefix-enum-values-with-type-name_1.cpp)]
 [!code-vb[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/VisualBasic/ca1712-do-not-prefix-enum-values-with-type-name_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1711: Tanımlayıcılar yanlış sonekine sahip olmamalıdır](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)  
  
 [CA1027: numaralandırmaları FlagsAttribute ile işaretle](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Enum?displayProperty=fullName>