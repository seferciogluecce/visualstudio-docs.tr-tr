---
title: "CA1411: COM kayıt yöntemleri görünebilir olmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1411
- ComRegistrationMethodsShouldNotBeVisible
helpviewer_keywords:
- ComRegistrationMethodsShouldNotBeVisible
- CA1411
ms.assetid: a59f96f1-1f38-4596-b656-947df5c55311
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 67a4d4124ac1aae99327fdcd757db546cb50adfe
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1411-com-registration-methods-should-not-be-visible"></a>CA1411: COM kayıt yöntemleri görünebilir olmamalıdır
|||  
|-|-|  
|TypeName|ComRegistrationMethodsShouldNotBeVisible|  
|CheckId|CA1411|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 İle işaretli bir yöntem <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> veya <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> özniteliktir harici olarak görünür.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bileşen Nesne Modeli (COM) ile bir derlemeyi kaydedildiğinde, her COM görünebilir tür derlemesindeki için kayıt defteri girişleri eklenir. İle işaretlenen yöntemleri <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> ve <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> öznitelikleri çağrılır kayıt ve kayıt silme işlemleri sırasında sırasıyla kaydı/kaydının silinmesi için bu tür özel kullanıcı kodu çalıştırmak için. Bu kod, bu işlemler çağrılmamalıdır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için yönteme erişilebilirliğini değiştirme `private` veya `internal` (`Friend` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kural ihlal iki yöntem gösterilmektedir.  
  
 [!code-csharp[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/CSharp/ca1411-com-registration-methods-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/VisualBasic/ca1411-com-registration-methods-should-not-be-visible_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1410: COM kayıt yöntemleri eşleşmesi](../code-quality/ca1410-com-registration-methods-should-be-matched.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [Derlemeleri COM ile kaydetme](/dotnet/framework/interop/registering-assemblies-with-com)   
 [RegAsm.exe (derleme kayıt aracı)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)