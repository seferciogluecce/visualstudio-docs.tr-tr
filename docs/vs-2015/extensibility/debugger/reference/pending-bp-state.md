---
title: PENDING_BP_STATE | Microsoft Docs
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
- PENDING_BP_STATE
helpviewer_keywords:
- PENDING_BP_STATE enumeration
ms.assetid: ac04ad72-fa92-4a15-ade2-0d0bbbadfc7f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f8e3a0a273a2575579aa0971d3d5649749e337a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49868449"
---
# <a name="pendingbpstate"></a>PENDING_BP_STATE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bekleyen kesme noktasının (henüz bağlı bir kesme noktası) durumunu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_PENDING_BP_STATE {   
   PBPS_NONE     = 0x0000,  
   PBPS_DELETED  = 0x0001,  
   PBPS_DISABLED = 0x0002,  
   PBPS_ENABLED  = 0x0003  
};  
typedef DWORD PENDING_BP_STATE;  
```  
  
```csharp  
public enum enum_PENDING_BP_STATE {   
   PBPS_NONE     = 0x0000,  
   PBPS_DELETED  = 0x0001,  
   PBPS_DISABLED = 0x0002,  
   PBPS_ENABLED  = 0x0003  
};  
```  
  
## <a name="members"></a>Üyeler  
 PBPS_NONE  
 Sıfır için yer tutucu. Bu değeri hiçbir zaman döndürülür.  
  
 PBPS_DELETED  
 Bekleyen kesme noktasının silindiğini gösterir.  
  
 PBPS_DISABLED  
 Bekleyen kesme noktasını devre dışı olduğunu gösterir.  
  
 PBPS_ENABLED  
 Bekleyen kesme noktasının etkin olduğunu gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Olarak `state` üyesi [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md) yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md)

