---
title: IDebugProgramNode2::DetachDebugger_V7 | Microsoft Docs
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
- IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
ms.assetid: d2d4b78e-a2dd-4217-97a6-ab648fd2ee2f
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 271a4053d90efd2d852e8b67ae8ad4d4353afa37
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49822318"
---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

KULLANIM DIŞI. KULLANMAYIN.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT DetachDebugger_V7 (   
   void   
);  
```  
  
```csharp  
int DetachDebugger_V7 ();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir uygulama her zaman döndürmelidir `E_NOTIMPL`.  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!WARNING]
>  Sürümünden itibaren [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], bu yöntem artık kullanılmamaktadır ve her zaman döndürmelidir `E_NOTIMPL`.  
  
 Hata ayıklayıcı beklenmedik şekilde sona erdiğinde, bu yöntem çağrılır. Bu yöntem çağrıldığında, kullanıcı CİHAZDAN ayrılmış gibi sorgulamanıza DE programın devam edecektir. Daha fazla hata ayıklama olay gönderilmelidir. Programın başka bir hata ayıklayıcı örneğinden iliştirilebilir olduğu bir durumda olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)

