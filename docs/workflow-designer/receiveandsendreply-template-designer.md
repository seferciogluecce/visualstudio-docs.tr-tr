---
title: "ReceiveAndSendReply şablonu Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.ReceiveAndSendReply.UI
- System.ServiceModel.Activities.SendReply.UI
ms.assetid: d1d9a058-df7e-48f5-a2e7-3caeeba7eaa6
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: ef7b027eb82b149f3cffcd54c976e1be608c2190
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="receiveandsendreply-template-designer"></a>ReceiveAndSendReply şablonu Tasarımcısı
**ReceiveAndSendReply** şablonu çifti oluşturmak için kullanılan önceden yapılandırılmış <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> içindeki etkinlikleri bir <xref:System.Activities.Statements.Sequence> istek/yanıt iletisi exchange bir parçası olarak bağıntılı etkinliği Sunucu üzerindeki deseni.  
  
## <a name="the-receiveandsendreply-template"></a>ReceiveAndSendReply şablonu  
 Ekleme **ReceiveAndSendReply** şablonu oluşturma yanı sıra üç şey yapar <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> etkinliklerle bir <xref:System.Activities.Statements.Sequence> etkinlik:  
  
1.  Yapılandırır <xref:System.ServiceModel.Activities.Receive.OperationName%2A>, <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> özelliklerini <xref:System.ServiceModel.Activities.Receive> etkinlik.  
  
2.  Bağlar <xref:System.ServiceModel.Activities.SendReply.Request%2A> özelliği <xref:System.ServiceModel.Activities.Receive> etkinliğe <xref:System.ServiceModel.Activities.Send> etkinlik.  
  
3.  Oluşturur bir <xref:System.ServiceModel.Activities.CorrelationHandle> bir değişken üst etkinlik olarak.  
  
### <a name="using-the-receiveandsendreply-template-designer"></a>ReceiveAndSendReply şablonu Tasarımcısı'nı kullanarak  
 **ReceiveAndSendReply** etkinlik Tasarımcısı bulunabilir **ileti** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç kutusu**  sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **ReceiveAndSendReply** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir. Bu oluşturur bir <xref:System.ServiceModel.Activities.Receive> ile yapılandırılmış etkinlik **Gönder** etkinlik Tasarımcısı ve bir ilişkili <xref:System.ServiceModel.Activities.SendReply> SendReplyToReceive Tasarımcısı ile yapılandırılabilir.  
  
 [!INCLUDE[crabout](../test/includes/crabout_md.md)]kullanarak **alma** yapılandırmak için tasarımcı <xref:System.ServiceModel.Activities.Receive> etkinliği bkz [alma](../workflow-designer/receive-activity-designer.md) konu.  
  
 [!INCLUDE[crabout](../test/includes/crabout_md.md)]kullanarak **SendReplyToReceive** yapılandırmak için tasarımcı <xref:System.ServiceModel.Activities.SendReply> etkinlik, aşağıdaki bölüme bakın.  
  
### <a name="properties-of-sendreply"></a>SendReply özellikleri  
 Aşağıdaki tabloda <xref:System.ServiceModel.Activities.SendReply> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellikleri kılavuzunda düzenlenebilir ve bazı üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Tasarımcı yüzeyine.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.ServiceModel.Activities.SendReply> etkinlik. SendReplyToReceive varsayılandır.<br /><br /> Ancak kolay için varsayılan olmayan bir değer kullanımını <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil gibi bir değer kullanmak için en iyi bir uygulamadır.|  
|<xref:System.ServiceModel.Activities.SendReply.Request%2A>|Doğru|Başvuru <xref:System.ServiceModel.Activities.Receive> etkinlik bu ile eşleştirilmiş <xref:System.ServiceModel.Activities.SendReply> etkinlik. Bu özellik olmamalıdır **null**. <xref:System.ServiceModel.Activities.Receive>ve <xref:System.ServiceModel.Activities.SendReply> etkinlikleri birlikte sunucuda bir istek/yanıt Mesajlaşma düzeni modellemek için kullanılır. Bu özellik belirten <xref:System.ServiceModel.Activities.Send> etkinlik eşleştirilmiş. Tasarımcıda için otomatik olarak bağlı olduğundan, bu özellik düzenlenemiyor <xref:System.ServiceModel.Activities.Send> , oluşturulduğu etkinlik <xref:System.ServiceModel.Activities.SendReply> etkinlik.|  
|<xref:System.ServiceModel.Activities.SendReply.Content%2A>|False|Almak için ileti veya parametre içeriğini belirtir. Ya da olabilir bir <xref:System.ServiceModel.Activities.ReceiveMessageContent> etkinlik veya <xref:System.ServiceModel.Activities.ReceiveParametersContent> etkinlik. Bu özelliğin yanındaki üç nokta düğmesine tıklayarak Düzenle **içerik** özellik kılavuzu veya tıklatarak alanındaki **tanımla...**  yanındaki düğmesini **içerik** üzerinde etiket **alma** etkinlik Tasarımcı yüzeyine. Her ikisi de görüntülemek **içerik tanımı** iletişim. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu kutu kullanma hakkında [içerik tanımı iletişim kutusunu](../workflow-designer/content-definition-dialog-box.md) konu.|  
|<xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A>|False|Koleksiyonunu belirtir <xref:System.ServiceModel.Activities.CorrelationInitializer> birden çok başlatma nesneleri <xref:System.ServiceModel.Activities.CorrelationHandle> bu yapılandırma nesneleri <xref:System.ServiceModel.Activities.Receive> akışındaki etkinlikler. Yanındaki üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A> özelliğini açmak için özellikler kılavuzunda **eklemek bağıntı başlatıcıları** iletişim kutusu. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu kutusunu kullanarak bkz [CorrelationInitializers iletişim kutusunu](../workflow-designer/add-correlationinitializers-dialog-box.md) konu.|  
|<xref:System.ServiceModel.Activities.SendReply.Action%2A>|False|İletinin eylem üstbilgisini belirtir. Açıkça ayarlanmazsa değerini varsayılan olarak:<br /><br /> **https://tempuri.org/ {hizmet sözleşmesi ad} / {hizmet sözleşmesi adı} / {işlem adı}**|  
|<xref:System.ServiceModel.Activities.SendReply.PersistBeforeSend%2A>|False|Yanıt iletisi gönderilmeden önce iş akışı örneği kalıcı olup olmadığını belirtir. Varsayılan değer **false**.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [Alma](../workflow-designer/receive-activity-designer.md)   
 [Gönder](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)