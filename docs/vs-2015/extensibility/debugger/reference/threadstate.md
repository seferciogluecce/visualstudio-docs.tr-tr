---
title: THREADSTATE | Microsoft Docs
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
- THREADSTATE
helpviewer_keywords:
- THREADSTATE enumeration
ms.assetid: 62efdd7c-25b1-4fd3-9d06-ac1830a418a9
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 07c4fe23f4bef02282ba1d53f4953f41d1f6343e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49814760"
---
# <a name="threadstate"></a>THREADSTATE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

İş parçacığı durumunu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
typedef DWORD THREADSTATE;  
```  
  
```csharp  
public enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
```  
  
## <a name="members"></a>Üyeler  
 THREADSTATE_RUNNING  
 İş parçacığı çalıştığını gösterir.  
  
 THREADSTATE_STOPPED  
 İş parçacığı bir kesme noktası nedeniyle durdurulduğunu gösterir.  
  
 THREADSTATE_FRESH  
 İş parçacığı oluşturuldu, ancak henüz kod çalışmıyor gösterir.  
  
 THREADSTATE_DEAD  
 İş parçacığı geçersiz olduğunu gösterir.  
  
 THREADSTATE_FROZEN  
 İş parçacığı'nın dondurulmuş olup olmadığını gösterir (hiçbir yürütme gerçekleştirilebilir).  
  
## <a name="remarks"></a>Açıklamalar  
 İçin kullanılan `dwThreadState` alanını [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)

