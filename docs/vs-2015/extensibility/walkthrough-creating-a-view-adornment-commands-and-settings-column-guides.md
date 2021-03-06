---
title: 'İzlenecek yol: görünüm kenarlığı, komutlar ve ayarlar (sütun kılavuzları) oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a2df0a3-42da-4f7b-996f-ee16a35ac922
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9e31588850d47276d63bda724e61e502c38a4575
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49862326"
---
# <a name="walkthrough-creating-a-view-adornment-commands-and-settings-column-guides"></a>İzlenecek Yol: Görünüm Kenarlığı, Komutlar ve Ayarlar (Sütun Kılavuzları) Oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio metin/Kod Düzenleyicisi komutları ve görünüm efektleriyle genişletebilirsiniz.  Bu konuda, bir popüler uzantısı özelliği, sütun kılavuzları ile çalışmaya başlama işlemini göstermektedir.  Sütun, kodunuzda belirli sütun genişliklerini yönetmenize yardımcı olmak için metin düzenleyici görünümünde görsel olarak ışık çizgileri kılavuzlardır.  Özel olarak biçimlendirilmiş kod belgeleri, blog gönderileri, dahil etmek veya hata raporları örnekleri için önemli olabilir.  
  
 Bu izlenecek yolda yapacaklarınız:  
  
- VSIX projesi oluşturun  
  
- Bir düzenleyici görünüm kenarlığı Ekle  
  
- Kaydetme ve (çizim sütun kılavuzları ve bunların renk için) ayarları almak için destek eklendi  
  
- Komutları eklendi (sütun kılavuzları Ekle/Kaldır, kendi rengi değiştirme)  
  
- Düzen menüsü ve metin belgesi bağlam menüleri komutları koyun  
  
- Visual Studio komut penceresinde komutlar yürütmesini desteği eklendi  
  
  Bu Visual Studio Galerisi sütun kılavuzları özelliğiyle sürümünü deneyebilirsiniz[uzantısı](https://visualstudiogallery.msdn.microsoft.com/da227a0b-0e31-4a11-8f6b-3a149cf2e459?SRC=Home).  
  
  **Not**: Bu kılavuzda visual studio uzantı şablonları tarafından oluşturulan bazı dosyalara bir sürü kod yapıştırın, ancak yakında bu kılavuzda github'da diğer uzantı örnekleriyle tamamlanmış bir çözümdür başvuracaktır.  Tamamlanan kodu generictemplate simgeler kullanmak yerine gerçek komut simgeleri sahip, biraz farklıdır.  
  
## <a name="getting-started"></a>Başlarken  
 Visual Studio 2015'ten başlayarak, size Visual Studio SDK İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yi daha sonra yükleyebilirsiniz. Daha fazla bilgi için [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="setting-up-the-solution"></a>Çözümünü ayarlama  
 İlk bir VSIX projesi oluşturun, bir düzenleyici görünüm kenarlığı ekleyin ve ardından (komut sahibi VSPackage ekleyen) bir komut ekleyin.  Temel mimari aşağıdaki gibidir:  
  
- Oluşturur bir metin görünümünü oluşturma dinleyici sahip bir `ColumnGuideAdornment` görünüm başına nesne.  Bu nesne görünümü değiştirme hakkında olayları dinleyen veya ayarları değiştirme, güncelleştirme veya yeniden sütun gerektiği şekilde kılavuzluk eder.  
  
- Var olan bir `GuidesSettingsManager` Visual Studio ayarları depolamadan yazma ve okuma işler.  Ayarlar Yöneticisi ayrıca kullanıcı komutları destek ayarları güncelleştirmek için işlemleri vardır (sütun ekleme, sütun kaldırmak, rengini değiştirme).  
  
- Kullanıcı komutları varsa gerekli olan bir VSIP paket, ancak yalnızca komutlar uygulama nesnesini başlatır Demirbaş kod değil.  
  
- Var olan bir `ColumnGuideCommands` uygulayan kullanıcı komutları ve komutlar için komut işleyicileri'kurmak kancaları nesne .vsct dosyası içinde bildirilmiş.  
  
  **VSIX**.  Kullanım **dosya &#124; yeni...** bir proje oluşturmak için komutu.  Sol Gezinti Bölmesi'nde genişletilebilirlik düğümünde C# ' ı seçin ve **VSIX projesi** sağ bölmede.  ColumnGuides adını girin ve seçin **Tamam** projeyi oluşturmak için.  
  
  **Kenarlığı görüntüleyin**.  Çözüm Gezgini'nde proje düğümüne sağ işaretçi düğmesine basın.  Seçin **ekleme &#124; yeni öğe...** Yeni bir görünüm kenarlığı öğe eklemek için komutu.  Seçin **genişletilebilirlik &#124; Düzenleyicisi** sol gezinti bölmesinde seçin **Düzenleyicisi Görünüm penceresi kenarlığı** sağ bölmede.  Öğe adı ColumnGuideAdornment adı girin ve seçin **Ekle** ekleyin.  
  
  Proje (yanı sıra başvuruları ve benzeri) Bu öğe şablonu eklenen iki dosya görebilirsiniz: ColumnGuideAdornment.cs ve ColumnGuideAdornmentTextViewCreationListener.cs.  Şablonlar, yalnızca görünümünde mor renkli bir dikdörtgen çizin.  Aşağıda birkaç görünüm oluşturma dinleyici satırları değiştirin ve ColumnGuideAdornment.cs içeriğini değiştirin.  
  
  **Komutları**.  Çözüm Gezgini'nde proje düğümüne sağ işaretçi düğmesine basın.  Seçin **ekleme &#124; yeni öğe...** Yeni bir görünüm kenarlığı öğe eklemek için komutu.  Seçin **genişletilebilirlik &#124; VSPackage** sol gezinti bölmesinde seçin **özel komut** sağ bölmede.  Öğe adı ColumnGuideCommands adı girin ve seçin **Ekle** ekleyin.  Birkaç başvurulara ek komutlar ve paket ekleme ColumnGuideCommands.cs ColumnGuideCommandsPackage.cs ve ColumnGuideCommandsPackage.vsct eklendi.  Aşağıdaki komutlar tanımlaması ve ilk ve son dosyaların içeriğini yerini alır.  
  
## <a name="setting-up-the-text-view-creation-listener"></a>Metin görünümü oluşturma dinleyici ayarlama  
 ColumnGuideAdornmentTextViewCreationListener.cs düzenleyicide açın.  Bu kod, her Visual Studio metin görünümler oluşturur için bir işleyici uygular.  İşleyici görünümün özelliklere bağlı olarak ne zaman çağrıldığını denetleyen öznitelikleri vardır.  
  
 Kod ayrıca kenarlığı katman bildirmeniz gerekir.  Düzenleyici güncelleştirmeler görünümleri, görünüme ait kenarlığı katmanları alır ve buradan kenarlığı öğeleri alır.  Başkalarının göre katmanınızdaki öznitelikleriyle sıralama bildirebilirsiniz.  Şu satırı değiştirin:  
  
```csharp  
[Order(After = PredefinedAdornmentLayers.Caret)]  
```  
  
 şu iki satırı ile:  
  
```csharp  
[Order(Before = PredefinedAdornmentLayers.Text)]  
[TextViewRole(PredefinedTextViewRoles.Document)]  
```  
  
 Kenarlığı katman declare öznitelikleri içinde değiştirdiğiniz satırı grubudur.   İlk satırı sütun kılavuz çizgileri göründüğü yalnızca değişiklikler değiştirildi.  "Önce" Görünüm içindeki metni arkasına veya aşağıdaki metni göründükleri anlamına gelir. satırlar çizme.  İkinci satır, sütun kılavuzu kenarlıklar, bir belge kavramı uyan metin varlıklar için geçerlidir, ancak, kenarlığı, örneğin, yalnızca iş için düzenlenebilir metin bildirebilirsiniz bildirir.  Daha fazla bilgi bulunmaktadır [dil hizmeti ve düzenleyici uzantı noktaları](../extensibility/language-service-and-editor-extension-points.md)  
  
## <a name="implementing-the-settings-manager"></a>Ayarları Yöneticisi uygulama  
 GuidesSettingsManager.cs içeriğini (aşağıda açıklanmıştır) aşağıdaki kodla değiştirin:  
  
```csharp  
using Microsoft.VisualStudio.Settings;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.Shell.Settings;  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows.Media;  
  
namespace ColumnGuides  
{  
    internal static class GuidesSettingsManager  
    {  
        // Because my code is always called from the UI thred, this succeeds.  
        internal static SettingsManager VsManagedSettingsManager =  
            new ShellSettingsManager(ServiceProvider.GlobalProvider);  
  
        private const int _maxGuides = 5;  
        private const string _collectionSettingsName = "Text Editor";  
        private const string _settingName = "Guides";  
        // 1000 seems reasonable since primary scenario is long lines of code  
        private const int _maxColumn = 1000;   
  
        static internal bool AddGuideline(int column)  
        {  
            if (! IsValidColumn(column))  
                throw new ArgumentOutOfRangeException(  
                    "column",  
                    "The paramenter must be between 1 and " + _maxGuides.ToString());  
            var offsets = GuidesSettingsManager.GetColumnOffsets();  
            if (offsets.Count() >= _maxGuides)  
                return false;  
            // Check for duplicates  
            if (offsets.Contains(column))  
                return false;  
            offsets.Add(column);  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, offsets);  
            return true;  
        }  
  
        static internal bool RemoveGuideline(int column)  
        {  
            if (!IsValidColumn(column))  
                throw new ArgumentOutOfRangeException(  
                    "column", "The paramenter must be between 1 and 10,000");  
            var columns = GuidesSettingsManager.GetColumnOffsets();  
            if (! columns.Remove(column))  
            {  
                // Not present.  Allow user to remove the last column   
                // even if they're not on the right column.  
                if (columns.Count != 1)  
                    return false;  
  
                columns.Clear();  
            }  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, columns);  
            return true;  
        }  
  
        static internal bool CanAddGuideline(int column)  
        {  
            if (!IsValidColumn(column))  
                return false;  
            var offsets = GetColumnOffsets();  
            if (offsets.Count >= _maxGuides)  
                return false;  
            return ! offsets.Contains(column);  
        }  
  
        static internal bool CanRemoveGuideline(int column)  
        {  
            if (! IsValidColumn(column))  
                return false;  
            // Allow user to remove the last guideline regardless of the column.  
            // Okay to call count, we limit the number of guides.  
            var offsets = GuidesSettingsManager.GetColumnOffsets();  
            return offsets.Contains(column) || offsets.Count() == 1;  
        }  
  
        static internal void RemoveAllGuidelines()  
        {  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, new int[0]);  
        }  
  
        private static bool IsValidColumn(int column)  
        {  
            // zero is allowed (per user request)  
            return 0 <= column && column <= _maxColumn;  
        }  
  
        // This has format "RGB(<int>, <int>, <int>) <int> <int>...".  
        // There can be any number of ints following the RGB part,   
        // and each int is a column (char offset into line) where to draw.  
        static private string _guidelinesConfiguration;  
        static private string GuidelinesConfiguration  
        {  
            get  
            {  
                if (_guidelinesConfiguration == null)  
                {  
                    _guidelinesConfiguration =   
                        GetUserSettingsString(  
                            GuidesSettingsManager._collectionSettingsName,  
                            GuidesSettingsManager._settingName)  
                        .Trim();  
                }  
                return _guidelinesConfiguration;  
            }  
  
            set  
            {  
                if (value != _guidelinesConfiguration)  
                {  
                    _guidelinesConfiguration = value;  
                    WriteUserSettingsString(  
                        GuidesSettingsManager._collectionSettingsName,  
                        GuidesSettingsManager._settingName, value);  
                    // Notify ColumnGuideAdornments to update adornments in views.  
                    var handler = GuidesSettingsManager.SettingsChanged;  
                    if (handler != null)  
                        handler();  
                }  
            }  
        }  
  
        internal static string GetUserSettingsString(string collection, string setting)  
        {  
            var store = GuidesSettingsManager  
                            .VsManagedSettingsManager  
                            .GetReadOnlySettingsStore(SettingsScope.UserSettings);  
            return store.GetString(collection, setting, "RGB(255,0,0) 80");  
        }  
  
        internal static void WriteUserSettingsString(string key, string propertyName,  
                                                     string value)  
        {  
            var store = GuidesSettingsManager  
                            .VsManagedSettingsManager  
                            .GetWritableSettingsStore(SettingsScope.UserSettings);  
            store.CreateCollection(key);  
            store.SetString(key, propertyName, value);  
        }  
  
        // Persists settings and sets property with side effect of signaling  
        // ColumnGuideAdornments to update.  
        static private void WriteSettings(Color color, IEnumerable<int> columns)  
        {  
            string value = ComposeSettingsString(color, columns);  
            GuidelinesConfiguration = value;  
        }  
  
        private static string ComposeSettingsString(Color color,  
                                                    IEnumerable<int> columns)  
        {  
            StringBuilder sb = new StringBuilder();  
            sb.AppendFormat("RGB({0},{1},{2})", color.R, color.G, color.B);  
            IEnumerator<int> columnsEnumerator = columns.GetEnumerator();  
            if (columnsEnumerator.MoveNext())  
            {  
                sb.AppendFormat(" {0}", columnsEnumerator.Current);  
                while (columnsEnumerator.MoveNext())  
                {  
                    sb.AppendFormat(", {0}", columnsEnumerator.Current);  
                }  
            }  
            return sb.ToString();  
        }  
  
        // Parse a color out of a string that begins like "RGB(255,0,0)"  
        static internal Color GuidelinesColor  
        {  
            get  
            {  
                string config = GuidelinesConfiguration;  
                if (!String.IsNullOrEmpty(config) && config.StartsWith("RGB("))  
                {  
                    int lastParen = config.IndexOf(')');  
                    if (lastParen > 4)  
                    {  
                        string[] rgbs = config.Substring(4, lastParen - 4).Split(',');  
  
                        if (rgbs.Length >= 3)  
                        {  
                            byte r, g, b;  
                            if (byte.TryParse(rgbs[0], out r) &&  
                                byte.TryParse(rgbs[1], out g) &&  
                                byte.TryParse(rgbs[2], out b))  
                            {  
                                return Color.FromRgb(r, g, b);  
                            }  
                        }  
                    }  
                }  
                return Colors.DarkRed;  
            }  
  
            set  
            {  
                WriteSettings(value, GetColumnOffsets());  
            }  
        }  
  
        // Parse a list of integer values out of a string that looks like  
        // "RGB(255,0,0) 1, 5, 10, 80"  
        static internal List<int> GetColumnOffsets()  
        {  
            var result = new List<int>();  
            string settings = GuidesSettingsManager.GuidelinesConfiguration;  
            if (String.IsNullOrEmpty(settings))  
                return new List<int>();  
  
            if (!settings.StartsWith("RGB("))  
                return new List<int>();  
  
            int lastParen = settings.IndexOf(')');  
            if (lastParen <= 4)  
                return new List<int>();  
  
            string[] columns = settings.Substring(lastParen + 1).Split(',');  
  
            int columnCount = 0;  
            foreach (string columnText in columns)  
            {  
                int column = -1;  
                // VS 2008 gallery extension didn't allow zero, so per user request ...  
                if (int.TryParse(columnText, out column) && column >= 0)  
                {  
                    columnCount++;  
                    result.Add(column);  
                    if (columnCount >= _maxGuides)  
                        break;  
                }  
            }  
            return result;  
        }  
  
        // Delegate and Event to fire when settings change so that ColumnGuideAdornments   
        // can update.  We need nothing special in this event since the settings manager   
        // is statically available.  
        //  
        internal delegate void SettingsChangedHandler();  
        static internal event SettingsChangedHandler SettingsChanged;  
  
    }  
}  
  
```  
  
 Bu kod çoğunu yalnızca oluşturur ve ayrıştırmak için ayarları biçimi: "RGB (\<int >,\<int >,\<int >) \<int >, \<int >,...".  Son sütun kılavuzları istediğiniz bir tabanlı sütunları tamsayılardır.  Sütun kılavuzları uzantısı tek ayar değer dizesi, tüm ayarlarını yakalar.  
  
 Bazı bölümlerini vurgulama değer kod vardır.  Aşağıdaki kod satırını ayarları depolama alanı için Visual Studio yönetilen sarmalayıcı alır.  Çoğunlukla, bunu Windows kayıt defteri soyutlar, ancak bu API, depolama mekanizması bağımsızdır.  
  
```csharp  
internal static SettingsManager VsManagedSettingsManager =  
    new ShellSettingsManager(ServiceProvider.GlobalProvider);  
```  
  
 Visual Studio ayarları depolama, tüm ayarlarını benzersiz olarak tanımlanabilmesi için kategorisi tanımlayıcısı ve bir ayar tanımlayıcısı kullanır:  
  
```csharp  
private const string _collectionSettingsName = "Text Editor";  
private const string _settingName = "Guides";  
```  
  
 Kullanmak zorunda değil `“Text Editor”` kategori olarak adı ve istediğiniz her şeyi seçebilirsiniz.  
  
 İlk birkaç işlevi ayarlarını değiştirmek için giriş noktalarıdır.  Bunlar, sayısı izin verilen kılavuzları gibi üst düzey kısıtlamalar kontrol edin.  Bunlar çağrı `WriteSettings` ayarları dize ölçeklemesini ve özelliği ayarlar `GuideLinesConfiguration`.  Bu özelliğin ayarlanması kaydeder ayarları değeri etkinleşir ve Visual Studio ayarları deposu `SettingsChanged` tümünü güncelleştirmek için olay `ColumnGuideAdornment` nesneler, her bir metin görünümü ile ilişkilendirilmiş.  
  
 Birkaç vardır giriş noktası işlevlerin gibi `CanAddGuideline`, ayarları değiştirmek komutları uygulamak için kullanılır.  Visual Studio menü gösterir, bu sorgular komutu şu anda, onun adı nedir etkin olup olmadığını görmek için komutun uygulamalarında, vs.  Aşağıda, bu komutun uygulamalarında giriş noktaları denetime nasıl görürsünüz.  Bkz: [genişletme menüler ve komutlar](../extensibility/extending-menus-and-commands.md) komutlar hakkında daha fazla bilgi için.  
  
## <a name="implementing-the-columnguideadornment-class"></a>ColumnGuideAdornment sınıfı  
 `ColumnGuideAdornment` Kenarlıklar olabilir her metin görünümünü sınıfı örneği.  Bu sınıf görünümü değiştirme hakkında olayları dinleyen veya ayarları değiştirme, güncelleştirme veya yeniden sütun gerektiği şekilde kılavuzluk eder.  
  
 ColumnGuideAdornment.cs içeriğini (aşağıda açıklanmıştır) aşağıdaki kodla değiştirin:  
  
```csharp  
using System;  
using System.Windows.Media;  
using Microsoft.VisualStudio.Text.Editor;  
using System.Collections.Generic;  
using System.Windows.Shapes;  
using Microsoft.VisualStudio.Text.Formatting;  
using System.Windows;  
  
namespace ColumnGuides  
{  
    /// <summary>  
    /// Adornment class, one instance per text view that draws a guides on the viewport  
    /// </summary>  
    internal sealed class ColumnGuideAdornment  
    {  
        private const double _lineThickness = 1.0;  
        private IList<Line> _guidelines;  
        private IWpfTextView _view;  
        private double _baseIndentation;  
        private double _columnWidth;  
  
        /// <summary>  
        /// Creates editor column guidelines  
        /// </summary>  
        /// <param name="view">The <see cref="IWpfTextView"/> upon   
        /// which the adornment will be drawn</param>  
        public ColumnGuideAdornment(IWpfTextView view)  
        {  
            _view = view;  
            _guidelines = CreateGuidelines();  
            GuidesSettingsManager.SettingsChanged +=   
                new GuidesSettingsManager.SettingsChangedHandler(SettingsChanged);  
            view.LayoutChanged +=   
                new EventHandler<TextViewLayoutChangedEventArgs>(OnViewLayoutChanged);  
            _view.Closed += new EventHandler(OnViewClosed);  
        }  
  
        void SettingsChanged()  
        {  
            _guidelines = CreateGuidelines();  
            UpdatePositions();  
            AddGuidelinesToAdornmentLayer();  
        }  
  
        void OnViewClosed(object sender, EventArgs e)  
        {  
            _view.LayoutChanged -= OnViewLayoutChanged;  
            _view.Closed -= OnViewClosed;  
            GuidesSettingsManager.SettingsChanged -= SettingsChanged;  
        }  
  
        private bool _firstLayoutDone;  
  
        void OnViewLayoutChanged(object sender, TextViewLayoutChangedEventArgs e)  
        {  
            bool fUpdatePositions = false;  
  
            IFormattedLineSource lineSource = _view.FormattedLineSource;  
            if (lineSource == null)  
            {  
                return;  
            }  
            if (_columnWidth != lineSource.ColumnWidth)  
            {  
                _columnWidth = lineSource.ColumnWidth;  
                fUpdatePositions = true;  
            }  
            if (_baseIndentation != lineSource.BaseIndentation)  
            {  
                _baseIndentation = lineSource.BaseIndentation;  
                fUpdatePositions = true;  
            }  
            if (fUpdatePositions ||  
                e.VerticalTranslation ||  
                e.NewViewState.ViewportTop != e.OldViewState.ViewportTop ||  
                e.NewViewState.ViewportBottom != e.OldViewState.ViewportBottom)  
            {  
                UpdatePositions();  
            }  
            if (!_firstLayoutDone)  
            {  
                AddGuidelinesToAdornmentLayer();  
                _firstLayoutDone = true;  
            }  
        }  
  
        private static IList<Line> CreateGuidelines()  
        {  
            Brush lineBrush = new SolidColorBrush(GuidesSettingsManager.GuidelinesColor);  
            DoubleCollection dashArray = new DoubleCollection(new double[] { 1.0, 3.0 });  
            IList<Line> result = new List<Line>();  
            foreach (int column in GuidesSettingsManager.GetColumnOffsets())  
            {  
                Line line = new Line()  
                {  
                    // Use the DataContext slot as a cookie to hold the column  
                    DataContext = column,  
                    Stroke = lineBrush,  
                    StrokeThickness = _lineThickness,  
                    StrokeDashArray = dashArray  
                };  
                result.Add(line);  
            }  
            return result;  
        }  
  
        void UpdatePositions()  
        {  
            foreach (Line line in _guidelines)  
            {  
                int column = (int)line.DataContext;  
                line.X2 = _baseIndentation + 0.5 + column * _columnWidth;  
                line.X1 = line.X2;  
                line.Y1 = _view.ViewportTop;  
                line.Y2 = _view.ViewportBottom;  
            }  
        }  
  
        void AddGuidelinesToAdornmentLayer()  
        {  
            // Grab a reference to the adornment layer that this adornment   
            // should be added to  
            // Must match exported name in ColumnGuideAdornmentTextViewCreationListener  
            IAdornmentLayer adornmentLayer =   
                _view.GetAdornmentLayer("ColumnGuideAdornment");  
            if (adornmentLayer == null)  
                return;  
            adornmentLayer.RemoveAllAdornments();  
            // Add the guidelines to the adornment layer and make them relative   
            // to the viewport  
            foreach (UIElement element in _guidelines)  
                adornmentLayer.AddAdornment(AdornmentPositioningBehavior.OwnerControlled,  
                                            null, null, element, null);  
        }  
    }  
  
}  
```  
  
 Bu sınıfın örnekleri tutan ilişkili <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView> ve listesini `Line` görünümünde çizilen nesneler.  
  
 Oluşturucu (çağrılır `ColumnGuideAdornmentTextViewCreationListener` Visual Studio, yeni görünümler oluşturduğunda) sütun kılavuzu oluşturur `Line` nesneleri.  Oluşturucu işleyiciler için de ekler; `SettingsChanged` olay (tanımlanan `GuidesSettingsManager`) ve olaylarını görüntüleme `LayoutChanged` ve `Closed`.  
  
 `LayoutChanged` Değişiklikleri görünümünde, Visual Studio görünüm oluşturduğunda dahil olmak üzere çeşitli türlerde nedeniyle olay harekete geçirilir.  `OnViewLayoutChanged` İşleyicisi çağrılarını `AddGuidelinesToAdornmentLayer` yürütülecek.  Kodda `OnViewLayoutChanged` yazı tipi boyutu değişiklikleri, görünüm boşluğu, yatay kaydırma ve benzeri gibi değişikliklere göre satır konumlarını güncelleştirme gerekip gerekmediğini belirler.  Kodda `UpdatePositions` karakter veya metin satırının belirtilen karakter uzaklığı olan metin sütunu hemen sonra çizmek kılavuz çizgilerini neden olur.  
  
 Zaman ayarları `SettingsChanged` işlevi yalnızca yeniden oluşturur tüm `Line` hangi yeni ayarlar ile nesneleri.  Kod satırı pozisyonları ayarladıktan sonra önceki tüm kaldırır `Line` nesnelerin `ColumnGuideAdornment` kenarlığı katman ve yenilerini ekler.  
  
## <a name="defining-the-commands-menus-and-menu-placements"></a>Komutlar, menüler ve menü yerleşimi tanımlama  
 Olabilir çok için komut işleyicileri ' takma komutlar ve menüler bildirme ve diğer çeşitli menülerde komutları ya da menü grubuna yerleştirerek.  Bu izlenecek yol, bu uzantıdaki ancak daha ayrıntılı bilgi için komutları nasıl çalıştığını vurgular, bkz: [genişletme menüler ve komutlar](../extensibility/extending-menus-and-commands.md).  
  
### <a name="introduction-to-the-code"></a>Kod giriş  
 Sütun kılavuzları uzantısı gösterir birlikte ait komut grubuyla ilgili bildirme (sütun ekleme, sütun kaldırmak, çizgi rengini değiştirin) ve ardından bu grubun düzenleyicinin bağlam menüsünün alt menüde yerleştirme.  Sütun kılavuzları uzantı komutları ana de ekler. **Düzenle** menü ancak tutar bunları görünmez, aşağıdaki yaygın desen olarak ele alınan.  
  
 Komutları uygulama üç bölümü vardır: ColumnGuideCommandsPackage.cs ColumnGuideCommandsPackage.vsct ve ColumnGuideCommands.cs.  Şablonları tarafından oluşturulan kodu bir komut yerleştirir **Araçları** uygulama olarak bir iletişim kutusu açılır menü.  Oldukça olduğundan nasıl, .vsct ve ColumnGuideCommands.cs dosyalarında uygulanır bakabilirsiniz.  Bu dosyalar aşağıdaki kodda yerini alır.  
  
 Paket, Visual Studio için uzantı komutları ve komutlar yerleştirileceği yeri sunduğunu keşfedin gerekli olan ortak bildirimleri kodudur.  Paket başlatır, bu örneği komutları uygulama sınıfı.  Komutlarına ilişkin paketleri hakkında daha fazla bilgi için yukarıda bağlantı komutları bakın.  
  
### <a name="a-common-commands-pattern"></a>Bir ortak desen komutları  
 Visual Studio'da çok yaygın bir düzen örneği sütun kılavuzları uzantısında komutlardır.  İlgili komutları bir gruba yerleştirmek ve o grubun ana menüde, sık sık ile yerleştirdiğiniz "`<CommandFlag>CommandWellOnly</CommandFlag>`" komutu görünmez yapmak için ayarlayın.  Ana menülerde komutları koyma (gibi **Düzenle**) bu şekilde bunları kullanışlı adlar sağlar (gibi **Edit.AddColumnGuide**) komutları, tuş bağlamaları yeniden atarken bulmak için yararlı olan  **Araçlar Seçenekler** ve komutları çağrılırken tamamlama alma **komut penceresi**.  
  
 Ardından komut grubunu bağlam menüleri ekleme veya alt menü komutlarını kullanmak için kullanıcı beklediğiniz yerde.  Visual Studio işler `CommandWellOnly` olarak yalnızca ana menüler bir görünmezlik bayrağı.  Bir bağlam menüsü veya alt menü komutları aynı kullanıcı grubu yerleştirdiğinizde, komutları görülebilir.  
  
 Sık karşılaşılan desenini bir parçası olarak, bir tek alt menü tutan ikinci bir grup sütun kılavuzları uzantısı oluşturur.  Alt menü sırayla ilk grupla dört sütun kılavuzu komutlarını içerir.  Alt menü tutan ikinci grup alt menü bu bağlam menüleri getirecek çeşitli bağlam menüleri üzerinde yerleştirdiğiniz yeniden kullanılabilir varlıktır.  
  
### <a name="the-vsct-file"></a>.Vsct dosyası  
 .Vsct dosyası, komutlar ve bunlar, birlikte simgeler vb. nereye bildirir.  .Vsct dosyası içeriğini (aşağıda açıklanmıştır) aşağıdaki kodla değiştirin:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
  <!--  This is the file that defines the actual layout and type of the commands.  
        It is divided in different sections (e.g. command definition, command  
        placement, ...), with each defining a specific set of properties.  
        See the comment before each section for more details about how to  
        use it. -->  
  
  <!--  The VSCT compiler (the tool that translates this file into the binary  
        format that VisualStudio will consume) has the ability to run a preprocessor  
        on the vsct file; this preprocessor is (usually) the C++ preprocessor, so  
        it is possible to define includes and macros with the same syntax used  
        in C++ files. Using this ability of the compiler here, we include some files  
        defining some of the constants that we will use inside the file. -->  
  
  <!--This is the file that defines the IDs for all the commands exposed by   
      VisualStudio. -->  
  <Extern href="stdidcmd.h"/>  
  
  <!--This header contains the command ids for the menus provided by the shell. -->  
  <Extern href="vsshlids.h"/>  
  
  <!--The Commands section is where commands, menus, and menu groups are defined.  
      This section uses a Guid to identify the package that provides the command   
      defined inside it. -->  
  <Commands package="guidColumnGuideCommandsPkg">  
    <!-- Inside this section we have different sub-sections: one for the menus, another    
    for the menu groups, one for the buttons (the actual commands), one for the combos   
    and the last one for the bitmaps used. Each element is identified by a command id  
    that is a unique pair of guid and numeric identifier; the guid part of the identifier  
    is usually called "command set" and is used to group different command inside a  
    logically related group; your package should define its own command set in order to  
    avoid collisions with command ids defined by other packages. -->  
  
    <!-- In this section you can define new menu groups. A menu group is a container for   
         other menus or buttons (commands); from a visual point of view you can see the   
         group as the part of a menu contained between two lines. The parent of a group   
         must be a menu. -->  
    <Groups>  
  
      <!-- The main group is parented to the edit menu. All the buttons within the group  
           have the "CommandWellOnly" flag, so they're actually invisible, but it means  
           they get canonical names that begin with "Edit". Using placements, the group  
           is also placed in the GuidesSubMenu group. -->  
      <!-- The priority 0xB801 is chosen so it goes just after   
           IDG_VS_EDIT_COMMANDWELL -->  
      <Group guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"  
             priority="0xB801">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_EDIT" />  
      </Group>  
  
      <!-- Group for holding the "Guidelines" sub-menu anchor (the item on the menu that  
           drops the sub menu). The group is parented to  
           the context menu for code windows. That takes care of most editors, but it's  
           also placed in a couple of other windows using Placements -->  
      <Group guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
             priority="0x0600">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_CTXT_CODEWIN" />  
      </Group>  
  
    </Groups>  
  
    <Menus>  
      <Menu guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" priority="0x1000"  
            type="Menu">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup" />  
        <Strings>  
          <ButtonText>&Column Guides</ButtonText>  
        </Strings>  
      </Menu>  
    </Menus>  
  
    <!--Buttons section. -->  
    <!--This section defines the elements the user can interact with, like a menu command or a button   
        or combo box in a toolbar. -->  
    <Buttons>  
      <!--To define a menu group you have to specify its ID, the parent menu and its   
          display priority.   
          The command is visible and enabled by default. If you need to change the   
          visibility, status, etc, you can use the CommandFlag node.  
          You can add more than one CommandFlag node e.g.:  
              <CommandFlag>DefaultInvisible</CommandFlag>  
              <CommandFlag>DynamicVisibility</CommandFlag>  
          If you do not want an image next to your command, remove the Icon node or   
          set it to <Icon guid="guidOfficeIcon" id="msotcidNoIcon" /> -->  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidAddColumnGuide"   
              priority="0x0100" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicAddGuide" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <CommandFlag>AllowParams</CommandFlag>  
        <Strings>  
          <ButtonText>&Add Column Guide</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidRemoveColumnGuide"   
              priority="0x0101" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicRemoveGuide" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <CommandFlag>AllowParams</CommandFlag>  
        <Strings>  
          <ButtonText>&Remove Column Guide</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidChooseGuideColor"   
              priority="0x0103" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicChooseColor" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <Strings>  
          <ButtonText>Column Guide &Color...</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidRemoveAllColumnGuides"   
              priority="0x0102" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <Strings>  
          <ButtonText>Remove A&ll Columns</ButtonText>  
        </Strings>  
      </Button>  
    </Buttons>  
  
    <!--The bitmaps section is used to define the bitmaps that are used for the  
        commands.-->  
    <Bitmaps>  
      <!--  The bitmap id is defined in a way that is a little bit different from the  
            others:   
            the declaration starts with a guid for the bitmap strip, then there is the  
            resource id of the bitmap strip containing the bitmaps and then there are   
            the numeric ids of the elements used inside a button definition. An important  
            aspect of this declaration is that the element id   
            must be the actual index (1-based) of the bitmap inside the bitmap strip. -->  
      <Bitmap guid="guidImages" href="Resources\ColumnGuideCommands.png"   
              usedList="bmpPicAddGuide, bmpPicRemoveGuide, bmpPicChooseColor" />  
    </Bitmaps>  
  
  </Commands>  
  
  <CommandPlacements>  
  
    <!-- Define secondary placements for our groups -->  
  
    <!-- Place the group containing the three commands in the sub-menu -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"   
                      priority="0x0100">  
      <Parent guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" />  
    </CommandPlacement>  
  
    <!-- The HTML editor context menu, for some reason, redefines its own groups  
         so we need to place a copy of our context menu there too. -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_HTML" />  
    </CommandPlacement>  
  
    <!-- The HTML context menu in Dev12 changed. -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp_Dev12" id="IDMX_HTM_SOURCE_HTML_Dev12" />  
    </CommandPlacement>  
  
    <!-- Similarly for Script -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"  
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_SCRIPT" />  
    </CommandPlacement>  
  
    <!-- Similarly for ASPX  -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_ASPX" />  
    </CommandPlacement>  
  
    <!-- Similarly for the XAML editor context menu -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"  
                      priority="0x0600">  
      <Parent guid="guidXamlUiCmds" id="IDM_XAML_EDITOR" />  
    </CommandPlacement>  
  
  </CommandPlacements>  
  
  <!-- This defines the identifiers and their values used above to index resources  
       and specify commands. -->  
  <Symbols>  
    <!-- This is the package guid. -->  
    <GuidSymbol name="guidColumnGuideCommandsPkg"   
                value="{e914e5de-0851-4904-b361-1a3a9d449704}" />  
  
    <!-- This is the guid used to group the menu commands together -->  
    <GuidSymbol name="guidColumnGuidesCommandSet"   
                value="{c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e}">  
      <IDSymbol name="GuidesContextMenuGroup" value="0x1020" />  
      <IDSymbol name="GuidesMenuItemsGroup" value="0x1021" />  
      <IDSymbol name="GuidesSubMenu" value="0x1022" />  
      <IDSymbol name="cmdidAddColumnGuide" value="0x0100" />  
      <IDSymbol name="cmdidRemoveColumnGuide" value="0x0101" />  
      <IDSymbol name="cmdidChooseGuideColor" value="0x0102" />  
      <IDSymbol name="cmdidRemoveAllColumnGuides" value="0x0103" />  
    </GuidSymbol>  
  
    <GuidSymbol name="guidImages" value="{2C99F852-587C-43AF-AA2D-F605DE2E46EF}">  
      <IDSymbol name="bmpPicAddGuide" value="1" />  
      <IDSymbol name="bmpPicRemoveGuide" value="2" />  
      <IDSymbol name="bmpPicChooseColor" value="3" />  
    </GuidSymbol>  
  
    <GuidSymbol name="CMDSETID_HtmEdGrp_Dev12"   
                value="{78F03954-2FB8-4087-8CE7-59D71710B3BB}">  
      <IDSymbol name="IDMX_HTM_SOURCE_HTML_Dev12" value="0x1" />  
    </GuidSymbol>  
  
    <GuidSymbol name="CMDSETID_HtmEdGrp" value="{d7e8c5e1-bdb8-11d0-9c88-0000f8040a53}">  
      <IDSymbol name="IDMX_HTM_SOURCE_HTML" value="0x33" />  
      <IDSymbol name="IDMX_HTM_SOURCE_SCRIPT" value="0x34" />  
      <IDSymbol name="IDMX_HTM_SOURCE_ASPX" value="0x35" />  
    </GuidSymbol>  
  
    <GuidSymbol name="guidXamlUiCmds" value="{4c87b692-1202-46aa-b64c-ef01faec53da}">  
      <IDSymbol name="IDM_XAML_EDITOR" value="0x103" />  
    </GuidSymbol>  
  </Symbols>  
  
</CommandTable>  
  
```  
  
 **GUID'LER**.  GUID (proje öğesi Şablonu oluşturulan) ColumnGuideCommandsPackage.cs dosyasında bildirilen paketi GUID (yukarıdaki kopyalandı .vsct dosyası bildirilen paket karşılamasını sağlamak gereken Visual Studio'nın, komut işleyicileri bulabilir ve bunları çağırma ).  Bu örnek kod yeniden kullanımı, böylece herkes ile bu kodu kopyalamış olmanız çakışmadığından farklı bir GUID olduğundan emin olun.  
  
 ColumnGuideCommandsPackage.cs içinde şu satırı bulun ve tırnak işaretleri arasındaki GUID kopyalayın:  
  
```csharp  
public const string PackageGuidString = "ef726849-5447-4f73-8de5-01b9e930f7cd";  
```  
  
 Böylece aşağıdaki satırı sahip GUID .vsct dosyaya yapıştırın, `Symbols` bildirimleri:  
  
```xml  
<GuidSymbol name="guidColumnGuideCommandsPkg"   
            value="{ef726849-5447-4f73-8de5-01b9e930f7cd}" />  
```  
  
 Komut için GUID'leri ayarlayın ve bit eşlem resim dosyası çok uzantılarınızı için benzersiz olmalıdır:  
  
```xml  
<GuidSymbol name="guidColumnGuidesCommandSet"   
            value="{c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e}">  
<GuidSymbol name="guidImages" value="{2C99F852-587C-43AF-AA2D-F605DE2E46EF}">  
```  
  
 Bununla birlikte, komut kümesini değiştirin ve çalışmak için kodu almak için bu kılavuzda GUID'leri görüntü bit eşlem gerekmez.  Ayarla komutu GUID ColumnGuideCommands.cs dosya bildiriminde eşleşmesi gerekiyor, ancak bu dosyanın içeriğini çok yerini alır; Bu nedenle, GUID'leri eşleşir.  
  
 Hiçbir zaman değiştirmek için sütun kılavuzu komutlarını eklendiği önceden varolan menülerin .vsct dosyası diğer GUID'leri belirleyin.  
  
 **Dosya bölümleri**.  .vsct üç dış bölümü vardır: komutları, yerleşimi ve semboller.  Komutları bölümüne komut gruplarını, menüler, düğmeler veya menü öğeleri ve simgeleri için bit eşlemler tanımlar.  Yerleşimi bölüm grupları menüleri veya önceden mevcut olan menüleri üzerine ek yerleşimi nereye bildirir.  Semboller bölümü .vsct kod daha okunabilir GUID'leri ve onaltılık sayı her yerde olması daha yapar .vsct dosyası başka bir yerde kullanılan tanımlayıcıları bildirir.  
  
 **Komutları bölümü, tanımlarını gruplar**.  Komutları bölümüne ilk komut gruplarını tanımlar.  Menülerde gruplara ayırarak hafif gri satırıyla gördüğünüz komutları komutları gruplarıdır.  Bir grup da bu örnekte olduğu gibi tüm alt menüsünde, doldurmanız ve bu durumda satırları ayırmak gri görmezsiniz.  .Vsct dosyaları iki gruba bildirir `GuidesMenuItemsGroup` için shapemap `IDM_VS_MENU_EDIT` (ana **Düzenle** menüsü) ve `GuidesContextMenuGroup` için shapemap `IDM_VS_CTXT_CODEWIN` (Kod Düzenleyicisi'nin bağlam menüsü).  
  
 İkinci grup bildirime sahip bir `0x0600` önceliği:  
  
```xml  
<Group guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
             priority="0x0600">  
```  
  
 Sütun yerleştirmek için alt menü alt menü grubu ekleyeceğiz, herhangi bir bağlam menüsü, sonunda kılavuzları olur.  Ancak, en iyi bildiğiniz ve önceliği kullanarak her zaman son olacak şekilde alt menü zorla varsayımında bulunmamalıdır `0xFFFF`.  Bu sayı, alt menü yerleştirdiğiniz yere bağlam menüleri nereden kaynaklandığını görmek için gerçekleştirebileceğiniz işlemleri gerekir.  Bu durumda `0x0600` görebiliriz ancak kendi uzantı isteniliyorsa sütun kılavuzları uzantıyı düşük olacak şekilde tasarlamak için başka birinin yer bırakır kadar menüleri sonunda koymak için yüksek.  
  
 **Bölümünde, menü tanımı komutları**.  Sonraki alt menü komutu bölümüne tanımlar `GuidesSubMenu`, üst öğeye sahip için `GuidesContextMenuGroup`.  `GuidesContextMenuGroup` Grup için tüm ilgili bağlam menüleri ekleriz.  Yerleşimi bölümünde kod dört sütun kılavuzu komutlarını grubuyla bu alt menüde yerleştirir.  
  
 **Komutları bölümü, tanımları düğmeleri**.  Komutları bölümüne sonra menü öğelerini tanımlar veya dört sütun düğmelerinden komutları size yol gösterir.  `CommandWellOnly`, yukarıda açıklanan, komutları bir ana menüsündeki yerleştirildiğinde görünmez anlamına gelir.  Menü öğesinin iki düğme bildirimleri (Kılavuzu ekleme ve kaldırma Kılavuzu) de bir `AllowParams` bayrağı:  
  
```xml  
<CommandFlag>AllowParams</CommandFlag>  
```  
  
 Bu bayrak, bunların ile ana menü yerleşimi, Visual Studio komut işleyici çağırır bağımsız değişkenlerini almak için komut olmak sağlar.  Kullanıcı komut penceresinden komut çağırırsa, geçirilen bağımsız değişken komut işleyicisi için olay bağımsız değişkenleri.  
  
 **Komutunu bölümler, bit eşlemler tanımları**.  Son olarak bit eşlemler veya komutlar için kullanılan simgeler komutları bölümüne bildirir.  Proje kaynağı tanımlar ve kullanılan simge bir tabanlı dizinleri listeler basit bir bildirimin budur.  .Vsct dosyası sembolleri bölümünü dizin kullanılan tanımlayıcıları değerlerini bildirir.  Bu izlenecek yol, projeye özel komut öğe şablonu ile sağlanan bit eşlem Şerit kullanır.  
  
 **Yerleşimi bölüm**.  Komutlarından sonra bölümü yerleşimi bölümdür.  İlki, açıklanan ilk grup dört sütun Kılavuzu alt menü komutları komutları göründüğü tutan kod burada ekler şöyledir:  
  
```xml  
<CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"   
                  priority="0x0100">  
  <Parent guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" />  
</CommandPlacement>  
```  
  
 Tüm diğer yerleşimi eklemek `GuidesContextMenuGroup` (içeren `GuidesSubMenu`) için diğer Düzenleyici bağlam menüleri.  Kod zaman bildirilen `GuidesContextMenuGroup`, Kod Düzenleyicisi'nin bağlam menüsüne shapemap.  Bir yerleştirme için Kod Düzenleyicisi'nin bağlam menüsünü görmezsiniz nedeni budur.  
  
 **Semboller bölüm**.  Yukarıda belirtildiği gibi simgeler bölümü .vsct kod daha okunabilir GUID'leri ve onaltılık sayı her yerde olması daha yapar .vsct dosyası başka bir yerde kullanılan tanımlayıcıları bildirir.  Bu bölümdeki önemli noktaları, paket GUID'ini GUID ile komut uygulama sınıf bildiriminde kabul etmelisiniz bildirim paket sınıfı ve komut kümesi ile kabul etmelisiniz ' dir.  
  
## <a name="implementing-the-commands"></a>Komutları uygulama  
 ColumnGuideCommands.cs dosya komutları uygular ve işleyicileri kancaları.  Visual Studio Paketi yükler ve başlatır, paket sırayla çağırır `Initialize` komutları uygulama sınıfı üzerinde.  Komutları başlatma, yalnızca sınıfın örneğini oluşturur ve komut işleyicileri Oluşturucu kancaları.  
  
 ColumnGuideCommands.cs dosyasının içeriğini (aşağıda açıklanmıştır) aşağıdaki kodla değiştirin:  
  
```csharp  
using System;  
using System.ComponentModel.Design;  
using System.Globalization;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.Shell.Interop;  
using Microsoft.VisualStudio.TextManager.Interop;  
using Microsoft.VisualStudio.Text.Editor;  
using Microsoft.VisualStudio;  
  
namespace ColumnGuides  
{  
    /// <summary>  
    /// Command handler  
    /// </summary>  
    internal sealed class ColumnGuideCommands  
    {  
  
        const int cmdidAddColumnGuide = 0x0100;  
        const int cmdidRemoveColumnGuide = 0x0101;  
        const int cmdidChooseGuideColor = 0x0102;  
        const int cmdidRemoveAllColumnGuides = 0x0103;  
  
        /// <summary>  
        /// Command menu group (command set GUID).  
        /// </summary>  
        static readonly Guid CommandSet =   
            new Guid("c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e");  
  
        /// <summary>  
        /// VS Package that provides this command, not null.  
        /// </summary>  
        private readonly Package package;  
  
        OleMenuCommand _addGuidelineCommand;  
        OleMenuCommand _removeGuidelineCommand;  
  
        /// <summary>  
        /// Initializes the singleton instance of the command.  
        /// </summary>  
        /// <param name="package">Owner package, not null.</param>  
        public static void Initialize(Package package)  
        {  
            Instance = new ColumnGuideCommands(package);  
        }  
  
        /// <summary>  
        /// Gets the instance of the command.  
        /// </summary>  
        public static ColumnGuideCommands Instance  
        {  
            get;  
            private set;  
        }  
  
        /// <summary>  
        /// Initializes a new instance of the <see cref="ColumnGuideCommands"/> class.  
        /// Adds our command handlers for menu (commands must exist in the command   
        /// table file)  
        /// </summary>  
        /// <param name="package">Owner package, not null.</param>  
        private ColumnGuideCommands(Package package)  
        {  
            if (package == null)  
            {  
                throw new ArgumentNullException("package");  
            }  
  
            this.package = package;  
  
            // Add our command handlers for menu (commands must exist in the .vsct file)  
  
            OleMenuCommandService commandService =  
                this.ServiceProvider.GetService(typeof(IMenuCommandService))  
                    as OleMenuCommandService;  
            if (commandService != null)  
            {  
                // Add guide  
                _addGuidelineCommand =   
                    new OleMenuCommand(AddColumnGuideExecuted, null,  
                                       AddColumnGuideBeforeQueryStatus,  
                                       new CommandID(ColumnGuideCommands.CommandSet,  
                                                     cmdidAddColumnGuide));  
                _addGuidelineCommand.ParametersDescription = "<column>";  
                commandService.AddCommand(_addGuidelineCommand);  
                // Remove guide  
                _removeGuidelineCommand =  
                    new OleMenuCommand(RemoveColumnGuideExecuted, null,  
                                       RemoveColumnGuideBeforeQueryStatus,  
                                       new CommandID(ColumnGuideCommands.CommandSet,  
                                                     cmdidRemoveColumnGuide));  
                _removeGuidelineCommand.ParametersDescription = "<column>";  
                commandService.AddCommand(_removeGuidelineCommand);  
                // Choose color  
                commandService.AddCommand(  
                    new MenuCommand(ChooseGuideColorExecuted,  
                                    new CommandID(ColumnGuideCommands.CommandSet,  
                                                  cmdidChooseGuideColor)));  
                // Remove all  
                commandService.AddCommand(  
                    new MenuCommand(RemoveAllGuidelinesExecuted,  
                                    new CommandID(ColumnGuideCommands.CommandSet,  
                                                  cmdidRemoveAllColumnGuides)));  
            }  
        }  
  
        /// <summary>  
        /// Gets the service provider from the owner package.  
        /// </summary>  
        private IServiceProvider ServiceProvider  
        {  
            get  
            {  
                return this.package;  
            }  
        }  
  
        private void AddColumnGuideBeforeQueryStatus(object sender, EventArgs e)  
        {  
            int currentColumn = GetCurrentEditorColumn();  
            _addGuidelineCommand.Enabled =  
                GuidesSettingsManager.CanAddGuideline(currentColumn);  
        }  
  
        private void RemoveColumnGuideBeforeQueryStatus(object sender, EventArgs e)  
        {  
            int currentColumn = GetCurrentEditorColumn();  
            _removeGuidelineCommand.Enabled =  
                GuidesSettingsManager.CanRemoveGuideline(currentColumn);  
        }  
  
        private int GetCurrentEditorColumn()  
        {  
            IVsTextView view = GetActiveTextView();  
            if (view == null)  
            {  
                return -1;  
            }  
  
            try  
            {  
                IWpfTextView textView = GetTextViewFromVsTextView(view);  
                int column = GetCaretColumn(textView);  
  
                // Note: GetCaretColumn returns 0-based positions. Guidelines are 1-based  
                // positions.  
                // However, do not subtract one here since the caret is positioned to the  
                // left of  
                // the given column and the guidelines are positioned to the right. We  
                // want the  
                // guideline to line up with the current caret position. e.g. When the  
                // caret is  
                // at position 1 (zero-based), the status bar says column 2. We want to  
                // add a  
                // guideline for column 1 since that will place the guideline where the  
                // caret is.  
                return column;  
            }  
            catch (InvalidOperationException)  
            {  
                return -1;  
            }  
        }  
  
        /// <summary>  
        /// Find the active text view (if any) in the active document.  
        /// </summary>  
        /// <returns>The IVsTextView of the active view, or null if there is no active  
        /// document or the  
        /// active view in the active document is not a text view.</returns>  
        private IVsTextView GetActiveTextView()  
        {  
            IVsMonitorSelection selection =  
                this.ServiceProvider.GetService(typeof(IVsMonitorSelection))  
                                                    as IVsMonitorSelection;  
            object frameObj = null;  
            ErrorHandler.ThrowOnFailure(  
                selection.GetCurrentElementValue(  
                    (uint)VSConstants.VSSELELEMID.SEID_DocumentFrame, out frameObj));  
  
            IVsWindowFrame frame = frameObj as IVsWindowFrame;  
            if (frame == null)  
            {  
                return null;  
            }  
  
            return GetActiveView(frame);  
        }  
  
        private static IVsTextView GetActiveView(IVsWindowFrame windowFrame)  
        {  
            if (windowFrame == null)  
            {  
                throw new ArgumentException("windowFrame");  
            }  
  
            object pvar;  
            ErrorHandler.ThrowOnFailure(  
                windowFrame.GetProperty((int)__VSFPROPID.VSFPROPID_DocView, out pvar));  
  
            IVsTextView textView = pvar as IVsTextView;  
            if (textView == null)  
            {  
                IVsCodeWindow codeWin = pvar as IVsCodeWindow;  
                if (codeWin != null)  
                {  
                    ErrorHandler.ThrowOnFailure(codeWin.GetLastActiveView(out textView));  
                }  
            }  
            return textView;  
        }  
  
        private static IWpfTextView GetTextViewFromVsTextView(IVsTextView view)  
        {  
  
            if (view == null)  
            {  
                throw new ArgumentNullException("view");  
            }  
  
            IVsUserData userData = view as IVsUserData;  
            if (userData == null)  
            {  
                throw new InvalidOperationException();  
            }  
  
            object objTextViewHost;  
            if (VSConstants.S_OK  
                   != userData.GetData(Microsoft.VisualStudio  
                                                .Editor  
                                                .DefGuidList.guidIWpfTextViewHost,  
                                       out objTextViewHost))  
            {  
                throw new InvalidOperationException();  
            }  
  
            IWpfTextViewHost textViewHost = objTextViewHost as IWpfTextViewHost;  
            if (textViewHost == null)  
            {  
                throw new InvalidOperationException();  
            }  
  
            return textViewHost.TextView;  
        }  
  
        /// <summary>  
        /// Given an IWpfTextView, find the position of the caret and report its column  
        /// number. The column number is 0-based  
        /// </summary>  
        /// <param name="textView">The text view containing the caret</param>  
        /// <returns>The column number of the caret's position. When the caret is at the  
        /// leftmost column, the return value is zero.</returns>  
        private static int GetCaretColumn(IWpfTextView textView)  
        {  
            // This is the code the editor uses to populate the status bar.  
            Microsoft.VisualStudio.Text.Formatting.ITextViewLine caretViewLine =  
                textView.Caret.ContainingTextViewLine;  
            double columnWidth = textView.FormattedLineSource.ColumnWidth;  
            return (int)(Math.Round((textView.Caret.Left - caretViewLine.Left)  
                                       / columnWidth));  
        }  
  
        /// <summary>  
        /// Determine the applicable column number for an add or remove command.  
        /// The column is parsed from command arguments, if present. Otherwise  
        /// the current position of the caret is used to determine the column.  
        /// </summary>  
        /// <param name="e">Event args passed to the command handler.</param>  
        /// <returns>The column number. May be negative to indicate the column number is  
        /// unavailable.</returns>  
        /// <exception cref="ArgumentException">The column number parsed from event args  
        /// was not a valid integer.</exception>  
        private int GetApplicableColumn(EventArgs e)  
        {  
            var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
            if (!string.IsNullOrEmpty(inValue))  
            {  
                int column;  
                if (!int.TryParse(inValue, out column) || column < 0)  
                    throw new ArgumentException("Invalid column");  
                return column;  
            }  
  
            return GetCurrentEditorColumn();  
        }  
  
        /// <summary>  
        /// This function is the callback used to execute a command when the a menu item  
        /// is clicked. See the Initialize method to see how the menu item is associated  
        /// to this function using the OleMenuCommandService service and the MenuCommand  
        /// class.  
        /// </summary>  
        private void AddColumnGuideExecuted(object sender, EventArgs e)  
        {  
            int column = GetApplicableColumn(e);  
            if (column >= 0)  
            {  
                GuidesSettingsManager.AddGuideline(column);  
            }  
        }  
  
        private void RemoveColumnGuideExecuted(object sender, EventArgs e)  
        {  
            int column = GetApplicableColumn(e);  
            if (column >= 0)  
            {  
                GuidesSettingsManager.RemoveGuideline(column);  
            }  
        }  
  
        private void RemoveAllGuidelinesExecuted(object sender, EventArgs e)  
        {  
            GuidesSettingsManager.RemoveAllGuidelines();  
        }  
  
        private void ChooseGuideColorExecuted(object sender, EventArgs e)  
        {  
            System.Windows.Media.Color color = GuidesSettingsManager.GuidelinesColor;  
  
            using (System.Windows.Forms.ColorDialog picker =   
                new System.Windows.Forms.ColorDialog())  
            {  
                picker.Color = System.Drawing.Color.FromArgb(255, color.R, color.G,  
                                                             color.B);  
                if (picker.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
                {  
                    GuidesSettingsManager.GuidelinesColor =   
                        System.Windows.Media.Color.FromRgb(picker.Color.R,  
                                                           picker.Color.G,   
                                                           picker.Color.B);  
                }  
            }  
        }  
  
    }  
}  
  
```  
  
 **Başvuruları düzelt**.  Bu noktada bir başvuru eksik olabilir.  Çözüm Gezgini'ndeki başvurular düğümü üzerinde doğru işaretçi düğmesine basın.  Seçin **Ekle...** komutu.  **Başvuru Ekle** iletişim sağ üst köşedeki arama kutusuna sahiptir.  "Düzenleyicisi" (çift tırnak işaretleri olmadan) girin.  Seçin **Microsoft.VisualStudio.Editor** (kontrol gerekir yalnızca select öğenin sol kutusuna öğe) öğesi seçin **Tamam** başvuru eklenemiyor.  
  
 **Başlatma**.  Paket sınıfı başlatır, çağrı `Initialize` komutları uygulama sınıfı üzerinde.  `ColumnGuideCommands` Başlatma sınıfın örneğini oluşturur ve sınıf üyeleri sınıf örneği ve paket başvurusu kaydeder.  
  
 Komut işleyici kanca ups birini sınıf oluşturucusunda bakalım:  
  
```csharp  
_addGuidelineCommand =   
    new OleMenuCommand(AddColumnGuideExecuted, null,  
                       AddColumnGuideBeforeQueryStatus,  
                       new CommandID(ColumnGuideCommands.CommandSet,  
                                     cmdidAddColumnGuide));  
  
```  
  
 Oluşturduğunuz bir `OleMenuCommand`.  Visual Studio, Microsoft Office komut sistemi kullanır.  Anahtar bağımsız değişkenleri bir OleMenuCommand örnekleme komutu uygulayan işlevi olduğunda (`AddColumnGuideExecuted`), Visual Studio bir menü komutu ile gösterdiğinde çağrılacak işlevin (`AddColumnGuideBeforeQueryStatus`) ve komut kimliği.  Visual studio komut kendisini görünmez veya menüsünün belirli bir ekran için gri yapabilmeleri için bir komutu menüde göstermeden önce sorgu durumu işlevi çağırır (örneğin, devre dışı bırakma **kopyalama** seçim yok ise), simgesini, değiştirme veya bile adını (örneğin, çerçevedeki ekleme bir şeyi kaldırmak için) değiştirin ve benzeri.  Komut kimliği .vsct dosyası içinde bildirilen bir komut kimliği ile eşleşmelidir.  Komut için dizeleri ayarlamak ve sütun kılavuzları komut ColumnGuideCommands.cs .vsct dosyası arasında eşleşmelidir ekleyin.  
  
 Kullanıcılar (aşağıda açıklanmıştır) komut penceresinde komutuyla çağırdığınızda Yardım almak için aşağıdaki satırı sağlar:  
  
```csharp  
_addGuidelineCommand.ParametersDescription = "<column>";  
```  
  
 **Sorgu durumu**.  Sorgu durumu işlevleri `AddColumnGuideBeforeQueryStatus` ve `RemoveColumnGuideBeforeQueryStatus` bazı ayarları (örneğin, en fazla sayı kılavuzları ve en fazla sütun) kontrol edin veya kaldırmak için sütun kılavuzunu ise.  Koşullar doğru olduğunda bunlar komutlar sağlar.  Sorgu durumu işlevleri Visual Studio menüsünde her komut için bir menü gösterir. her zaman çalıştırdığı nedeni çok verimli olması gerekir.  
  
 **AddColumnGuideExecuted işlevi**.  Bir kılavuz ekleme ilginç bölümü geçerli Düzenleyici görünümü ve giriş işareti konumunu çıkarılıyor.  Önce bu işlevi çağıran `GetApplicableColumn` denetleyen komut işleyicinin olay bağımsız değişkenlerini bir kullanıcı tarafından sağlanan bağımsız değişken yoktur ve varsa hiçbiri, işlev Düzenleyicisi'nin görünümü denetler:  
  
```csharp  
private int GetApplicableColumn(EventArgs e)  
{  
    var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
    if (!string.IsNullOrEmpty(inValue))  
    {  
        int column;  
        if (!int.TryParse(inValue, out column) || column < 0)  
            throw new ArgumentException("Invalid column");  
        return column;  
    }  
  
    return GetCurrentEditorColumn();  
}  
  
```  
  
 `GetCurrentEditorColumn` almak için biraz incelemek için bir <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView> kod görünümü.  Aracılığıyla izleme, `GetActiveTextView`, `GetActiveView`, ve `GetTextViewFromVsTextView`, bunun nasıl yapılacağını görebilirsiniz.  Geçerli seçimi ile başlayan seçimin çerçeve alma sonra çerçeve DocView olarak alma soyutlanır, ilgili kodu verilmiştir bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>, ardından alınırken bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData> Ivstextview ve ardından bir görünüm ana alınıyor gelen ve Son olarak Iwpftextview:  
  
```csharp  
   IVsMonitorSelection selection =  
       this.ServiceProvider.GetService(typeof(IVsMonitorSelection))   
           as IVsMonitorSelection;  
   object frameObj = null;  
  
ErrorHandler.ThrowOnFailure(selection.GetCurrentElementValue(  
                                (uint)VSConstants.VSSELELEMID.SEID_DocumentFrame,  
                                out frameObj));  
  
   IVsWindowFrame frame = frameObj as IVsWindowFrame;  
   if (frame == null)  
       <<do nothing>>;  
  
...  
   object pvar;  
   ErrorHandler.ThrowOnFailure(frame.GetProperty((int)__VSFPROPID.VSFPROPID_DocView,  
                                                  out pvar));  
  
   IVsTextView textView = pvar as IVsTextView;  
   if (textView == null)  
   {  
       IVsCodeWindow codeWin = pvar as IVsCodeWindow;  
       if (codeWin != null)  
       {  
           ErrorHandler.ThrowOnFailure(codeWin.GetLastActiveView(out textView));  
       }  
   }  
  
...  
   if (textView == null)  
       <<do nothing>>  
  
   IVsUserData userData = textView as IVsUserData;  
   if (userData == null)  
       <<do nothing>>  
  
   object objTextViewHost;  
   if (VSConstants.S_OK   
           != userData.GetData(Microsoft.VisualStudio.Editor.DefGuidList  
                                                            .guidIWpfTextViewHost,  
                                out objTextViewHost))  
   {  
       <<do nothing>>  
   }  
  
   IWpfTextViewHost textViewHost = objTextViewHost as IWpfTextViewHost;  
   if (textViewHost == null)  
       <<do nothing>>  
  
   IWpfTextView textView = textViewHost.TextView;  
  
```  
  
 Bir Iwpftextview aldıktan sonra düzeltme işaretinin bulunduğu sütun alabilirsiniz:  
  
```csharp  
private static int GetCaretColumn(IWpfTextView textView)  
{  
    // This is the code the editor uses to populate the status bar.  
    Microsoft.VisualStudio.Text.Formatting.ITextViewLine caretViewLine =  
        textView.Caret.ContainingTextViewLine;  
    double columnWidth = textView.FormattedLineSource.ColumnWidth;  
    return (int)(Math.Round((textView.Caret.Left - caretViewLine.Left)  
                                / columnWidth));  
}  
  
```  
  
 Kullanıcı tıkladı olduğunda, geçerli sütun ele kod yalnızca eklemek veya sütunu kaldırmak için ayarları Yöneticisi çağırır.  Ayarlar Yöneticisi için tüm olay harekete `ColumnGuideAdornment` nesneleri dinleyin.  Olay oluşturulduğunda, bu nesneler, ilişkili metin görünümleri ile yeni bir sütun kılavuzu ayarlarını güncelleştirin.  
  
## <a name="invoking-command-from-the-command-window"></a>Komut penceresinden çağrılıyor komutu  
 Sütun kılavuzları örnek, kullanıcıların iki komutu komut penceresinden genişletilebilirlik biçimi çağrılacak sağlar.  Kullanırsanız **görünümü &#124; diğer Windows &#124; komut penceresi** komut, komut penceresinde görebilirsiniz.  "Düzenle" girerek komut penceresi ile etkileşime geçebilir ve komut adı tamamlama ve bağımsız değişken 120 sağlayarak, aşağıdakilere sahip:  
  
```  
> Edit.AddColumnGuide 120  
>  
```  
  
 Bu olan .vsct dosyası bildirimlerinde sağlayan örnek parçalarını `ColumnGuideCommands` komut işleyicileri ve olay bağımsız değişkenleri denetleyin komut işleyicisi uygulamaları kancaları sınıf oluşturucusu.  
  
 Gördüğünüz "`<CommandFlag>CommandWellOnly</CommandFlag>`".vsct dosyası yanı sıra düzenleme ana menüsündeki yerleşimi olsa bile değil göstereceğiz komutlar **Düzenle** menüsünde kullanıcı Arabirimi.  Bunları ana Düzen menüsündeki sahip sağlayan gibi adları **Edit.AddColumnGuide**.  Komutları doğrudan Düzen menüsündeki dört komuttan grubuna yerleştirilen tutan bildirimi Grup:  
  
```xml  
<Group guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"  
             priority="0xB801">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_EDIT" />  
      </Group>  
  
```  
  
 Daha sonra bildirilen komutları düğmeleri bölümünü `CommandWellOnly` bunları ana menüde görünmez tutmak için ve bunları ile bildirilen `AllowParams`:  
  
```xml  
<Button guid="guidColumnGuidesCommandSet" id="cmdidAddColumnGuide"   
        priority="0x0100" type="Button">  
  <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
  <Icon guid="guidImages" id="bmpPicAddGuide" />  
  <CommandFlag>CommandWellOnly</CommandFlag>  
  <CommandFlag>AllowParams</CommandFlag>  
  
```  
  
 Kod içinde bağlama komut işleyici gördüğünüz `ColumnGuideCommands` sınıf oluşturucusu sağlanan izin verilen parametre açıklaması:  
  
```csharp  
_addGuidelineCommand.ParametersDescription = "<column>";  
  
```  
  
 Gördüğünüz `GetApplicableColumn` işlev denetimleri `OleMenuCmdEventArgs` Düzenleyicisi'nin görünümü geçerli bir sütun için iade etmeden önce bir değer için:  
  
```csharp  
private int GetApplicableColumn(EventArgs e)  
{  
    var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
    if (!string.IsNullOrEmpty(inValue))  
    {  
        int column;  
        if (!int.TryParse(inValue, out column) || column < 0)  
            throw new ArgumentException("Invalid column");  
        return column;  
    }  
  
```  
  
## <a name="trying-your-extension"></a>Uzantınızı çalışıyor  
 Artık basabilirsiniz **F5** sütun kılavuzları uzantınızı yürütülecek.  Bir metin dosyasını açın ve kılavuz çizgileri ekleme, bunları kaldırmanız ve bunların rengini değiştirmek için düzenleyicinin bağlam menüsünü kullanın.  Metinde'ye tıklamanız (boşluk değil, satır sonu geçildi) bir sütun eklemek için kılavuz veya düzenleyici satırın son sütunu ekler.  Komut penceresini kullanın ve bağımsız değişken ile komutları çağırır, herhangi bir sütun kılavuzları ekleyebilirsiniz.  
  
 Farklı komut yerleşimi deneyin, adlarını değiştirmek, simgeler vb. değiştirmek istediğiniz ve Visual Studio menülerinde en son kodu gösteren herhangi bir sorun varsa, hata ayıklaması yaptığınız Deneysel hive sıfırlayabilirsiniz.  Ortaya çıkarmak **Windows Başlat menüsündeki** ve "Sıfırla" yazın.  Arayın ve çağırmak **sonraki Visual Studio Deneysel örneğini sıfırlama**.  Bu, tüm uzantı bileşenlerinin Deneysel kayıt defteri kovanı temizler.  Mevcut bileşenlerinden temizleme ayarları şekilde Visual Studio'nun Deneysel hive'ı kapattığınızda sahip tüm kılavuzları hala alınmaz vardır, kodunuzun sonraki başlatmada ayarlar deposu okur.  
  
## <a name="finished-code-project"></a>Tamamlanmış kod projesini  
 Bir github projesini Visual Studio genişletilebilirliği örnekleri yakında ve projeyi olacak.  Bu konuda, bu durum oluştuğunda var. işaret edecek şekilde güncelleştireceğiz.  Tamamlanan örnek proje, farklı GUID'leri olabilir ve farklı bit eşlemler Şerit komut simgeler için gerekir.  
  
 Bu Visual Studio Galerisi sütun kılavuzları özelliğiyle sürümünü deneyebilirsiniz[uzantısı](https://visualstudiogallery.msdn.microsoft.com/da227a0b-0e31-4a11-8f6b-3a149cf2e459?SRC=Home).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düzenleyicinin içinde](../extensibility/inside-the-editor.md)   
 [Düzenleyici ve dil hizmetlerini genişletme](../extensibility/extending-the-editor-and-language-services.md)   
 [Dil hizmeti ve düzenleyici uzantı noktaları](../extensibility/language-service-and-editor-extension-points.md)   
 [Menüleri ve komutlari genişletme komutları](../extensibility/extending-menus-and-commands.md)   
 [Bir menüye alt menü ekleme](../extensibility/adding-a-submenu-to-a-menu.md)   
 [Düzenleyici Öğesi Şablonuyla Uzantı Oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md)

