---
title: "Hata: DCOM iletişimi başlatılamıyor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.unmarshal_server_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 2a7b27e6-2526-4f32-bc4d-eaee447f24ec
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c80f2455b53cba46f0f2f753c55ff1b7e9dad8d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="error-unable-to-initiate-dcom-communication"></a>Hata: DCOM iletişimi başlatılamıyor
Yerel makine ile uzak makineye bağlantı kurmaya çalışırken bir DCOM hata oluştu. Bu bir güvenlik duvarı uzak sunucuda veya uzak makinede bozuk Windows kimlik doğrulaması kaynaklanır.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Uzak makinede Windows Güvenlik Duvarı etkinse, bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md) yerel hata ayıklama için Güvenlik Duvarı'nı yapılandırma hakkında yönergeler için.  
  
-   Windows kimlik doğrulaması geri yüklemek için her iki makine yeniden deneyin. Yerel ve Uzak makinelerde Kerberos hataları için olay günlüklerini inceleyin ve bilinen sorunlar için etki alanı yöneticileri ile iletişime geçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)