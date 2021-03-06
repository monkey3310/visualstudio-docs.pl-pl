---
title: Flowchart, Projektant działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Flowchart.UI
- System.Activities.Statements.FlowStep.UI
- System.Activities.Core.Presentation.FlowStart.UI
ms.assetid: d5af2276-5215-4138-880a-cf2b90bbf3a0
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 1fb9c6493390b0f489b2afaf27dc0293748c70a6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681535"
---
# <a name="flowchart-activity-designer"></a>Flowchart, projektant działań
<xref:System.Activities.Statements.Flowchart> To działanie służy do tworzenia przepływów pracy służących do definiowania i zarządzania kontrolek złożonych przepływów. A <xref:System.Activities.Statements.Flowchart> można tworzyć w kodzie lub za pomocą [!INCLUDE[wfd2](../includes/wfd2-md.md)]. Ten temat dokumenty [!INCLUDE[wfd2](../includes/wfd2-md.md)] środowiska. [!INCLUDE[wfd1](../includes/wfd1-md.md)] Projektanta działań przepływu pracy umożliwia deweloperom tworzyć przepływy pracy w sposób naturalny.  
  
## <a name="the-flowchart-activity"></a>Schemat blokowy działania  
 <xref:System.Activities.Statements.Flowchart> Określa unikatową <xref:System.Activities.Statements.Flowchart.StartNode%2A> , jest wykonywany, gdy uruchamia przepływ pracy i używa połączone z siecią <xref:System.Activities.Statements.Flowchart.Nodes%2A> do utworzenia dowolnego pętli lub przekierowywać przepływem wykonania w dowolnym miejscu w przepływie pracy w danym momencie.  
  
### <a name="using-the-flowchart-activity-designer"></a>Za pomocą Flowchart, Projektant działań  
 **Schemat blokowy** projektanta działań można znaleźć w **schemat blokowy** kategorii **przybornika**, które jest dostępne po kliknięciu **przybornika**karcie [!INCLUDE[wfd2](../includes/wfd2-md.md)] (można także wybrać **narzędzi** z **widoku** menu lub klawiszy CTRL + ALT + X.)  
  
 **Schemat blokowy** projektanta działań mogą być przeciągnięte z **przybornika** i porzuconych do [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni wszędzie tam, gdzie Projektanci działań są zazwyczaj umieszczone, jako działania głównego lub jako element podrzędny inny działań przepływu sterowania. Jeśli **schemat blokowy** projektanta działań jest upuszczony na pusty [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni, tworzy on <xref:System.Activities.Statements.Flowchart> działania, które domyślnie prezentowanie się rozwinięty widok, w którym jest węzeł początkowy, który inicjuje wykonywania reprezentowana jako zielony kulki. Jeśli **schemat blokowy** projektanta działań są przenoszone do kolejnego działania przepływu sterowania, wyświetla się w trybie zminimalizowanym widoku, który można rozszerzać przez dwukrotne kliknięcie **schemat blokowy** projektanta działań. Wszelkie działania w **przybornika** można przeciągać bezpośrednio **schemat blokowy** Projektant działań, w tym inne działania przepływu sterowania.  
  
 Po przeciągnięciu różnych Projektanci działań na [!INCLUDE[wfd2](../includes/wfd2-md.md)] kanwy <xref:System.Activities.Activity> obiekty, które reprezentują one mogą być połączone ze sobą, aby określić kolejność wykonywania. Aby utworzyć łącze między działania źródłowego i działanie docelowe, myszy Projektanta działania źródłowego i kwadratowe uchwyty są wyświetlane na każdej stronie. Kliknij jeden z uchwytów, kwadratowych i przeciągnij go, przytrzymując przycisk myszy, aby jeden z uchwytów, które pojawia się w podobny sposób na działanie docelowe, po umieszczeniu wskaźnika myszy nad nim za pomocą myszy. Zwolnij przycisk myszy, a następnie tworzone jest połączenie między te dwa działania, które jest reprezentowany jako strzałka z projektanta źródła do docelowego projektanta.  
  
### <a name="flowchart-activity-properties"></a>Schemat blokowy działania właściwości  
 W poniższej tabeli przedstawiono <xref:System.Activities.Statements.Flowchart> właściwości i w tym artykule opisano, jak są używane w projektancie. Te właściwości można edytować w siatce właściwości lub na powierzchni projektowej.  
  
|Nazwa właściwości|Wymagane|Użycie|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Określa nazwę wyświetlaną, Projektant działań w nagłówku. Wartością domyślną jest blokowy. Wartość może być edytowana w **właściwości** okna lub bezpośrednio w nagłówku projektanta działań.<br /><br /> Mimo że <xref:System.Activities.Activity.DisplayName%2A> nie jest bezwzględnie konieczne jest najlepszym rozwiązaniem, aby użyć jednego.|  
|<xref:System.Activities.Statements.Flowchart.Variables%2A>|False|Kolekcja zmiennych, które są ograniczone w ramach tej <xref:System.Activities.Statements.Flowchart> udostępniania stanu między działania podrzędne.|  
|<xref:System.Activities.Statements.Flowchart.StartNode%2A>|False|<xref:System.Activities.Statements.FlowNode> Oznacza to wykonywane, kiedy <xref:System.Activities.Statements.Flowchart> rozpoczyna się.|  
|<xref:System.Activities.Statements.Flowchart.Nodes%2A>|False|Zawiera kolekcję <xref:System.Activities.Statements.FlowNode> obiekty w <xref:System.Activities.Statements.Flowchart>.|  
  
## <a name="see-also"></a>Zobacz też  
 [Schemat blokowy](../workflow-designer/flowchart-activity-designers.md)   
 [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)   
 [FlowSwitch\<T>](../workflow-designer/flowswitch-t-activity-designer.md)