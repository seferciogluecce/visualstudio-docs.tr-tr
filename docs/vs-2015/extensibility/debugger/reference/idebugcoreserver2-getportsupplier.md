---
title: IDebugCoreServer2::GetPortSupplier | Microsoft Docs
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
- IDebugCoreServer2::GetPortSupplier
helpviewer_keywords:
- IDebugCoreServer2::GetPortSupplier
ms.assetid: acf181d4-ef42-4aa5-86f9-95fd5467ea31
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a31d1ef0f6719de648cbdcbe4a4903d9c8135192
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49892901"
---
# <a name="idebugcoreserver2getportsupplier"></a>IDebugCoreServer2::GetPortSupplier
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Belirli bir bağlantı noktası sağlayıcısı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetPortSupplier(   
   REFGUID               guidPortSupplier,  
   IDebugPortSupplier2** ppPortSupplier  
);  
```  
  
```csharp  
int GetPortSupplier(   
   ref Guid                guidPortSupplier,  
   out IDebugPortSupplier2 ppPortSupplier  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guidPortSupplier`  
 [in] Alınacak bağlantı noktası sağlayıcısı GUID.  
  
 `ppPortSupplier`  
 [out] Döndürür bir [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) istenen bağlantı noktası sağlayıcısı temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)

