---
title: 'Hata: Güvenlik denetimi başarısız IIS Yönetici Hizmeti yanıt vermediğinden | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.iis_not_responding
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: 6060e94e-71dc-49f2-bb59-2584216eadbf
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a90a684a9de45e1fba67460d0ba0f01554d248f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49207200"
---
# <a name="error-a-security-check-failed-because-the-iis-admin-service-did-not-respond"></a>Hata: IIS Yönetici Hizmeti Yanıt Vermediğinden Güvenlik Denetimi Başarısız
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

IIS Yönetici Hizmeti yanıt vermiyor, bu hata oluşur. Bu, genellikle IIS yükleme ile ilgili bir sorun olduğunu gösterir. İlk olarak kullanarak hizmetinin çalıştığını doğrulayın. **Hizmetleri** gelen aracı **Yönetimsel Araçlar**.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   IIS kullanarak yeniden **Program Ekle veya Kaldır** Denetim Masası.  
  
-   veya  
  
-   Program Ekle veya Kaldır Denetim Masası'nı kullanarak makinenizden IIS kaldırın. IIS kaldırmış ve hala sorunlarla, kayıt defterini denetleyin ve bu anahtar artık mevcut olduğundan emin olun:  
  
    ```  
    HKEY_CLASSES_ROOT\CLSID\{A9E69610-B80D-11D0-B9B9-00A0C922E750}  
    ```  
  
     veya  
  
-   Yönetimsel Araçlar Denetim Masası'nı kullanarak IIS Yönetici Hizmeti devre dışı bırakın. Bu IIS makinenizde devre dışı bırakır.  
  
     Bu üç adımlardan herhangi biri gerçekleştirildikten sonra bilgisayarınızı yeniden başlatın.  
  
     Ek bilgi için IIS belgelerine bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Web Uygulamalarında Hata Ayıklama: Hatalar ve Sorun Giderme](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



