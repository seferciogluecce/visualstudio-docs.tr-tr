---
title: Sembol sağlayıcısı | Microsoft Docs
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
- symbol handler
- debugging [Debugging SDK], symbol handler
ms.assetid: 5fce651b-fead-4418-81b0-a011df7644ab
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ec512dc9b200550996e9e82f0c1f3cbd616087d3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49236736"
---
# <a name="symbol-provider"></a>Sembol Sağlayıcısı
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bir ifade değerlendiricisi uygulama değişkenleri ve ifadeleri değerlendirilebilmesi için dil derleyicisi tarafından üretilen sembolik hata ayıklama bilgileri erişmeniz gerekir. Bunu bir sembol işleyici olarak da adlandırılan bir sembol sağlayıcısı (SP) arabirimleri kullanma tarafından yapar.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Program veritabanı (PDB) sembolü dosya biçimi kullanılarak yerel kod yanı sıra yönetilen kod için SPs sağlar. Olmadığı sürece güçlü özel biçiminde depolanan semboller kullanmak, programınız için gerekir, bu tarafından sağlanan SPs kullanmanız önerilir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="implementation-notes"></a>Uygulama Notları  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Hata ayıklama motorlarını beklediğiniz ortak dil çalışma zamanı (CLR) arabirimlerini kullanarak SPs ile bahsedeceğiz. Sonuç olarak, Visual Studio hata ayıklama altyapıları ile çalışan bir SP CLR desteklemesi gerekir. Hata ayıklama arabirimleri tüm CLR tam listesi parçası olan debugref.doc içinde bulunabilir, [!INCLUDE[winsdklong](../../includes/winsdklong-md.md)].  
  
 Yalnızca özel hata ayıklama altyapısıyla, SP çalışacaksınız ise, hata ayıklama altyapısı gereksinimlerine bağlı olarak uygun gördüğünüz şekilde SP uygulayabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcı Bileşenleri](../../extensibility/debugger/debugger-components.md)

