---
title: PARSEFLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PARSEFLAGS
helpviewer_keywords: PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9c96eb60c397093fb5ec3291a0b02ee7cbd07e34
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="parseflags"></a>PARSEFLAGS
Bir ifade ayrıştırmayı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
typedef DWORD PARSEFLAGS;  
```  
  
```csharp  
public enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
```  
  
## <a name="members"></a>Üyeler  
 PARSE_EXPRESSION  
 İfade bir ifade değil gösterir.  
  
 PARSE_FUNCTION_AS_ADDRESS  
 İfade bir adresi olarak ayrıştırılması (ve daha sonra değerlendirilmesi için) olduğunu gösterir.  
  
 PARSE_DESIGN_TIME_EXPR_EVAL  
 İfade tasarım sırasında Ayrıştırılmakta olan gösterir (diğer bir deyişle, bir tasarımcı açık olduğunda).  
  
## <a name="remarks"></a>Açıklamalar  
 Bir parametre olarak geçirilen [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) ve [ayrıştırma](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [Ayrıştırma](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)