---
title: Eski dil hizmeti komutlarını kesme | Microsoft Docs
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
- commands, intercepting language service
- language services, intercepting commands
ms.assetid: eea69f03-349c-44bb-bd4f-4925c0dc3e55
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 45f0084d060e9727f30ba39233ec5b92818d9205
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49829891"
---
# <a name="intercepting-legacy-language-service-commands"></a>Eski Dil Hizmeti Komutlarını Kesme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

İle [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], metin görünümünü aksi işlemek dil hizmeti ıntercept komutları olabilir. Bu metin görünümünü değil yönetmiyor dile özgü davranışı için kullanışlıdır. Bu komutlar, dil hizmetinizden metin görünümü bir veya daha fazla komut filtreler ekleyerek yakalayabilirsiniz.  
  
## <a name="getting-and-routing-the-command"></a>Alma ve komut yönlendirme  
 Bir komut filtresi bir <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> belirli karakter dizileri veya anahtar komutları izleyen bir nesne. Tek metin görünümle birden fazla komut filtre ilişkilendirebilirsiniz. Her metin görünümünü bir komuta zincirini filtreleri korur. Yeni bir komut filtre oluşturduktan sonra uygun bir metin görünümünü zincirinde için filtre ekleyin.  
  
 Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> metodunda <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> zinciri, komut filtre eklemek için. Çağırdığınızda <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] komut filtrenizle işlemiyor komutları geçirmek başka bir komut filtre döndürür.  
  
 Komut işleme için aşağıdaki seçenekleriniz vardır:  
  
- Komutu işlemek ve ardından sonraki komut filtre açın komut zincirinde geçirin.  
  
- Komutu işlemek ve sonraki komutu filtre açın komutu kodum'a geçirmez.  
  
- Komutunu işleyemez, ancak sonraki komut filtre açın komutu geçirin.  
  
- Komut yoksayın. Geçerli filtreye işlemez ve sıradaki filtreye açın geçirmeyin.  
  
  Dil hizmetinizin hangi komutları işlemek için bilgi [dil hizmeti filtreleri için önemli komutlar](../../extensibility/internals/important-commands-for-language-service-filters.md).

