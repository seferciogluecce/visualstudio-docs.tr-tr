---
title: "Nasıl yapılır: ClickOnce uygulaması için dosya ilişkilendirmeleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- file associations, ClickOnce applications
- ClickOnce deployment, file associations
ms.assetid: 835230c8-3177-440f-85e3-e40f1d8b4f9d
caps.latest.revision: "7"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 491de73e97bf44ea54d5ccdfb604924ff26c9530
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-create-file-associations-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için Dosya İlişkilendirmeleri Oluşturma
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]Böylece uygulama, kullanıcı o türden bir dosya açıldığında otomatik olarak başlatılır uygulamaları bir veya daha fazla dosya adı uzantıları ile ilişkilendirilebilir. Dosya adı uzantısı desteği ekleme bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamasıdır kolay.  
  
### <a name="to-create-file-associations-for-a-clickonce-application"></a>ClickOnce uygulaması için dosya ilişkilendirmeleri oluşturmak için  
  
1.  Oluşturma bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama normalde veya var olan kullanmak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
2.  Bir metin veya Not Defteri gibi bir XML Düzenleyicisi ile uygulama bildirimini açın.  
  
3.  Bul `assembly` öğesi. Daha fazla bilgi için bkz: [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md).  
  
4.  Bir alt öğesi olarak `assembly` öğesi ekleme bir `fileAssociation` öğesi. `fileAssociation` Öğesi dört özniteliğe sahiptir:  
  
    -   `extension`: Uygulama ile ilişkilendirmek istediğiniz dosya adı uzantısı.  
  
    -   `description`: Windows Kabuğu'nda görünür dosya türü bir açıklaması.  
  
    -   `progid`: Kayıt defterinde işaretlemek için dosya türü benzersiz olarak tanımlayan bir dize.  
  
    -   `defaultIcon`: Bu dosya türü için kullanılacak bir simge. Simge bir dosya kaynak uygulama bildirimi olarak eklenmelidir. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulamasına bir veri dosyası dahil](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
     Bir örnek için `file` ve `fileAssociation` öğeler, bkz [ \<fileAssociation > öğesi](../deployment/fileassociation-element-clickonce-application.md).  
  
5.  Birden çok dosya türünü uygulama ile ilişkilendirmek istiyorsanız, ek eklemeniz `fileAssociation` öğeleri. Unutmayın `progid` özniteliği her biri için farklı olmalıdır.  
  
6.  Uygulama bildirimine tamamladıktan sonra bildirimi yeniden imzalayın. Komut satırından Mage.exe kullanarak bunu yapabilirsiniz.  
  
     `mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx`  
  
     Daha fazla bilgi için bkz: [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<fileAssociation > öğesi](../deployment/fileassociation-element-clickonce-application.md)   
 [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)   
 [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)