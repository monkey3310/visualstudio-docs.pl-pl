---
title: 'Porady: programowane ukrywanie arkuszy'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden worksheets
- worksheets, hiding
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a60a0189af5608496e1f0f415a2d668e896af8e3
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "35677604"
---
# <a name="how-to-programmatically-hide-worksheets"></a>Porady: programowane ukrywanie arkuszy
  Możesz pokazać lub ukryć wszystkie arkusza w skoroszycie. Aby ukryć arkusza, użyj element hosta arkusza lub dostęp do arkusza za pomocą kolekcji arkuszy skoroszytu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="use-the-worksheet-host-item"></a>Użyj element hosta arkusza  
 Jeśli arkusz został dodany w czasie projektowania w dostosowaniu na poziomie dokumentu, należy użyć <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> właściwości, aby ukryć określonego arkusza.  
  
### <a name="to-hide-a-worksheet-using-a-worksheet-host-item"></a>Aby ukryć w arkuszu za pomocą element hosta arkusza  
  
1.  Ustaw <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> właściwość `Sheet1` element hosta do <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> wartość wyliczenia.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#25)]  
  
## <a name="use-the-sheets-collection-of-the-excel-workbook"></a>Korzystać z kolekcji arkuszy skoroszytu programu Excel  
 Dostęp do arkuszy za pomocą programu Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Sheets> kolekcji w następujących przypadkach:  
  
-   Chcesz ukryć arkusza w dodatku VSTO.  
  
-   Arkusz kalkulacyjny, który chcesz ukryć został utworzony w czasie wykonywania w dostosowaniu na poziomie dokumentu.  
  
### <a name="to-hide-a-worksheet-using-the-sheets-collection-of-the-excel-workbook"></a>Aby ukryć w arkuszu za pomocą kolekcji arkuszy skoroszytu programu Excel  
  
1.  Ustaw <xref:Microsoft.Office.Interop.Excel.Worksheets.Visible%2A> właściwości arkusza do <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> wartość wyliczenia.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#26)]  
  
## <a name="see-also"></a>Zobacz także  
 [Praca z arkuszami](../vsto/working-with-worksheets.md)   
 [Porady: programowane usuwanie arkuszy ze skoroszytu](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Porady: programowane przenoszenie arkuszy w obrębie skoroszytu](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Porady: programowane Włączanie ochrony arkuszy](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Host formantów Przegląd obiektów hosta i](../vsto/host-items-and-host-controls-overview.md)   
 [Globalny dostęp do obiektów w projektach pakietu Office](../vsto/global-access-to-objects-in-office-projects.md)  
  