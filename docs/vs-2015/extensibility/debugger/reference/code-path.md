---
title: CODE_PATH | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CODE_PATH
helpviewer_keywords:
- CODE_PATH structure
ms.assetid: 2d4b2890-4c9d-47e1-83c0-df9c6436427f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cf8326fe1434b65293dc19de9da64a9a39327e39
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49844616"
---
# <a name="codepath"></a>CODE_PATH
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bir yöntem veya işlev çağrısı açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
typedef struct tagCODE_PATH {   
   BSTR                bstrName;  
   IDebugCodeContext2* pCode;  
} CODE_PATH;  
```  
  
```csharp  
public struct CODE_PATH {  
   public string            bstrName;  
   public IDebugCodeContext pCode;  
}  
```  
  
## <a name="members"></a>Üyeler  
 bstrName  
 Kod yolu adı.  
  
 pCode  
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) bir işleve için kodu nerede tanımlayan nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı, bir işlevin Adımlama uygulamak için kullanılır. [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md) tüm çağrıları ayıklanan programın geçerli konumu döndürür. Bu yapı, böyle bir çağrısını temsil eder.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)

