---
title: "CA2230: değişken bağımsız değişkenler için params kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseParamsForVariableArguments
- CA2230
helpviewer_keywords:
- CA2230
- UseParamsForVariableArguments
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 10920c4ff9083b52e2d35f7fa151644b89bb1102
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230: Değişken bağımsız değişkenler için params kullanın
|||  
|-|-|  
|TypeName|UseParamsForVariableArguments|  
|CheckId|CA2230|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir genel veya korumalı türünü kullanan bir ortak veya korumalı yöntem içeren `VarArgs` çağırma.  
  
## <a name="rule-description"></a>Kural Tanımı  
 `VarArgs` Çağırma parametreleri değişken sayıda ele belirli yöntemi tanımları ile kullanılır. Yöntemini kullanarak `VarArgs` çağırma ortak dil belirtimi (CLS) uyumlu değil ve programlama dilleri üzerinden erişilebilir olmayabilir.  
  
 C# ' ta, `VarArgs` çağırma kullanılan bir yöntemin parametre listesi ile sona erdiğinde `__arglist` anahtar sözcüğü. Visual Basic desteklemiyor `VarArgs` elips kullanan yönetilmeyen kod içinde verir kullanımını çağırma kuralı ve Visual C++ `...` gösterimi.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal C# ' ta düzeltmek için kullanın [params](/dotnet/csharp/language-reference/keywords/params) anahtar sözcüğü yerine `__arglist`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, iki yöntem, kural ihlal eden diğeri kural karşılayan gösterir.  
  
 [!code-csharp[FxCop.Usage.UseParams#1](../code-quality/codesnippet/CSharp/ca2230-use-params-for-variable-arguments_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Reflection.CallingConventions?displayProperty=fullName>   
 [Dil bağımsızlığı ve dilden bağımsız bileşenler](http://msdn.microsoft.com/Library/4f0b77d0-4844-464f-af73-6e06bedeafc6)