---
title: TaskScheduler sınıfı - dahili üyeler | Microsoft Docs
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
- TaskScheduler class [.NET Framework debug engines]
- debug engines, TaskScheduler class [.NET Framework]
ms.assetid: 87f1c969-0217-4464-8907-7609c1bf61d3
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e384b9c7734c2197dd79c0b9fb6b415329ae0f05
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49203794"
---
# <a name="taskscheduler-class---internal-members"></a>TaskScheduler Sınıfı - Dahili Üyeler
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konu, iç üyelerini açıklar <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> yardımcı sınıf, bir özel hata ayıklayıcı uygulama. Bu sınıf hakkında genel bilgi için bkz: <xref:System.Threading.Tasks.TaskScheduler> başvuru konusu.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Bütünleştirilmiş kod:** mscorlib (mscorlib.dll içinde)  
  
 Bu iç üyeleri .NET Framework'ten erişemediği için aşağıdaki söz dizimini ortak Ara dil (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.class public abstract auto ansi beforefieldinit System.Threading.Tasks.TaskScheduler  
       extends System.Object  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[GetScheduledTasksForDebugger](../../extensibility/debugger/getscheduledtasksfordebugger-method.md)|Tüm zamanlanmış görevlerin dizisini alır.|  
|[GetTaskSchedulersForDebugger](../../extensibility/debugger/gettaskschedulersfordebugger-method.md)|Tüm alır <xref:System.Threading.Tasks.TaskScheduler> şu anda etkin olan nesneler.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [.NET Framework için Paralel Uzantı Dahili Bileşenleri](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)

