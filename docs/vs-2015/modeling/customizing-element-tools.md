---
title: Narzędzia dostosowywania elementów | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dac48b6-db68-4bcd-8aa2-422c2ad5d28b
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 91866f93f5a5a10f3a4295c21ee5e2046853ff4c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683545"
---
# <a name="customizing-element-tools"></a>Narzędzia dostosowywania elementów
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Dostosowywanie narzędzi elementów](https://docs.microsoft.com/visualstudio/modeling/customizing-element-tools).  
  
Definicje DSL użytkownik oświadcza koncepcji pojedynczego jako grupy elementów. Na przykład jeśli utworzysz model, w którym składnik ma ustalony zestaw elementów portów, zawsze ma porty, które ma zostać utworzony w tym samym czasie jako ich składnika nadrzędnego. W związku z tym trzeba dostosować narzędzie do tworzenia elementu, więc, że zostanie utworzona grupa elementów zamiast jednego. Aby to osiągnąć, można dostosować, jak narzędzie do tworzenia elementu jest zainicjowany.  
  
 Możesz również zastąpić, co się stanie, gdy narzędzie jest przeciągnięto diagramu lub elementu.  
  
## <a name="customizing-the-content-of-an-element-tool"></a>Dostosowywanie zawartości to narzędzie do elementu  
 Narzędzie każdy element przechowuje wystąpienie <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype> (EGP), który zawiera Zserializowany wersję jednego lub więcej elementów modelu, jak i łącza. Domyślnie EGP narzędzia element zawiera jedno wystąpienie klasy, które określisz dla narzędzia. Tę wartość można zmienić poprzez zastąpienie *YourLanguage*`ToolboxHelper.CreateElementToolPrototype`. Ta metoda jest wywoływana po załadowaniu pakietu języka DSL.  
  
 Parametr metody jest identyfikator klasy, który określiłeś w definicji DSL. Gdy metoda jest wywoływana z klasą, który Cię interesuje, możesz dodać dodatkowe elementy do EGP.  
  
 Mogą zawierać EGP osadzania łącza z jednym elementem głównym do elementów pomocniczych. Może również obejmować linki odwołań.  
  
 Poniższy przykład tworzy elementu głównego i dwóch elementów osadzonych. Główna klasa ma nazwę rezystor i ma dwie relacje osadzania do elementów o nazwie terminalu. Osadzanie właściwości roli są nazywane Terminal1 i Terminal2 i mają liczebność 1..1.  
  
```  
using Microsoft.VisualStudio.Modeling; ...    
public partial class CircuitDiagramToolboxHelper  
{  
  protected override ElementGroupPrototype    CreateElementToolPrototype(Store store, Guid domainClassId)  
  {  
    // A case for each tool to customize:    
    if (domainClassId == Resistor.DomainClassId)  
    {  
      // Set up the prototype elements and links:  
      Resistor resistor = new Resistor(store);  
      resistor.Terminal1 = new Terminal(store);   
      resistor.Terminal2 = new Terminal(store);  
      resistor.Terminal1.Name = "T1"; // embedding  
      resistor.Terminal2.Name = "T2"; // embedding  
      // We could also set up reference links.  
  
      // Create an element group prototype for the toolbox:  
      ElementGroup egp = new ElementGroup(store.DefaultPartition);  
      egp.AddGraph(resistor, true);  
      // We do not have to explicitly include embedded children.  
      return egp.CreatePrototype();  
    }  
    // Element tools for other classes:  
    else  
      return base.CreateElementToolPrototype(store, domainClassId);  
  }  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Dostosowywanie tworzenia i przesuwania elementu](../modeling/customizing-element-creation-and-movement.md)



