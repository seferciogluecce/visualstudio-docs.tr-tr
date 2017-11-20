---
title: IDebugStackFrame2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugStackFrame2
helpviewer_keywords: IDebugStackFrame2 interface
ms.assetid: bd212a6a-dcc6-4756-a77a-e8dfda38b104
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4d7c08cd7fc89e33ef9d505c9e32c23737ef7e84
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugstackframe2"></a>IDebugStackFrame2
Bu arabirim, belirli bir iş parçacığı çağrı yığınında tek yığın çerçevesi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugStackFrame2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE) yığın çerçevesi temsil etmek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) almak için bir [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) arabirimi. Çağrı [sonraki](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md) almak için bir [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) içeren yapısı `IDebugStackFrame2` arabirimi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugStackFrame2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|Bu yığın çerçevesi için kod bağlamını alır.|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|Bu yığın çerçevesi için belge bağlamını alır.|  
|[GetName](../../../extensibility/debugger/reference/idebugstackframe2-getname.md)|Yığın çerçevesi adını alır.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)|Yığın çerçevesi açıklamasını alır.|  
|[GetPhysicalStackRange](../../../extensibility/debugger/reference/idebugstackframe2-getphysicalstackrange.md)|Yığın çerçevesi ile ilişkili fiziksel adres aralığını makine bağımlı bir gösterimini alır.|  
|[GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)|Geçerli bağlam içinde ifade değerlendirme bir yığın çerçevesi ve iş parçacığı yapmak için bir değerlendirme bağlamını alır.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugstackframe2-getlanguageinfo.md)|Yığın çerçevesi ile ilişkili dilini alır.|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)|Yığın çerçevesi ile ilişkili özellikleri açıklamasını alır.|  
|[EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)|Yığın için bir numaralandırıcı çerçeve özellikleri oluşturur.|  
|[GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)|Yığın çerçevesi ile ilişkili iş parçacığı alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayıklanacak program (ya da bir kullanıcı tarafından ayarlanmış kesme noktası veya bir özel durum nedeniyle) bir kesme noktasında yalnızca durduruldu olduğunda bu arabirimi elde edilir. Bu arabirimden ifadeleri değerlendirmek için bir ifade bağlamı alınabilir, kayıtları listesi döndürülebilecek veya çağrı yığını elde ve incelenmesi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)