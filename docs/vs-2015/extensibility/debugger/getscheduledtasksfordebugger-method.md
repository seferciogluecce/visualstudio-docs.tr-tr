---
title: GetScheduledTasksForDebugger metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 57d71dff0404b8bcea7f7274b943925eb45e0830
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49202003"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger Metodu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tüm zamanlanmış görevlerin dizisini alır.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Bütünleştirilmiş kod:** mscorlib (mscorlib.dll içinde)  
  
 .NET Framework'den bu iç üye erişemediği için aşağıdaki söz dizimini ortak Ara dil (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tüm zamanlanmış görevlerin dizisi. Her görev, yürütülmekte olan veya yürütülmesi tamamlandı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem iş parçacığı güvenli değildir ve diğer örnekleri aynı anda kullanılmamalıdır <xref:System.Threading.Tasks.TaskScheduler> yalnızca hata ayıklayıcı, diğer tüm iş parçacıkları askıya olduğunda, hata ayıklayıcı'dan çağrılmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TaskScheduler Sınıfı](../../extensibility/debugger/taskscheduler-class-internal-members.md)

