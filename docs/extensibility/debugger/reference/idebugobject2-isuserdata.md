---
title: IDebugObject2::IsUserData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject2::IsUserData
helpviewer_keywords: IDebugObject2::IsUserData method
ms.assetid: 6ffa0d0e-f742-496d-acc7-db74c248bc45
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ac758e7e8ce4d288b347b1207883642c920059bb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugobject2isuserdata"></a>IDebugObject2::IsUserData
Nesne kullanıcı verilerini temsil edip etmediğini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT IsUserData(  
   BOOL* pfUser  
);  
```  
  
```csharp  
int IsUserData(  
   out int pfUser  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pfUser`  
 [out] Sıfır olmayan bir değer döndürür (`TRUE`) kullanıcı verilerini; nesne temsil ediyorsa sıfır (`FALSE`) mevcut değilse.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı, JustMyCode (kullanıcı kodu olarak ve bu nedenle yığın izlemesi görünür bir modül işaretler kullanıcı tarafından yapılandırılabilir bir seçeneği) olarak tasarlanmış bir modülün parçası olan herhangi bir nesne verilerdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)