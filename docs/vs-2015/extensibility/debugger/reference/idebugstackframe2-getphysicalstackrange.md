---
title: IDebugStackFrame2::GetPhysicalStackRange | Microsoft Docs
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
- IDebugStackFrame2::GetPhysicalStackRange
helpviewer_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73024b173eb3cacd3bd75e703225bc3bc6b1eb33
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49918566"
---
# <a name="idebugstackframe2getphysicalstackrange"></a>IDebugStackFrame2::GetPhysicalStackRange
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bir yığın çerçevesiyle ilgili olan fiziksel adres aralığını makine bağımlı bir gösterimini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetPhysicalStackRange (   
   UINT64* paddrMin,  
   UINT64* paddrMax  
);  
```  
  
```csharp  
int GetPhysicalStackRange (   
   out ulong paddrMin,  
   out ulong paddrMax  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `paddrMin`  
 [out] Bu yığın çerçevesiyle ilgili en düşük fiziksel adresini döndürür.  
  
 `paddrMax`  
 [out] Bu yığın çerçevesiyle ilgili en yüksek fiziksel adresini döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından döndürülen bilgileri, yığın çerçevelerini sıralamak için oturum hata ayıklama Yöneticisi (SDM) tarafından kullanılır.  
  
 Bu çağrı yığını, diğer bir deyişle büyüdükçe, yeni yığın çerçevelerini gittikçe daha düşük bellek adreslerinde eklenir varsayılır. Bir çalışma zamanı mimarisi bu varsayımı eşleşen fiziksel yığın aralığı sağlamanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)

