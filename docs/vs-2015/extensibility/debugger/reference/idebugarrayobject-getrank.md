---
title: IDebugArrayObject::GetRank | Microsoft Docs
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
- IDebugArrayObject::GetRank
helpviewer_keywords:
- IDebugArrayObject::GetRank method
ms.assetid: 9948551a-e334-4ff6-979c-08dab633b9b6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ddfee024f856b5f94702e6e7cae12b09f3bfa59e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49908993"
---
# <a name="idebugarrayobjectgetrank"></a>IDebugArrayObject::GetRank
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Dizi boyut sayısını, diğer bir deyişle, boyut sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdwRank`  
 [out] Derecesini döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım [GetDimensions](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md) dizi nesnesinin her boyutunun boyutunu almak için yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)

