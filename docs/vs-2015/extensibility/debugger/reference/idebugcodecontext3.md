---
title: IDebugCodeContext3 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dc3ed9762a781b26c6bf12e0c51fa95efaf9056b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49295002"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Genişletir [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) modülü ve işlem arabirimleri alınmasını etkinleştirmek için arabirim.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama motoru tarafından uygulanan ve tarafından tüketilen [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] paketinin hatalarını ayıkla.  
  
## <a name="methods"></a>Yöntemler  
 Yöntemlere ek olarak `IDebugCodeContext2` arabirimi bu arabirim, aşağıdaki yöntemleri uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|Hata ayıklama modülü arabirimine bir başvuru alır.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|Hata ayıklama işlemini arabirimine bir başvuru alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu genellikle uygulanacak bulunmayan isteğe bağlı bir arabirimdir.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

