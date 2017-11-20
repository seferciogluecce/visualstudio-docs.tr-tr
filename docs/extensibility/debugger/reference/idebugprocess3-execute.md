---
title: IDebugProcess3::Execute | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess3::Execute
helpviewer_keywords: IDebugProcess3::Execute
ms.assetid: d831cd81-d7bf-4172-8517-aa699867791f
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 96b18bdb8aa0097071369a01013772dc3bd0d5bd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocess3execute"></a>IDebugProcess3::Execute
Bu işlem durdurulmuş bir durumdan çalışmaya devam eder. Herhangi bir önceki yürütme durumu (örneğin, bir adım) kaldırılır ve yeniden yürütme işlemi başlatır.  
  
> [!NOTE]
>  Bu yöntem yerine kullanılmalıdır [yürütme](../../../extensibility/debugger/reference/idebugprogram2-execute.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Execute(  
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Execute(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pThread`  
 [in] Bir [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) yürütmek için iş parçacığı temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde, hata kodunu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı başka bir işlem ait iş parçacığı durdurulmuş durumda gelen yürütme başlatıldığında, bu işlemi bu yöntem çağrılır. Kullanıcı seçtiğinde bu yöntem olarak da adlandırılır **Başlat** komutunu **hata ayıklama** IDE menüde. Bu yöntemin kullanımı çağırmak kadar kolaydır [Sürdür](../../../extensibility/debugger/reference/idebugthread2-resume.md) işlemdeki geçerli iş parçacığı üzerinde yöntemi.  
  
> [!WARNING]
>  Bir durdurma veya bir anında (zaman uyumlu) olayın göndermeyin [olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) bu çağrıyı; işlenirken hata ayıklayıcı aksi kilitlenebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Devam et](../../../extensibility/debugger/reference/idebugthread2-resume.md)   
 [Olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)