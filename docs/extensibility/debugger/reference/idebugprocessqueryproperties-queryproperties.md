---
title: IDebugProcessQueryProperties::QueryProperties | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugProcessQueryProperties::QueryProperties
ms.assetid: 976a9962-b689-45bb-afb6-16b2c5dbc3b8
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c73cd73283a700d1e47ff5909d6c4ce7ec198714
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocessquerypropertiesqueryproperties"></a>IDebugProcessQueryProperties::QueryProperties
Hata ayıklama işlemi, belirtilen özellik değerleri için bu yöntemi sorgular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT QueryProperties(  
   ULONG                  celt,  
   PROCESS_PROPERTY_TYPE *rgdwPropTypes,  
   VARIANT               *rgtPropValues);  
```  
  
```csharp  
int QueryProperties(  
   uint                       celt,  
   enum_PROCESS_PROPERTY_TYPE rgdwPropTypes,  
   out object[ ]              rgtPropValues);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Özellik tanımları ve özellik değerlerini içeren dizi büyüklüğü.  
  
 `dwPropType`  
 [in] Sorgulanan özelliklerinin tanımları içeren bir dizi. Olası değerler şunlardır:  
  
-   PROCESS_PROPERTY_COMMAND_LINE = 1  
  
-   PROCESS_PROPERTY_CURRENT_DIRECTORY = 2  
  
-   PROCESS_PROPERTY_ENVIRONMENT_VARIABLES = 3  
  
 `pvarPropValue`  
 [out] Özellik değerlerini içeren bir dizi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem nadiren kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcessQueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties.md)