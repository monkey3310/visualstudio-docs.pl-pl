---
title: 'Porady: programowane drukowanie dokumentów'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], printing documents
- documents [Office development in Visual Studio], printing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6c1e34e723618d24870d76dd961e7f4c484bc6fd
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "35676184"
---
# <a name="how-to-programmatically-print-documents"></a>Porady: programowane drukowanie dokumentów
  Możesz wydrukować cały dokument programu Microsoft Office Word lub części dokumentu, do drukarki domyślnej.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="print-a-document-that-is-part-of-a-document-level-customization"></a>Drukuj dokument, który jest częścią dostosowywania poziomie dokumentu  
  
### <a name="to-print-the-entire-document"></a>Aby wydrukować cały dokument  
  
1.  Wywołaj <xref:Microsoft.Office.Tools.Word.Document.PrintOut%2A> metody `ThisDocument` klasy w projekcie, aby wydrukować cały dokument. Aby użyć tego przykładu, należy uruchomić kod z `ThisDocument` klasy.  
  
     [!code-vb[Trin_VstcoreWordAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#11)]
     [!code-csharp[Trin_VstcoreWordAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#11)]  
  
### <a name="to-print-the-current-page-of-the-document"></a>Aby wydrukować bieżącą stronę dokumentu  
  
1.  Wywołaj <xref:Microsoft.Office.Tools.Word.Document.PrintOut%2A> metody `ThisDocument` klasy w projekcie i określić, że wydrukowana jedna kopia bieżącej strony. Aby użyć tego przykładu, należy uruchomić kod z `ThisDocument` klasy.  
  
     [!code-vb[Trin_VstcoreWordAutomation#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#12)]
     [!code-csharp[Trin_VstcoreWordAutomation#12](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#12)]  
  
## <a name="print-a-document-by-using-a-vsto-add-in"></a>Drukowanie dokumentu za pomocą dodatku narzędzi VSTO  
  
### <a name="to-print-an-entire-document"></a>Aby wydrukować cały dokument  
  
1.  Wywołaj <xref:Microsoft.Office.Interop.Word._Document.PrintOut%2A> metody <xref:Microsoft.Office.Interop.Word.Document> obiekt, który chcesz wydrukować. Poniższy przykład kodu Drukuje aktywny dokument. Aby użyć tego przykładu, należy uruchomić kod z `ThisAddIn` klasy w projekcie.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#11)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#11](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#11)]  
  
### <a name="to-print-the-current-page-of-a-document"></a>Aby wydrukować bieżącą stronę dokumentu  
  
1.  Wywołaj <xref:Microsoft.Office.Interop.Word._Document.PrintOut%2A> metody <xref:Microsoft.Office.Interop.Word.Document> obiekt, który chcesz wydrukować i określić, że wydrukowana jedna kopia bieżącej strony. Poniższy przykład kodu Drukuje aktywny dokument. Aby użyć tego przykładu, należy uruchomić kod z `ThisAddIn` klasy w projekcie.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#12)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#12](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#12)]  
  
## <a name="see-also"></a>Zobacz także  
 [Parametry opcjonalne w rozwiązaniach pakietu Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  