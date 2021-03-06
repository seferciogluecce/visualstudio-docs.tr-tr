---
title: Eski dil hizmetinde Ayraç eşleştirme | Microsoft Docs
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
- brace matching
- language services [managed package framework], brace matching
ms.assetid: 4e3d0a70-f22f-49dd-92d8-edf48ab62b52
caps.latest.revision: 28
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7742b54b69cea8d1f814a4ac4fd8cc190dfe2b99
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49265063"
---
# <a name="brace-matching-in-a-legacy-language-service"></a>Eski Dil Hizmetinde Ayraç Eşleştirme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ayraç eşleştirme ayraçlar ve küme ayraçlarının gibi birlikte gerçekleşmesi gereken dil öğelerini izleme Geliştirici yardımcı olur. Bir geliştirici bir kapanış ayracı girdiğinde, açılış ayracı vurgulanır.  
  
 Çiftleri ve Üçlü adlı iki veya üç birlikte bulunan öğelerin eşleşebilir. Üçlü dizisini üç birlikte bulunan öğeleri kümesidir. Örneğin, C# ' ta `foreach` deyimi bir Üçlü forms: "`foreach()`","`{`", ve "`}`". Kapanış küme ayracı yazıldığında, tüm üç öğe vurgulanır.  
  
 Eski dil Hizmetleri bir VSPackage'ı bir parçası olarak uygulanır, ancak dil hizmeti özellikleri uygulamak için daha yeni MEF uzantıları kullanmaktır. Ayraç eşleştirme uygulamak için en yeni yolu hakkında daha fazla bilgi için bkz: [izlenecek yol: eşleşen küme ayraçlarını görüntüleme](../../extensibility/walkthrough-displaying-matching-braces.md).  
  
> [!NOTE]
>  Yeni bir düzenleyici API hemen kullanmaya başlamak öneririz. Bu dil hizmetinizin performansını ve yeni düzenleyici özellikleri yararlanmanıza olanak tanır.  
  
 <xref:Microsoft.VisualStudio.Package.AuthoringSink> Sınıf hem çiftleri destekler ve ile triples <xref:Microsoft.VisualStudio.Package.AuthoringSink.MatchPair%2A> ve <xref:Microsoft.VisualStudio.Package.AuthoringSink.MatchTriple%2A> yöntemleri.  
  
## <a name="implementation"></a>Uygulama  
 Dildeki tüm eşleşen öğeleri tanımlamak ve ardından tüm eşleşen çiftlerini bulmak dil hizmeti gerekiyor. Bu uygulama tarafından genellikle gerçekleştirilir <xref:Microsoft.VisualStudio.Package.IScanner> eşleşen dil ve ardından kullanarak algılamak için <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> öğelerle eşleme için yöntemi.  
  
 <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Satır simgeleştirin ve hemen önce giriş işaretini bir belirteç döndürecek tarayıcı yöntemini çağırır. Tarayıcı dil bir öğe çifti tetikleyici belirteç değerini ayarlayarak bulundu belirtir <xref:Microsoft.VisualStudio.Package.TokenTriggers> geçerli belirteç üzerinde. <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Yöntem çağrılarını <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> sırayla çağıran yöntemi <xref:Microsoft.VisualStudio.Package.LanguageService.BeginParse%2A> ayrıştırma neden değeriyle yöntemi <xref:Microsoft.VisualStudio.Package.ParseReason> eşleşen dil öğesi bulunamıyor. Eşleşen dil öğesi bulunduğunda, her iki öğe vurgulanır.  
  
 Nasıl bir küme ayracı yazma küme ayracı vurgulayarak tetikleyen bir tam açıklaması için "Örnek ayrıştırma işlemi" bölümüne bakın. [eski dil hizmeti ayrıştırıcısı ve tarayıcısı](../../extensibility/internals/legacy-language-service-parser-and-scanner.md).  
  
## <a name="enabling-support-for-brace-matching"></a>Ayraç eşleştirme için desteğini etkinleştirme  
 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> Özniteliği ayarlayabilirsiniz `MatchBraces`, `MatchBracesAtCaret`, ve `ShowMatchingBrace` karşılık gelen özelliklerini ayarlayın parametreleri adlı <xref:Microsoft.VisualStudio.Package.LanguagePreferences> sınıfı. Dil tercihi özellikleri de kullanıcı tarafından ayarlanabilir.  
  
|Kayıt defteri girdisi|Özellik|Açıklama|  
|--------------------|--------------|-----------------|  
|`MatchBraces`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableMatchBraces%2A>|Etkinleştirir Ayraç eşleştirme|  
|`MatchBracesAtCaret`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableMatchBracesAtCaret%2A>|Etkinleştirir küme ayracı giriş işaretini eşleşen taşır.|  
|`ShowMatchingBrace`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A>|Eşleşen Ayraca vurgular.|  
  
## <a name="matching-conditional-statements"></a>Eşleşen koşullu deyimler  
 Koşullu ifadeler gibi eşleşebilir `if`, `else if`, ve `else`, veya `#if`, `#elif`, `#else`, `#endif`, ayırıcısı olarak aynı şekilde. Öğesinin alt sınıfı için <xref:Microsoft.VisualStudio.Package.AuthoringSink> sınıfı ve metin ekleyebileceğiniz bir yöntem yayılan öğeleri eşleşen iç diziyi sınırlayıcıları yanı sıra sağlayın.  
  
## <a name="setting-the-trigger"></a>Tetikleyiciyi ayarlama  
 Aşağıdaki örnek, eşleşen parantez, küme ayracı ve köşeli ayraçlar ve tarayıcıda için tetikleyiciyi ayarlama nasıl gösterir. <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Metodunda <xref:Microsoft.VisualStudio.Package.Source> sınıfı tetikleyici algılar ve (Bu konudaki "eşleşme bulma" bölümüne bakın) eşleşen bir çift bulmak için ayrıştırıcı çağırır. Bu örnek yalnızca tanım amaçlıdır. Tarayıcınız bir yöntem içerdiğini varsayar `GetNextToken` tanımlar ve bir metin satırından belirteçleri döndürür.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestScanner : IScanner  
    {  
        private const string braces = "()[]{}";  
        private Lexer lex;  
  
        public bool ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo,  
                                                   ref int state)  
        {  
            bool foundToken = false;  
            string token = lex.GetNextToken();  
            if (token != null)  
            {  
                foundToken = true;  
                char firstChar = token[0];  
                if (Char.IsPunctuation(firstChar) && token.Length > 0)  
                {  
                    if (braces.IndexOf(firstChar) != -1)  
                    {  
                        tokenInfo.Trigger = TokenTriggers.MatchBraces;  
                    }  
                }  
            }  
            return foundToken;  
        }  
```  
  
## <a name="matching-the-braces"></a>Ayraç eşleştirme  
 Dil öğeleri {}, () ve [] ile eşleşen ve bunların yayılma için ekleme için basitleştirilmiş bir örnek <xref:Microsoft.VisualStudio.Package.AuthoringSink> nesne. Bu yaklaşım, kaynak kodu ayrıştırma için önerilen bir yaklaşım değildir; Bunu yalnızca tanım amaçlıdır.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class Parser  
    {  
         private IList<TextSpan[]> m_braces;  
         public IList<TextSpan[]> Braces  
         {  
             get { return m_braces; }  
         }  
         private void AddMatchingBraces(TextSpan braceSpan1, TextSpan braceSpan2)  
         {  
             if IsMatch(braceSpan1, braceSpan2)  
                 m_braces.Add(new TextSpan[] { braceSpan1, braceSpan2 });  
         }  
  
         private bool IsMatch(TextSpan braceSpan1, TextSpan braceSpan2)  
         {  
             //definition for matching here  
          }  
    }  
  
    public class TestLanguageService : LanguageService  
    {  
         Parser parser = new Parser();  
         Source source = (Source) this.GetSource(req.FileName);  
  
         private AuthoringScope ParseSource(ParseRequest req)  
         {  
             if (req.Sink.BraceMatching)  
             {  
                 if (req.Reason==ParseReason.MatchBraces)  
                 {  
                     foreach (TextSpan[] brace in parser.Braces)  
                     {  
                         req.Sink.MatchPair(brace[0], brace[1], 1);  
                     }  
                 }  
             }  
             return new TestAuthoringScope();  
         }  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti özellikleri](../../extensibility/internals/legacy-language-service-features1.md)   
 [Eski Dil Hizmeti Ayrıştırıcısı ve Tarayıcısı](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)

