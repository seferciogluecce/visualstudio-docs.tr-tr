---
title: 'İzlenecek yol: INSERT özelleştirme, güncelleştirme ve silme davranışı varlık sınıflarının | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03ff1146-706e-4780-91cb-56a83df63eea
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4d8ef69258d9c672bb5deb01b9c2e0972d4e8303
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49193550"
---
# <a name="walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes"></a>İzlenecek yol: INSERT özelleştirme, güncelleştirme ve silme davranışı varlık sınıflarının
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
[LINQ to SQL araçlarını Visual Studio'da](../data-tools/linq-to-sql-tools-in-visual-studio2.md) oluşturma ve düzenleme için bir görsel tasarım yüzeyi sağlar [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] bir veritabanındaki nesneleri temel alan sınıfları (varlık sınıfları). Kullanarak [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655), SQL veritabanlarına erişim bir LINQ teknolojisi kullanabilirsiniz. Daha fazla bilgi için [LINQ (dil ile tümleşik sorgu)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).  
  
 Varsayılan olarak, güncelleştirmeleri gerçekleştirmek için mantığı tarafından sağlanan [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] çalışma zamanı. Çalışma zamanı varsayılan tablo (sütun tanımları ve birincil anahtar bilgileri) şemasını temel alan INSERT, Update ve Delete deyimlerini oluşturur. Varsayılan davranışı kullanmak istemediğinizde, güncelleştirme davranışı yapılandırmak ve gerekli ekleme, güncelleştirme gerçekleştirmek için belirli saklı yordamlar belirlemek ve siler, veritabanındaki verilerle çalışmak için gerekli. Varlık sınıflarınızı görünümleriyle eşleme, varsayılan davranışı gibi değil oluşturulduğunda, aynı zamanda bunu yapabilirsiniz. Ayrıca, veritabanı saklı yordamlar aracılığıyla tablo erişim gerektirdiğinde varsayılan güncelleştirme davranışı geçersiz kılabilirsiniz. Daha fazla bilgi için [özelleştirme işlemleri tarafından kullanarak saklı yordamlar](http://msdn.microsoft.com/library/aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a).  
  
> [!NOTE]
>  Bu izlenecek yolda kullanılabilirliğini gerektirir **Insertcustomer**, **UpdateCustomer**, ve **DeleteCustomer** saklı yordamlar için Northwind veritabanı. Bu saklı yordamlar oluşturma hakkında daha fazla bilgi için bkz. [izlenecek yol: güncelleştirme saklı yordamlar oluşturma'için Northwind Customers tablosunu](../data-tools/walkthrough-creating-update-stored-procedures-for-the-northwind-customers-table.md).  
  
 Bu izlenecek yol, ' % s'varsayılan LINQ için saklı yordamları kullanarak verileri bir veritabanına geri kaydediliyor SQL çalışma zamanı davranışı için geçersiz kılmak için izlemeniz gereken adımları sağlar.  
  
 Bu kılavuz boyunca aşağıdaki görevlerin nasıl gerçekleştirileceğini öğreneceksiniz:  
  
-   Yeni bir Windows Forms uygulaması oluşturma ve ekleme bir [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] ona dosya.  
  
-   Northwind Customers tablosuna eşlendi bir varlık sınıfı oluşturun.  
  
-   LINQ to SQL müşteri sınıfı başvuran bir nesne veri kaynağı oluşturun.  
  
-   İçeren bir Windows formu oluşturma bir <xref:System.Windows.Forms.DataGridView> müşteri sınıfa bağlı.  
  
-   Uygulama işlevselliği formu için kaydedin.  
  
-   Oluşturma <xref:System.Data.Linq.DataContext> ekleyerek yöntemleri saklı yordamlar için [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
-   Müşteri sınıf ekleme, güncelleştirme ve silme gerçekleştirmek için saklı yordamları kullanmak için yapılandırın.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdakiler gerekir:  
  
-   Northwind örnek veritabanındaki SQL Server sürümünü erişim. Daha fazla bilgi için [nasıl yapılır: örnek veritabanları yükleme](../data-tools/how-to-install-sample-databases.md).  
  
-   **Insertcustomer**, **UpdateCustomer**, ve **DeleteCustomer** saklı yordamlar için Northwind veritabanı. Daha fazla bilgi için [izlenecek yol: güncelleştirme saklı yordamlar oluşturma'için Northwind Customers tablosunu](../data-tools/walkthrough-creating-update-stored-procedures-for-the-northwind-customers-table.md).  
  
## <a name="creating-an-application-and-adding-linq-to-sql-classes"></a>Uygulama oluşturma ve SQL sınıflarına LINQ ekleme  
 İle çalışacaksınız çünkü [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] sınıfları ve bir Windows formunda veri görüntüleme, yeni bir Windows Forms uygulaması oluşturma ve LINQ to SQL sınıfları dosyasına ekleyin.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-create-a-new-windows-application-project-that-contains-linq-to-sql-classes"></a>SQL sınıflarına LINQ içeren yeni bir Windows uygulaması projesi oluşturmak için  
  
1.  Gelen **dosya** menüsünden Yeni bir proje oluşturun.  
  
2.  Projeyi adlandırın **UpdatingwithSProcsWalkthrough**.  
  
    > [!NOTE]
    >  [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] Desteklenir [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ve C# projeleri. Bu nedenle, yeni projeyi bu dillerden birinde oluşturun.  
  
3.  Tıklayın **Windows Forms uygulaması** şablonu ve tıklatın **Tamam**. Daha fazla bilgi için [istemci uygulamaları](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68).  
  
     UpdatingwithSProcsWalkthrough projesi oluşturulur ve eklenen **Çözüm Gezgini**.  
  
4.  Üzerinde **proje** menüsünü tıklatın **Yeni Öğe Ekle**.  
  
5.  Tıklayın **LINQ to SQL sınıfları** şablonu ve türü **Northwind.dbml** içinde **adı** kutusu.  
  
6.  **Ekle**'yi tıklatın.  
  
     Boş bir LINQ SQL sınıfları dosyasına (Northwind.dbml) projeye eklenir ve [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] açılır.  
  
## <a name="creating-the-customer-entity-class-and-object-data-source"></a>Nesne veri kaynağı ve müşteri varlık sınıfı oluşturma  
 Oluşturma [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] veritabanı tablolarıyla tablolardan sürükleyerek eşleştirilir sınıf **Sunucu Gezgini**/**veritabanı Gezgini** üzerine [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. Sonuç, veritabanındaki tabloları eşleştirmek SQL varlık sınıflarına LINQ olur. Varlık sınıflarının oluşturduktan sonra ortak özelliklere sahip diğer sınıflar gibi nesne veri kaynağı olarak kullanılabilir.  
  
#### <a name="to-create-a-customer-entity-class-and-configure-a-data-source-with-it"></a>Bir müşteri varlık sınıfı oluşturmak ve bir veri kaynağı ile yapılandırmak için  
  
1.  İçinde **Sunucu Gezgini**/**veritabanı Gezgini**, Northwind örnek veritabanındaki SQL Server sürümünde Müşteri tablosunu bulun. Daha fazla bilgi için [nasıl yapılır: Northwind veritabanına bağlanmak](../data-tools/how-to-connect-to-the-northwind-database.md).  
  
2.  Sürükleme **müşteriler** düğümünden **Sunucu Gezgini**/**veritabanı Gezgini** üzerine [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] yüzeyi.  
  
     Adlı bir varlık sınıfı **müşteri** oluşturulur. Müşteriler tablosundaki sütunlara karşılık gelen özelliklerle var. Varlık sınıfı adlı **müşteri** (değil **müşteriler**) olduğundan Müşteriler tablosundan tek bir müşteri temsil eder.  
  
    > [!NOTE]
    >  Bu yeniden adlandırma adlandırılır *çoğullaştırma*. Bunu açılıp kapatılabilir [Seçenekler iletişim kutusu](../ide/reference/options-dialog-box-visual-studio.md). Daha fazla bilgi için [nasıl yapılır: açma ve kapatma (O/R Tasarımcısı) çoğullaştırma kapatma](../data-tools/how-to-turn-pluralization-on-and-off-o-r-designer.md).  
  
3.  Üzerinde **derleme** menüsünde tıklatın **derleme UpdatingwithSProcsWalkthrough** Projeyi derlemek için.  
  
4.  Üzerinde **veri** menüsünü tıklatın **veri kaynaklarını Göster**.  
  
5.  İçinde **veri kaynakları** penceresinde tıklayın **yeni veri kaynağı Ekle**.  
  
6.  Tıklayın **nesne** üzerinde **bir veri kaynağı türü seçin** sayfasında ve ardından **sonraki**.  
  
7.  Genişletin **UpdatingwithSProcsWalkthrough** düğümünü bulun ve seçin **müşteri** sınıfı.  
  
    > [!NOTE]
    >  Varsa **müşteri** sınıf kullanılabilir değil, Sihirbazı iptal etmeniz, projeyi derleyin ve sihirbazı yeniden çalıştırın.  
  
8.  Tıklayın **son** veri kaynağı oluşturma ve ekleme **müşteri** varlık sınıfı için **veri kaynakları** penceresi.  
  
## <a name="creating-a-datagridview-to-display-the-customer-data-on-a-windows-form"></a>Müşteri verilerini bir Windows formunda görüntülemek için bir DataGridView oluşturma  
 Varlık sınıflarına sürükleyerek bağlı denetimler oluşturmak [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] veri kaynağı öğelerinden **veri kaynakları** penceresini bir Windows Form üzerine.  
  
#### <a name="to-add-controls-that-are-bound-to-the-entity-classes"></a>Varlık sınıflarına bağlı denetimler eklemek için  
  
1.  Form1 Tasarım Görünümü'nde açın.  
  
2.  Gelen **veri kaynakları** penceresinde Sürükle **müşteri** düğümünü Form1 üzerine.  
  
    > [!NOTE]
    >  Görüntülenecek **veri kaynakları** penceresinde tıklayın **veri kaynaklarını Göster** üzerinde **veri** menüsü.  
  
3.  Form1 kod Düzenleyicisi'nde açın.  
  
4.  Genel form, belirli herhangi bir yöntemi dışında ancak Form1 sınıf içinde formuna aşağıdaki kodu ekleyin:  
  
    ```vb  
    Private NorthwindDataContext1 As New NorthwindDataContext  
    ```  
  
    ```csharp  
    private NorthwindDataContext northwindDataContext1  
        = new NorthwindDataContext();  
  
    ```  
  
5.  İçin bir olay işleyicisi oluşturun `Form_Load` olay işleyicisine aşağıdaki kodu ekleyin:  
  
    ```vb  
    CustomerBindingSource.DataSource = NorthwindDataContext1.Customers  
    ```  
  
    ```csharp  
    customerBindingSource.DataSource  
        = northwindDataContext1.Customers;  
  
    ```  
  
## <a name="implementing-save-functionality"></a>İşlevlerini uygulama  
 Varsayılan olarak Kaydet düğmesi etkin değildir ve kaydetme işlevinin uygulanmadı. Ayrıca, kod verilere bağlı denetimler nesnesi veri kaynakları için oluşturulan, değiştirilen verileri veritabanına kaydetmek için otomatik olarak eklenmez. Bu bölümde, kaydetmeyi etkinleştirmek açıklanmaktadır düğmesine tıklayın ve işlevselliği için Kaydet uygulamak [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] nesneleri.  
  
#### <a name="to-implement-save-functionality"></a>İşlevselliği uygulamak için  
  
1.  Form1 Tasarım Görünümü'nde açın.  
  
2.  Kaydet'i seçin düğmesini **CustomerBindingNavigator** (düğme disket simgesi ile).  
  
3.  İçinde **özellikleri** penceresinde **etkin** özelliğini **True**.  
  
4.  Bir olay işleyicisi oluşturun ve kod düzenleyicisine geçmek için Kaydet düğmesine çift tıklayın.  
  
5.  Kaydetme aşağıdaki kodu ekleyin düğmesi olay işleyicisi:  
  
    ```vb  
    NorthwindDataContext1.SubmitChanges()  
    ```  
  
    ```csharp  
    northwindDataContext1.SubmitChanges();  
    ```  
  
## <a name="overriding-the-default-behavior-for-performing-updates-inserts-updates-and-deletes"></a>Güncellemelerini (ekleme, güncelleştirme ve silme) için varsayılan davranışı geçersiz kılma  
  
#### <a name="to-override-the-default-update-behavior"></a>Güncelleştirme varsayılan davranışı geçersiz kılmak için  
  
1.  LINQ to SQL dosyasını açın [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. (Çift **Northwind.dbml** dosyası **Çözüm Gezgini**.)  
  
2.  İçinde **Sunucu Gezgini**/**veritabanı Gezgini**, Northwind veritabanı genişletin **saklı yordamlar** düğümünü bulun  **InsertCustomers**, **UpdateCustomers**, ve **DeleteCustomers** saklı yordamlar.  
  
3.  Üç tüm saklı yordamları üzerine sürükleyin [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
     Yöntemler bölmesini saklı yordamları eklenir <xref:System.Data.Linq.DataContext> yöntemleri. Daha fazla bilgi için [DataContext yöntemi (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md).  
  
4.  Seçin **müşteri** varlık sınıfında [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
5.  İçinde **özellikleri** penceresinde **Ekle** özelliği.  
  
6.  Yanındaki üç nokta (...) tıklayın **kullanım çalışma zamanı** açmak için **davranışı Yapılandır** iletişim kutusu.  
  
7.  Seçin **özelleştirme**.  
  
8.  Seçin **InsertCustomers** yönteminde **Özelleştir** listesi.  
  
9. Tıklayın **Uygula** seçilen sınıf ve davranış için yapılandırmayı kaydetmek için.  
  
    > [!NOTE]
    >  Tıkladığınız sürece her bir sınıf/davranışını bileşimi davranışını yapılandırmak devam **Uygula** her değişikliği yaptıktan sonra. Tıklamadan önce sınıf veya davranış değiştirirseniz **Uygula**, bir uyarı iletişim kutusu sağlama değişiklikleri uygulamak için bir fırsat görünür.  
  
10. Seçin **güncelleştirme** içinde **davranışı** listesi.  
  
11. Seçin **özelleştirme**.  
  
12. Seçin **UpdateCustomers** yönteminde **Özelleştir** listesi.  
  
     Listesini denetleyin **yöntem bağımsız değişkenleri** ve **sınıfı özellikleri** ve iki olduğuna dikkat edin **yöntem bağımsız değişkenleri** ve iki **sınıfı özellikleri**tabloda bazı sütunları için. Bu, değişiklikleri izlemek ve denetlemek için eşzamanlılık ihlalleri deyimlerini oluşturmak kolaylaştırır.  
  
13. Harita **Original_CustomerID** metot bağımsız değişkeni **CustomerID (özgün)** sınıf özelliği.  
  
    > [!NOTE]
    >  Adları eşleştiğinde varsayılan olarak, yöntem bağımsız değişkenleri sınıfın özelliklerine eşlenir. Özellik adlarının değiştirilir ve tablo arasında varlık sınıfı artık eşleşen, O/R Tasarımcısı doğru Eşleme belirleyemiyorsa eşlemek için eşdeğer sınıf özelliği seçmek olabilir. Yöntem bağımsız değişkenleri eşlemek için geçerli bir sınıf özellikleri yoksa, ayrıca, ayarlayabilirsiniz **sınıfı özellikleri** değerini **(hiçbiri)**.  
  
14. Tıklayın **Uygula** seçilen sınıf ve davranış için yapılandırmayı kaydetmek için.  
  
15. Seçin **Sil** içinde **davranışı** listesi.  
  
16. Seçin **özelleştirme**.  
  
17. Seçin **DeleteCustomers** yönteminde **Özelleştir** listesi.  
  
18. Harita **Original_CustomerID** metot bağımsız değişkeni **CustomerID (özgün)** sınıf özelliği.  
  
19. **Tamam**'ı tıklatın.  
  
> [!NOTE]
>  Bu belirli yönlendirme sorunu olmasa da, hatalarının ayıklanabileceğini belirtmekte yarar [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] ekleme sırasında otomatik olarak kimlik (otomatik artış), rowguıdcol (veritabanı tarafından oluşturulan GUID) ve zaman damgası sütunları için veritabanı tarafından oluşturulan değerleri işleme ve güncelleştirmeler. Veritabanı üretilmiş değerler diğer sütun türlerinde beklenmedik bir null değer neden olur. Veritabanı tarafından oluşturulan değerleri döndürülecek el ile ayarlamanız <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> için `true` ve <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> aşağıdakilerden birine: <xref:System.Data.Linq.Mapping.AutoSync>, <xref:System.Data.Linq.Mapping.AutoSync>, veya <xref:System.Data.Linq.Mapping.AutoSync>.  
  
## <a name="testing-the-application"></a>Uygulamayı Test Etme  
 Yeniden doğrulamak için uygulamayı çalıştırmak **UpdateCustomers** saklı yordam doğru veritabanında müşteri kaydı güncelleştirir.  
  
#### <a name="to-test-the-application"></a>Uygulamayı test etmek için  
  
1.  F5 tuşuna basın.  
  
2.  Bir kaydı Güncelleştirme davranışı test kılavuza değiştirin.  
  
3.  INSERT davranışı test etmek için yeni bir kayıt ekleyin.  
  
4.  Değişiklikleri veritabanına kaydetmek için Kaydet düğmesine tıklayın.  
  
5.  Formu kapatın.  
  
6.  F5 tuşuna basın ve güncelleştirilen kaydı ve yeni eklenen kaydı kalıcı olduğunu doğrulayın.  
  
7.  Yeni oluşturduğunuz kaydı silme silme davranışını test etmek için 3. adımı.  
  
8.  Kaydet'e tıklayın düğmesine veritabanından silinen kaydı kaldırmak ve değişiklikleri gönderme  
  
9. Formu kapatın.  
  
10. F5 tuşuna basın ve Silinen kaydı veritabanından kaldırıldığını doğrulayın.  
  
    > [!NOTE]
    >  Uygulamanızı değerini bağlı olarak SQL Server Express Edition kullanıyorsa **çıkış dizinine Kopyala** özelliği veritabanı dosyasının değişiklikleri adım 10 F5 tuşuna bastığınızda görünmeyebilir. Daha fazla bilgi için [nasıl yapılır: Manage Local Data Files in Your Project](../data-tools/how-to-manage-local-data-files-in-your-project.md).  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Uygulama gereksinimlerinize bağlı olarak, oluşturduktan sonra gerçekleştirmek isteyebileceğiniz birkaç adım vardır [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] varlık sınıfları. Bu uygulama için yapabileceğiniz bazı geliştirmeler şunları içerir:  
  
-   Eşzamanlılık denetimi sırasında güncelleştirmeleri uygulayın. Bilgi için [iyimser eşzamanlılık: genel bakış](http://msdn.microsoft.com/library/c2e38512-d0c8-4807-b30a-cb7e30338694).  
  
-   Verilere filtre uygulamak için LINQ sorguları ekleyin. Bilgi için [(C#) LINQ sorgularına giriş](http://msdn.microsoft.com/library/37895c02-268c-41d5-be39-f7d936fa88a8).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ to SQL araçlarını Visual Studio'da](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [LINQ to SQL sorguları](http://msdn.microsoft.com/library/f4897aaa-7f44-4c20-a471-b948c2971aae)   
 [DataContext yöntemi (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md)   
 [Nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atama](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)   
 [PAVE veri uygulaması geliştirme Visual Studio 2012'deki yenilikler](http://msdn.microsoft.com/en-us/3d50d68f-5f44-4915-842f-6d42fce793f1)

