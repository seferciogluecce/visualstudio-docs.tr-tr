---
title: GETHOSTNAME_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: GETHOSTNAME_TYPE
helpviewer_keywords: GETHOSTNAME_TYPE enumeration
ms.assetid: 2be92bea-8133-412b-9015-1833baf16e1b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ba4c0eb77d1eb2a902c9db1288785cf2b6d0ac7a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="gethostnametype"></a>GETHOSTNAME_TYPE
Ana bilgisayar adı türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_GETHOSTNAME_TYPE {   
   GHN_FRIENDLY_NAME = 0,  
   GHN_FILE_NAME     = 1  
};  
typedef DWORD GETHOSTNAME_TYPE;  
```  
  
```csharp  
public enum enum_GETHOSTNAME_TYPE {   
   GHN_FRIENDLY_NAME = 0,  
   GHN_FILE_NAME     = 1  
};  
```  
  
## <a name="members"></a>Üyeler  
 GHN_FRIENDLY_NAME  
 Ana bilgisayarın kolay adını belirtir.  
  
 GHN_FILE_NAME  
 Ana bilgisayar dosya adını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerler için bağımsız değişken olarak geçirilen [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) bir ana bilgisayar adı farklı biçimlerde alma yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)