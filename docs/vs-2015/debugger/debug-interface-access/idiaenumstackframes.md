---
title: Idiaenumstackframes | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumStackFrames interface
ms.assetid: 3d1e8403-c9fc-42ff-ae35-0ab9a5ed2ad7
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 143ed31b8f19fcba56b7c7e6a7bb41e94f7d6432
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49182890"
---
# <a name="idiaenumstackframes"></a>IDiaEnumStackFrames
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Kullanılabilir çeşitli yığın çerçevelerini listeler.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaEnumStackFrames::Next](../../debugger/debug-interface-access/idiaenumstackframes-next.md)|Yığın çerçeve öğelerin belirtilen bir sayı sabit listesi dizisinden alır.|  
|[IDiaEnumStackFrames::Reset](../../debugger/debug-interface-access/idiaenumstackframes-reset.md)|Bir numaralandırma sıralı başlangıç durumuna sıfırlar.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırarak elde [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) veya [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) yöntemleri.  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl elde edilir ve gösterir `IDiaEnumStackFrames` arabirimi. Bkz: [Idiastackframe](../../debugger/debug-interface-access/idiastackframe.md) arabirimi uygulaması için `PrintStackFrame` işlevi.  
  
```cpp#  
void DumpStackFrames(IDiaStackWalker*     pStackWalker,  
                     IDiaStackWalkHelper* pStackWalkHelper,  
                     CV_CPU_TYPE_e        cpuType)  
{  
    if (pStackWalker != NULL && pStackWalkHelper != NULL)  
    {  
        CComPtr<IDiaEnumStackFrames> pEnumsFrames;  
        HRESULT hr;  
        hr = pStackWalker->getEnumFrames2(cpuType, pStackWalkHelper, &pEnumFrames);  
        if (SUCCEEDED(hr) && pEnumFrames != NULL)  
        {  
             CComPtr<IDiaStackFrame> pStackFrame;  
             DWORD celt = 0;  
  
             while (pEnumFrames->Next(1, &pStackFrame, &celt) == S_OK)  
             {  
                 PrintStackFrame(pStackFrame);  
             }  
             pStackFrame = NULL;  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Dia2.h  
  
 Kitaplık: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiastackwalkframe](../../debugger/debug-interface-access/idiastackwalkframe.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)



