---
title: 'Nasıl yapılır: özel durumdan sonra sistem kodunu İnceleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, exceptions
- exceptions, debugging
ms.assetid: a38ad49b-7cf3-483d-91c4-eb3116eba50c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a8a1da63e47514771a868b69ee798f71265fdb42
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31472471"
---
# <a name="how-to-examine-system-code-after-an-exception"></a>Nasıl Yapılır: Özel Durumdan Sonra Sistem Kodunu İnceleme
Bir özel durum oluştuğunda, özel durum nedenini belirlemek için bir sistem çağrısı içinde kod inceleyin gerekebilir. Aşağıdaki yordam, sistem kodunu yüklenen simgeleri yoksa bunun nasıl yapılacağı ya da sadece kendi kodumu etkin olup olmadığını açıklar.  
  
### <a name="to-examine-system-code-following-an-exception"></a>Bir özel durum aşağıdaki sistem kodu incelemek için  
  
1.  İçinde **çağrı yığını** penceresinde, sağ tıklatın ve ardından tıklatın **Göster harici kod**.  
  
     Sadece kendi kodumu etkin değilse, bu seçenek kısayol menüsünde kullanılabilir değil ve sistem kodu varsayılan olarak gösterilir.  
  
2.  Artık görünür harici kod çerçeveleri sağ **çağrı yığını** penceresi.  
  
3.  İşaret **yük simgeleri gelen** ve ardından **Microsoft simge sunucuları**.  
  
    1.  Sadece kendi kodumu etkinleştirilmişse, bir iletişim kutusu görüntülenir. Bu, sadece kendi kodumu şimdi devre dışı olduğunu belirtir. Bu, sistem çağrıları Adımlama için gereklidir.  
  
    2.  **Genel semboller indirme** iletişim kutusu görüntülenir. Tamamlandığında indirirken kaybolur.  
  
4.  Artık sistem kodda inceleyebilirsiniz **çağrı yığını** penceresini açın ve diğer windows. Örneğin, bir kaynak kodunu görüntülemek için bir çağrı yığını çerçevesi çift tıklayarak veya **ayrıştırılmış** penceresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durumları hata ayıklayıcısı ile yönetme](../debugger/managing-exceptions-with-the-debugger.md)