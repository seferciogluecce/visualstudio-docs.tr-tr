---
title: Bir alan özelliğine Visual Studio'da yeniden düzenleme
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.csharp.refactoring.encapsulatefield
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 0c6594521774ca7e4fe91bc47776c4f0c4a489a9
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942926"
---
# <a name="encapsulate-a-field-refactoring"></a>Yeniden düzenleme alanı kapsülle

Bu yeniden düzenleme için geçerlidir:

- C#

- Visual Basic

**Ne:** alana bir özellikte açın ve yeni oluşturulan özelliği kullanmak için bu alanın tüm kullanımları güncelleştirme olanak tanır.

**Ne zaman:** bir özellikte alandan ve bu alanın tüm başvurularını güncelleştirmek istediğiniz.

**Neden:** bir alan diğer sınıflar erişim vermek istediğiniz, ancak söz konusu sınıfın doğrudan erişimine sahip olmasını istemiyorsanız.  Bir özellik alanı sarmalama tarafından örneğin atanan değerin doğrulamak için kod yazabilirsiniz.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Vurgulama veya yalıtılacak alanın adını metin imleci yerleştirin:

   - C# İÇİN:

       ![Vurgulanan kodu:C#](media/encapsulate-highlight-cs.png)

   - Visual Basic:

       ![Vurgulanmış kodu - Visual Basic](media/encapsulate-highlight-vb.png)

2. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
      - Tuşuna **Ctrl + R**, ardından **Ctrl + E**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
      - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yeniden düzenlemeler** menüsü ya da seçin **kapsülleme alanı** girişi önizleme penceresi açılır.
   - **Fare**
      - Seçin **Düzenle > yeniden düzenleyin > alanı Yalıt**.
      - Kod sağ tıklayın, **hızlı Eylemler ve yeniden düzenlemeler** menüsü ya da seçin **kapsülleme alanı** girişi önizleme penceresi açılır.

   Seçim | Açıklama
   --------- | -----------
   **Alanı kapsülle (ve özellik kullan)** | Alan özelliğine sahip kapsüller ve oluşturulan özellik kullanılacak alanın tüm kullanımları güncelleştirir
   **Alanı kapsülle (ancak yine de alan kullan)** | Alan özelliğine sahip saklar, ancak alanın tüm kullanımları dokunulmadan kalır

   Özelliği oluşturulur ve seçtiyseniz alanına yapılan başvurular güncelleştirilir.

   > [!TIP]
   > Kullanım **değişiklik önizlemesi** bağlantıyı açılan pencerede [sonucu görmek için](../../ide/preview-changes.md) kendisine gerçekleştirmeden önce.

   - C# İÇİN:

      ![Özellik sonucu kapsülleyen-C#](media/encapsulate-result-cs.png)

   - Visual Basic:

      ![Özellik sonucu - Visual Basic yalıtma](media/encapsulate-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)