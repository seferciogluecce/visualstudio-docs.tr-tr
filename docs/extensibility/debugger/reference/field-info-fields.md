---
title: FIELD_INFO_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FIELD_INFO_FIELDS
helpviewer_keywords: FIELD_INFO_FIELDS enumeration
ms.assetid: a69487d2-e701-4165-804a-8a011df9a3bd
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d1aa1c2363ecf3cb6bfd9531112c87d8bcaeefe4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="fieldinfofields"></a>FIELD_INFO_FIELDS
Hakkında almak için hangi bilgilerin belirten bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_FIELD_INFO_FIELDS {   
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
typedef DWORD FIELD_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_FIELD_INFO_FIELDS {  
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
```  
  
## <a name="members"></a>Üyeler  
 FIF_FULLNAME  
 Başlatma/kullanım `bstrFullName` alanındaki [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) yapısı.  
  
 FIF_NAME  
 Başlatma/kullanım `bstrName` alanındaki `FIELD_INFO` yapısı.  
  
 FIF_TYPE  
 Başlatma/kullanım `bstrType` alanındaki `FIELD_INFO` yapısı.  
  
 FIF_MODIFIERS  
 Başlatma/kullanım `bstrModifiers` alanındaki `FIELD_INFO` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerleri de bağımsız değişken olarak geçirilen [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) hangi alanlarının belirtmek için yöntemi [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) yapısı başlatılması üzeresiniz.  
  
 Bu değerleri de içinde kullanılan `dwFields` üyesi `FIELD_INFO` hangi alanların kullanılan ve geçerli olduğunu belirtmek için yapısı.  
  
 Bu bayrakların bit ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)