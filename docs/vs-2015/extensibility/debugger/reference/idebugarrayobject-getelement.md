---
title: IDebugArrayObject::GetElement | Microsoft Docs
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
- IDebugArrayObject::GetElement
helpviewer_keywords:
- IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ec19e6c0b3d9e0b73232eda6ea52d674ac1933cf
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49900611"
---
# <a name="idebugarrayobjectgetelement"></a>IDebugArrayObject::GetElement
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bir dizideki öğe alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetElement(   
   DWORD          dwIndex,  
   IDebugObject** ppElement  
);  
```  
  
```csharp  
int GetElement(  
   [In] uint dwIndex,   
   out IDebugObject ppElement  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwIndex`  
 [in] Öğenin dizini.  
  
 `ppElement`  
 [out] Döndürür bir [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) öğeyi temsil eden arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Çok boyutlu dizi nesnesi olsa bile, bu yöntem, bir dizi nesnesinin tüm öğeleri tek boyutlu dizi görür. Örneğin, bir dizi verilen `myarray[3][2][6]` ve `dwIndex` 20 parametresi, bu yöntem döndürmesine öğesinden `myarray[1][1][2]`ve bir `dwIndex` 21 parametresinin öğesinden döndürmesine `myarray[1][1][3]`. Kullanım [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) dizideki öğelerin toplam sayısını belirlemek için yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)

