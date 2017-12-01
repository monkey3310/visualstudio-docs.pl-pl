---
title: "Dodawanie formantów do dokumentów pakietu Office w czasie wykonywania | Dokumentacja firmy Microsoft"
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
- Office documents [Office development in Visual Studio, Windows Forms controls
- host controls [Office development in Visual Studio], adding
- Windows Forms controls [Office development in Visual Studio], adding
- Office documents [Office development in Visual Studio, host controls
- user controls [Office development in Visual Studio], adding at run time
- documents [Office development in Visual Studio], Windows Forms controls
- document-level customizations [Office development in Visual Studio], host controls
- documents [Office development in Visual Studio], host controls
- document-level customizations [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], adding at run time
- helper methods [Office development in Visual Studio]
ms.assetid: 4f43b3eb-f0ec-44e2-9885-6ede327c6913
caps.latest.revision: "102"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: db8a4fad73bb710662ce63bd299751c725e0c6ce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="adding-controls-to-office-documents-at-run-time"></a>Dodawanie formantów do dokumentów pakietu Office w czasie wykonywania
  Można dodawać formanty do dokumentu programu Microsoft Office Word i Microsoft Office Excel skoroszytu w czasie wykonywania. Można również usunąć je w czasie wykonywania. Formanty, które są dodawane lub usuwane w czasie wykonywania są nazywane *formantów dynamicznych*.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
 W tym temacie opisano następujące czynności:  
  
-   [Zarządzanie formantów w czasie wykonywania za pomocą kolekcji kontroli](#ControlsCollection).  
  
-   [Dodawanie do dokumentów kontrolki hosta](#HostControls).  
  
-   [Dodawanie formantów formularzy systemu Windows do dokumentów](#WindowsForms).  
  
 ![łącze do wideo](../vsto/media/playvideo.gif "łącze do wideo") dla powiązanych pokaz wideo, zobacz [jak czy I: Dodaj formanty do powierzchni dokumentu w czasie wykonywania?](http://go.microsoft.com/fwlink/?LinkId=132782).  
  
##  <a name="ControlsCollection"></a>Zarządzanie formantów w czasie wykonywania za pomocą kolekcji formantu  
 Aby dodać, pobrać lub usunąć formantów w czasie wykonywania, należy użyć metody pomocnika <xref:Microsoft.Office.Tools.Excel.ControlCollection> i <xref:Microsoft.Office.Tools.Word.ControlCollection> obiektów.  
  
 Sposób uzyskać dostępu do tych obiektów, zależy od typu projektu, który tworzysz:  
  
-   W projekcie poziomie dokumentu dla programu Excel, użyj <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> właściwość `Sheet1`, `Sheet2`, i `Sheet3` klasy. Aby uzyskać więcej informacji na temat tych klas, zobacz [element hosta arkusza](../vsto/worksheet-host-item.md).  
  
-   W projekcie poziomie dokumentu dla programu Word, użyj <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> właściwość `ThisDocument` klasy. Aby uzyskać więcej informacji na temat tej klasy, zobacz [element hosta dokumentu](../vsto/document-host-item.md).  
  
-   W projekcie dodatku narzędzi VSTO dla programu Excel lub Word, użyj właściwości kontrolki <xref:Microsoft.Office.Tools.Excel.Worksheet> lub <xref:Microsoft.Office.Tools.Word.Document> generowany w czasie wykonywania. Aby uzyskać więcej informacji na temat generowania tych obiektów w czasie wykonywania, zobacz [Rozszerzanie dokumentów programu Word i skoroszytów programu Excel w dodatkach VSTO w czasie wykonywania](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
### <a name="adding-controls"></a>Dodawanie formantów  
 <xref:Microsoft.Office.Tools.Excel.ControlCollection> i <xref:Microsoft.Office.Tools.Word.ControlCollection> typy metody pomocnicze, które można dodać kontrolki hosta i typowych formantów formularzy systemu Windows do dokumentów i arkuszy. Każda nazwa metody ma format `Add` *kontrolować klasy*, gdzie *kontrolować klasy* jest nazwą klasy formantu, który chcesz dodać. Na przykład, aby dodać <xref:Microsoft.Office.Tools.Excel.NamedRange> formantu do dokumentu, użyj <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddNamedRange%2A> metody.  
  
 Poniższy przykładowy kod dodaje <xref:Microsoft.Office.Tools.Excel.NamedRange> do `Sheet1` w projektach na poziomie dokumentu dla programu Excel.  
  
 [!code-vb[Trin_ExcelWorkbookDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/ThisWorkbook.vb#3)]
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#3](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/ThisWorkbook.cs#3)]  
  
### <a name="accessing-and-deleting-controls"></a>Uzyskiwanie dostępu i usuwanie kontrolek  
 Można użyć właściwości Controls elementu <xref:Microsoft.Office.Tools.Excel.Worksheet> lub <xref:Microsoft.Office.Tools.Word.Document> do iterowania po wszystkich kontrolek w dokumencie, łącznie z formantami dodawanymi w czasie projektowania. Formanty dodane w czasie projektowania są również nazywane *formantów statycznych*.  
  
 Możesz usunąć formantów dynamicznych przez wywołanie metody Delete sterowania lub przez wywołanie metody Usuń wszystkich kolekcji formantów. Poniższy przykład kodu wykorzystuje <xref:Microsoft.Office.Tools.Excel.ControlCollection.Remove%2A> metodę, aby usunąć <xref:Microsoft.Office.Tools.Excel.NamedRange> z `Sheet1` w projektach na poziomie dokumentu dla programu Excel.  
  
 [!code-vb[Trin_ExcelWorkbookDynamicControls#4](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/ThisWorkbook.vb#4)]
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#4](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/ThisWorkbook.cs#4)]  
  
 Nie można usunąć statyczne formantów w czasie wykonywania. Próba usunięcia statyczną kontrolkę, przy użyciu metody Delete lub usuń <xref:Microsoft.Office.Tools.CannotRemoveControlException> zostanie wygenerowany.  
  
> [!NOTE]  
>  Nie usuwaj programowo formantów w `Shutdown` obsługi zdarzeń dokumentu. Elementy interfejsu użytkownika dokumentu nie będą dostępne podczas `Shutdown` zdarzenia. Jeśli chcesz usunąć formanty przed zamknięciem dokumentu, Dodaj swój kod obsługi zdarzeń dla innego zdarzenia, takie jak <xref:Microsoft.Office.Tools.Word.Document.BeforeClose> lub <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> dla programu Word, lub <xref:Microsoft.Office.Tools.Excel.Workbook.BeforeClose>, lub <xref:Microsoft.Office.Tools.Excel.Workbook.BeforeSave> dla programu Excel.  
  
##  <a name="HostControls"></a>Dodawanie do dokumentów formanty hosta  
 Po dodaniu programowo hosta formantów do dokumentów, należy podać nazwę, która unikatowo identyfikuje formant i musisz określić, gdzie można dodać kontrolki w dokumencie. Aby uzyskać szczegółowe instrukcje zobacz następujące tematy:  
  
-   [Porady: dodawanie formantów ListObject do arkuszy](../vsto/how-to-add-listobject-controls-to-worksheets.md)  
  
-   [Porady: dodawanie formantów NamedRange do arkuszy](../vsto/how-to-add-namedrange-controls-to-worksheets.md)  
  
-   [Porady: dodawanie formantów wykresu do arkuszy](../vsto/how-to-add-chart-controls-to-worksheets.md)  
  
-   [Porady: dodawanie formantów zawartości do dokumentów programu Word](../vsto/how-to-add-content-controls-to-word-documents.md)  
  
-   [Porady: dodawanie formantów zakładek do dokumentów programu Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)  
  
 Aby uzyskać informacje o formantach hosta, zobacz [elementów hosta i informacje o formantach hosta](../vsto/host-items-and-host-controls-overview.md).  
  
 Gdy dokumentu jest zapisane, a następnie zamknięte, wszystkie formanty hosta utworzony dynamicznie zostały odłączone od ich zdarzeń i utracą ich funkcji wiązania danych. Można dodać kod do rozwiązania, aby ponownie utworzyć formanty hosta po otwarciu dokumentu. Aby uzyskać więcej informacji, zobacz [przechowywanie formantów dynamicznych w dokumentach pakietu Office](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
> [!NOTE]  
>  Metody pomocnicze nie są dostarczane dla następujących hostowania formantów, ponieważ tych kontrolek nie można dodać programistycznie do dokumentów: <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>, <xref:Microsoft.Office.Tools.Word.XMLNode>, i <xref:Microsoft.Office.Tools.Word.XMLNodes>.  
  
##  <a name="WindowsForms"></a>Dodawanie Windows Forms formantów do dokumentów  
 Po dodaniu programowo formantu formularzy systemu Windows do dokumentu, należy podać lokalizację formantu i nazwy, które jednoznacznie identyfikuje formant. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Udostępnia metody pomocy dla każdego formantu. Te metody są przeciążone tak, aby można przekazać zakres lub określone współrzędne lokalizacji kontrolki.  
  
 Gdy dokumentu jest zapisane, a następnie zamknięte, wszystkie formanty formularzy systemu Windows utworzony dynamicznie zostaną usunięte z dokumentu. Można dodać kod do rozwiązania, aby ponownie utworzyć formantów po otwarciu dokumentu. Jeśli utworzysz dynamiczne formanty formularzy systemu Windows przy użyciu dodatku VSTO otoki ActiveX formantów pozostają w dokumencie. Aby uzyskać więcej informacji, zobacz [przechowywanie formantów dynamicznych w dokumentach pakietu Office](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
> [!NOTE]  
>  Formanty formularzy systemu Windows nie można dodać programistycznie do dokumentów chronionych. Jeśli nie można programistycznie Chroń, dokumentu programu Word lub arkuszu programu Excel, aby dodać kontrolkę, należy napisać dodatkowy kod w celu usunięcia formantu ActiveX otoki, gdy dokument zostanie zamknięty. Kontrolki ActiveX otoki nie zostanie automatycznie usunięta z chronionych dokumentów.  
  
### <a name="adding-custom-controls"></a>Dodawanie formantów niestandardowych  
 Jeśli chcesz dodać <xref:System.Windows.Forms.Control> nie jest obsługiwana przez metody pomocnika dostępne, takich jak kontrola użytkownika niestandardowego, należy użyć następujących metod:  
  
-   Dla programu Excel, użyj jednej z <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddControl%2A> metody <xref:Microsoft.Office.Tools.Excel.ControlCollection> obiektu.  
  
-   Dla programu Word, użyj jednej z <xref:Microsoft.Office.Tools.Word.ControlCollection.AddControl%2A> metody <xref:Microsoft.Office.Tools.Word.ControlCollection> obiektu.  
  
 Aby dodać kontrolki, należy przekazać <xref:System.Windows.Forms.Control>, lokalizacji dla formantu oraz nazwę, która unikatowo identyfikuje formant do metody AddControl. Metoda AddControl zwraca obiekt definiujący jak kontrolki współdziała z arkusza kalkulacyjnego lub dokumentu. Zwraca metodę AddControl <xref:Microsoft.Office.Tools.Excel.ControlSite> (dla programu Excel) lub <xref:Microsoft.Office.Tools.Word.ControlSite> obiektu (dla programu Word).  
  
 Poniższy przykład kodu pokazuje sposób użycia <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddControl%2A> metody dynamiczne dodawanie formantu niestandardowego użytkownika do arkusza w projektach na poziomie dokumentu programu Excel. W tym przykładzie kontrolki użytkownika o nazwie `UserControl1`i <xref:Microsoft.Office.Interop.Excel.Range> nosi nazwę `range1`. Aby użyć tego przykładu, uruchom go z `Sheet`  *n*  klasy w projekcie.  
  
 [!code-vb[Trin_VstcoreProgrammingControlsExcel#2](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#2)]
 [!code-csharp[Trin_VstcoreProgrammingControlsExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#2)]  
  
### <a name="using-members-of-custom-controls"></a>Przy użyciu elementów członkowskich niestandardowych kontrolek  
 Przy użyciu jednej z metod AddControl Dodawanie formantu do arkusza lub dokument, teraz są dwa obiekty inny formant:  
  
-   <xref:System.Windows.Forms.Control> Reprezentujący kontrolkę niestandardową.  
  
-   Obiekt ControlSite, OLEObject lub OLEControl reprezentujący kontrolkę po został dodany do arkusza lub dokumentu.  
  
 Wiele właściwości i metody są wspólne dla tych kontrolek. Jest ważne, dostęp do tych elementów członkowskich za pomocą odpowiedniej kontrolki:  
  
-   Aby uzyskać dostęp do elementów członkowskich, które należeć tylko do kontrolki niestandardowej, należy użyć <xref:System.Windows.Forms.Control>.  
  
-   Aby uzyskać dostęp do elementów członkowskich, które są udostępniane przez formanty, użyj obiektu ControlSite, OLEObject lub OLEControl.  
  
 Jeśli dostęp do udostępnionego elementu członkowskiego z <xref:System.Windows.Forms.Control>, może być niemożliwe bez ostrzeżenia lub powiadomienie, lub może spowodować nieprawidłowe wyniki. Zawsze używaj metody lub właściwości obiektu ControlSite, OLEObject lub OLEControl, chyba że ta metoda lub właściwość potrzebne nie jest dostępna; następnie należy można odwoływać się <xref:System.Windows.Forms.Control>.  
  
 Na przykład zarówno <xref:Microsoft.Office.Tools.Excel.ControlSite> klasy i <xref:System.Windows.Forms.Control> klasy mają właściwość Top. Aby pobrać lub ustawić odległość między górną krawędzią formantu a górnej części dokumentu, należy użyć <xref:Microsoft.Office.Tools.Excel.ControlSite.Top%2A> właściwość <xref:Microsoft.Office.Tools.Excel.ControlSite>, a nie <xref:System.Windows.Forms.Control.Top%2A> właściwość <xref:System.Windows.Forms.Control>.  
  
 [!code-vb[Trin_VstcoreProgrammingControlsExcel#3](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#3)]
 [!code-csharp[Trin_VstcoreProgrammingControlsExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#3)]  
  
## <a name="see-also"></a>Zobacz też  
 [Formanty w dokumentach pakietu Office](../vsto/controls-on-office-documents.md)   
 [Przechowywanie formantów dynamicznych w dokumentach pakietu Office](../vsto/persisting-dynamic-controls-in-office-documents.md)   
 [Porady: dodawanie formantów ListObject do arkuszy](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Porady: dodawanie formantów NamedRange do arkuszy](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Porady: dodawanie formantów wykresu do arkuszy](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [Porady: dodawanie formantów zawartości do dokumentów programu Word](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Porady: dodawanie formantów zakładek do dokumentów programu Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Formanty formularzy Windows w przegląd dokumentów pakietu Office](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Porady: dodawanie formantów do dokumentów pakietu Office formularzy systemu Windows](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   