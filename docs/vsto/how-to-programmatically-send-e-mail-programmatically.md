---
title: "Nasıl yapılır: program aracılığıyla e-posta gönderme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], sending e-mail
- Outlook [Office development in Visual Studio], creating e-mail
- Outlook [Office development in Visual Studio], sending e-mail
- e-mail [Office development in Visual Studio], sending
ms.assetid: 4fa0e1b5-2caf-4a11-8626-df643b23f5f0
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 98b0eefafa86fdaf8f7a664ac75a2f7c71a43549
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-send-e-mail"></a>Nasıl yapılır: program aracılığıyla e-posta Gönder  
  Bu örnekte, etki alanı adına sahip kişiler için bir e-posta iletisi gönderilir **example.com** e-posta adreslerini içinde.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_OL_ProgramEmail#1](../vsto/codesnippet/CSharp/Trin_OL_ProgramEMail/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Etki alanı adına sahip kişiler **example.com** e-posta adreslerini içinde.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Etki alanı adını arar filtre kodunu kaldırmayın **example.com**. Filtre kaldırırsanız çözümünüzü tüm kişilerinizin e-posta iletileri gönderir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Posta öğeleri ile çalışma](../vsto/working-with-mail-items.md)   
 [Nasıl yapılır: program aracılığıyla e-posta öğesi oluşturma](../vsto/how-to-programmatically-create-an-e-mail-item.md)   
 [Nasıl yapılır: program aracılığıyla, Outlook Kişilerine erişme](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [Nasıl yapılır: bir e-posta iletisi alındığında program aracılığıyla işlem gerçekleştirme](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
  
  