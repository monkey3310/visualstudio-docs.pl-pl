---
title: 'Porady: programowane ukrywanie arkuszy | Dokumentacja firmy Microsoft'
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
- hidden worksheets
- worksheets, hiding
ms.assetid: 3208f633-137f-47f9-9c9c-2cf8e3c72096
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ef9d6e72f7d69e3b71b8ea6f6acea9021be6b2cf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-hide-worksheets"></a>Porady: Programowane ukrywanie arkuszy
  Możesz wyświetlić lub ukryć żadnych arkusza w skoroszycie. Aby ukryć arkusza, użyj element hosta arkusza lub dostęp do arkusza przy użyciu kolekcji arkuszy skoroszytu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-the-worksheet-host-item"></a>Przy użyciu element hosta arkusza  
 Jeśli arkusz został dodany w czasie projektowania w dostosowaniu poziomie dokumentu, użyj <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> Ukryj określony arkusz właściwości.  
  
#### <a name="to-hide-a-worksheet-using-a-worksheet-host-item"></a>Aby ukryć arkuszu za pomocą element hosta arkusza  
  
1.  Ustaw <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> właściwość `Sheet1` element hosta do <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> wartości wyliczenia.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#25)]  
  
## <a name="using-the-sheets-collection-of-the-excel-workbook"></a>Przy użyciu kolekcji arkuszy skoroszytu programu Excel  
 Dostęp do arkuszy za pomocą programu Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Sheets> kolekcji w następujących przypadkach:  
  
-   Chcesz ukryć arkusza w dodatku VSTO.  
  
-   Arkusz, który chcesz ukryć został utworzony w czasie wykonywania w dostosowaniu poziomie dokumentu.  
  
#### <a name="to-hide-a-worksheet-using-the-sheets-collection-of-the-excel-workbook"></a>Aby ukryć arkuszu za pomocą kolekcji arkuszy skoroszytu programu Excel  
  
1.  Ustaw <xref:Microsoft.Office.Interop.Excel.Worksheets.Visible%2A> właściwości arkusza, aby <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> wartości wyliczenia.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#26)]  
  
## <a name="see-also"></a>Zobacz też  
 [Praca z arkuszami](../vsto/working-with-worksheets.md)   
 [Porady: programowane usuwanie arkuszy ze skoroszytu](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Porady: programowane przenoszenie arkuszy w obrębie skoroszytu](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Porady: programowane Włączanie ochrony arkuszy](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Obiekty hosta i informacje o formantach hosta](../vsto/host-items-and-host-controls-overview.md)   
 [Globalny dostęp do obiektów w projektach pakietu Office](../vsto/global-access-to-objects-in-office-projects.md)  
  