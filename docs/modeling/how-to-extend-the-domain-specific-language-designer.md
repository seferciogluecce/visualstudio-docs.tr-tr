---
title: "Nasıl yapılır: etki alanına özgü dil Tasarımcısı genişletmek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa807f1b-2780-491e-925b-abbfd31b2bfa
caps.latest.revision: "9"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 44b3ea3d3997ac781b02220316810f00826f2beb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-extend-the-domain-specific-language-designer"></a>Nasıl yapılır: Etki Alanına Özgü Dil Tasarımcısını Genişletme
Uzantıları DSL tanımları düzenlemek için kullandığınız Tasarımcı yapabilirsiniz. Menü komutları eklenmesi için işleyiciler sürükleyin ve hareketlerini ve belirli türlerdeki değerleri ilişkileri değiştirdiğinizde tetiklenen kuralları çift ekleme yapabileceğiniz uzantı türleri. Uzantılar bir Visual Studio Tümleştirme Uzantısı (VSIX olarak) paketlenir ve diğer kullanıcılara dağıtılacak.  
  
 Örnek kod ve bu özellik hakkında daha fazla bilgi için Visual Studio bkz [Görselleştirme ve modelleme SDK (VMSDK) Web sitesini](http://go.microsoft.com/fwlink/?LinkID=186128).  
  
## <a name="setting-up-the-solution"></a>Çözüm ayarlama  
 Uzantınızı kodunu içeren bir proje ve proje aktarır VSIX proje ayarlayın. Çözümünüzü aynı VSIX dahil diğer projeler içerebilir.  
  
#### <a name="to-create-a-dsl-designer-extension-solution"></a>Bir DSL Tasarımcısı uzantısı çözümü oluşturmak için  
  
1.  Sınıf kitaplığı proje şablonu kullanarak yeni bir proje oluşturun. İçinde **yeni proje** iletişim kutusu, tıklatın **Visual C#** ve orta penceresinde tıklatın ardından **sınıf kitaplığı**.  
  
     Bu proje uzantılarınızın kodunu içerir.  
  
2.  VSIX proje şablonunu kullanarak yeni bir proje oluşturun. İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#**, tıklatın **genişletilebilirlik**ve ardından Orta penceresi seçin **VSIX proje**.  
  
     Seçin **çözüme eklemek**.  
  
     Source.extension.vsixmanifest VSIX bildirim Düzenleyicisi'nde açar.  
  
3.  İçerik alanının üstünde tıklatın **İçerik Ekle**.  
  
4.  İçinde **İçerik Ekle** iletişim kutusu, kümesi **bir içerik türü seçin** için **MEF Bileşeni**ve **proje** sınıf kitaplığını projenize.  
  
5.  Tıklatın **sürümleri seçin** emin olun **Visual Studio Enterprise** denetlenir.  
  
6.  VSIX proje çözüm başlangıç projesi olduğundan emin olun.  
  
7.  Sınıf kitaplığı projesinde aşağıdaki derlemelerine başvurular ekleyin:  
  
     Microsoft.VisualStudio.CoreUtility  
  
     Microsoft.VisualStudio.Modeling.Sdk.11.0  
  
     Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0  
  
     Microsoft.VisualStudio.Modeling.Sdk.DslDefinition.11.0  
  
     Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0  
  
     System.ComponentModel.Composition  
  
     System.Drawing  
  
     System.Drawing.Design  
  
     System.Windows.Forms  
  
## <a name="testing-and-deployment"></a>Test ve dağıtım  
 Tüm uzantıların bu konudaki sınamak için yapı ve çözümü çalıştırın. Deneysel örneği [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] açar. Bu örnekte, bir DSL çözümü açın. DslDefinition diyagramı düzenleyin. Uzantısı davranışının görülebilir.  
  
 Uzantıları için ana dağıtmak için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ve diğer bilgisayarlar için aşağıdaki adımları izleyin:  
  
1.  VSIX projenizde depo VSIX yükleme dosyasını bulmak\\*\\\*.vsix  
  
2.  Bu dosyayı hedef bilgisayara kopyalayın ve ardından Windows Gezgini (veya dosya Gezgini'ni) çift tıklayın.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Uzantı Yöneticisi'ni açar uzantısı yüklü olduğunu doğrulamak için.  
  
 Uzantıyı kaldırmak için şu adımları izleyin:  
  
1.  içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], **Araçları** menüsünde tıklatın **Uzantı Yöneticisi**.  
  
2.  Uzantıyı seçin ve silin.  
  
## <a name="adding-a-shortcut-menu-command"></a>Bir kısayol menü komutu ekleme  
 Bir kısayol menü komutu DSL Tasarımcısı yüzeyinde veya DSL Gezgini penceresinde görünür yapmak için aşağıdaki benzeyen bir sınıf yazın.  
  
 Sınıf uygulamalıdır `ICommandExtension` ve öznitelik olmalıdır `DslDefinitionModelCommandExtension`.  
  
```  
using System.Collections.Generic;  
using System.ComponentModel.Composition;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.DslDefinition;  
using Microsoft.VisualStudio.Modeling.DslDefinition.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.DslDesigner;  
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;  
  
namespace Fabrikam.SimpleDslDesignerExtension  
{  
  /// <summary>  
  /// Command extending the DslDesigner.  
  /// </summary>  
  [DslDefinitionModelCommandExtension]   
  public class MyDslDesignerCommand : ICommandExtension  
  {  
    /// <summary>  
    /// Selection Context for this command  
    /// </summary>  
    [Import]  
    IVsSelectionContext SelectionContext { get; set; }  
  
    /// <summary>  
    /// Is the command visible and active?  
    /// This is called when the user right-clicks.  
    /// </summary>  
    public void QueryStatus(IMenuCommand command)  
    {  
      command.Visible = true;  
      // Is there any selected DomainClasses in the Dsl explorer?  
      command.Enabled =   
        SelectionContext.AtLeastOneSelected<DomainClass>();  
  
      // Is there any selected ClassShape on the design surface?  
      command.Enabled |=   
        (SelectionContext.GetCurrentSelection<ClassShape>()  
                .Count() > 0);  
    }  
    /// <summary>  
    /// Executes the command   
    /// </summary>  
    /// <param name="command">Command initiating this action</param>  
    public void Execute(IMenuCommand command)  
    {  
      ...  
    }  
    /// <summary>  
    /// Label for the command  
    /// </summary>  
    public string Text  
    {  
      get { return "My Command"; }  
    }  
  }  
}  
```  
  
## <a name="handling-mouse-gestures"></a>Fare hareketleri işleme  
 Menü komutunu kodu için kod benzer.  
  
```  
[DslDefinitionModelGestureExtension]  
 class MouseGesturesExtensions : IGestureExtension  
 {  
  /// <summary>  
  /// Double-clicking on a shape representing a Domain model element displays this model element in a dialog box  
  /// </summary>  
  /// <param name="targetElement">Shape element on which the user has clicked</param>  
  /// <param name="diagramPointEventArgs">event args for this double-click</param>  
  public void OnDoubleClick(ShapeElement targetElement,  
       DiagramPointEventArgs diagramPointEventArgs)  
  {  
   ModelElement modelElement = PresentationElementHelper.  
        GetDslDefinitionModelElement(targetElement);  
   if (modelElement != null)  
   {  
    MessageBox.Show(string.Format(  
      "Double clicked on {0}", modelElement.ToString()),   
      "Model element double-clicked");  
   }  
  }  
  
  /// <summary>  
  /// Tells if the DslDesigner can consume the to-be-dropped information  
  /// </summary>  
  /// <param name="targetMergeElement">Shape on which we try to drop</param>  
  /// <param name="diagramDragEventArgs">Drop event</param>  
  /// <returns><c>true</c> if we can consume the to be dropped data, and <c>false</c> otherwise</returns>  
  public bool CanDragDrop(ShapeElement targetMergeElement,  
        DiagramDragEventArgs diagramDragEventArgs)  
  {  
   if (diagramDragEventArgs.Data.GetDataPresent(DataFormats.FileDrop))  
   {  
    diagramDragEventArgs.Effect = DragDropEffects.Copy;  
    return true;  
   }  
   return false;  
  }  
  
  /// <summary>  
  /// Processes the drop by displaying the dropped text  
  /// </summary>  
  /// <param name="targetMergeElement">Shape on which we dropped</param>  
  /// <param name="diagramDragEventArgs">Drop event</param>  
  public void OnDragDrop(ShapeElement targetDropElement, DiagramDragEventArgs diagramDragEventArgs)  
  {  
   if (diagramDragEventArgs.Data.GetDataPresent(DataFormats.FileDrop))  
   {  
    string[] droppedFiles =   
      diagramDragEventArgs.Data.  
               GetData(DataFormats.FileDrop) as string[];  
    MessageBox.Show(string.Format("Dropped text {0}",  
        string.Join("\r\n", droppedFiles)), "Dropped Text");  
   }  
  }  
 }  
```  
  
## <a name="responding-to-value-changes"></a>Değişiklikleri değer yanıtlama  
 Bu işleyicinin düzgün çalışması için bir etki alanı modeli gerekir. Basit etki alanı modeli sunuyoruz.  
  
```  
using System.Diagnostics;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.DslDefinition;  
namespace Fabrikam.SimpleDslDesignerExtension  
{  
  /// <summary>  
  /// Rule firing when the type of a domain model property is changed. The change is displayed  
  /// in the debugger (Output window of the Visual Studio instance debugging this extension)  
  /// </summary>  
  [RuleOn(typeof(PropertyHasType))]  
  public class DomainPropertyTypeChangedRule : RolePlayerChangeRule  
  {  
    /// <summary>  
    /// Method called when the Type of a Domain Property   
    /// is changed by the user in a DslDefinition  
    /// </summary>  
    /// <param name="e"></param>  
    public override void RolePlayerChanged(RolePlayerChangedEventArgs e)  
    {  
      // We are only interested in the type  
      if (e.DomainRole.Id == PropertyHasType.TypeDomainRoleId)  
      {  
        PropertyHasType relationship =   
           e.ElementLink as PropertyHasType;  
        DomainType newType = e.NewRolePlayer as DomainType;  
        DomainType oldType = e.OldRolePlayer as DomainType;  
        DomainProperty property = relationship.Property;  
  
         // We write about the Type change in the debugguer  
        Debug.WriteLine(string.Format("The type of the Domain property '{0}' of domain class '{1}' changed from '{2}' to '{3}'",  
          property.Name,  
          property.Class.Name,  
          oldType.GetFullName(false),  
          newType.GetFullName(false))  
} }  }  );  
```  
  
 Aşağıdaki kod basit bir modeli uygular. Yer tutucu değiştirmek için yeni bir GUID oluşturun.  
  
```  
using System;  
using System.ComponentModel.Composition;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.DslDefinition;  
namespace Fabrikam.SimpleDslDesignerExtension  
{  
    /// <summary>  
    /// Simplest possible domain model   
    /// needed only for extension rules.   
    /// </summary>  
    [DomainObjectId(SimpleDomainModelExtension.DomainModelId)]  
    public class SimpleDomainModelExtension : DomainModel  
    {  
        // Id of this domain model extension   
        // Please replace this with a new GUID:  
        public const string DomainModelId =   
                  "00000000-0000-0000-0000-000000000000";  
  
        /// <summary>  
        /// Constructor for the domain model extension  
        /// </summary>  
        /// <param name="store">Store in which the domain model will be loaded</param>  
        public SimpleDomainModelExtension(Store store)  
            : base(store, new Guid(SimpleDomainModelExtension.DomainModelId))  
        {  
  
        }  
  
        /// <summary>  
        /// Rules brought by this domain model extension  
        /// </summary>  
        /// <returns></returns>  
        protected override System.Type[] GetCustomDomainModelTypes()  
        {  
            return new Type[] {  
                     typeof(DomainPropertyTypeChangedRule)  
                              };  
        }  
    }  
  
    /// <summary>  
    /// Provider for the DomainModelExtension  
    /// </summary>  
    [Export(typeof(DomainModelExtensionProvider))]    [ProvidesExtensionToDomainModel(typeof(DslDefinitionModelDomainModel))]  
    public class SimpleDomainModelExtensionProvider   
          : DomainModelExtensionProvider  
    {  
        /// <summary>  
        /// Extension model type  
        /// </summary>  
        public override Type DomainModelType  
        {  
            get  
            {  
                return typeof(SimpleDomainModelExtension);  
            }  
        }  
  
    }  
}  
```