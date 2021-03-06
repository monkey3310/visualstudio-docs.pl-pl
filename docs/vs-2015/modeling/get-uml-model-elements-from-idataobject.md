---
title: Pobieranie elementów modelu UML z IDataObject | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML API, copy and paste
ms.assetid: e0b9cec8-3b93-4a24-8bd3-3e086501d387
caps.latest.revision: 20
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: a69a6f20fdccdce9d8795c68bf0a70c74604428b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680378"
---
# <a name="get-uml-model-elements-from-idataobject"></a>Pobieranie elementów modelu UML z elementu IDataObject
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [elementów modelu UML Pobierz z elementu IDataObject](https://docs.microsoft.com/visualstudio/modeling/get-uml-model-elements-from-idataobject).  
  
Gdy użytkownik przeciągnie elementy z dowolnego źródła na diagramie, przeciągane elementy zostaną zakodowane w `System.Windows.Forms.IDataObject`. Kodowanie jest zależne od typu obiektu źródłowego. Poniższy fragment przedstawia sposób pobierania elementów, gdy źródłem jest UML diagram.  
  
> [!NOTE]
>  Większość operacji, które należy wykonać na modelach UML można wykonać przy użyciu typów w zdefiniowanych zestawach **Microsoft.VisualStudio.Uml.Interfaces** i  **Microsoft.VisualStudio.ArchitectureTools.Extensibility**. Ale w tym celu należy użyć niektórych klas, które są częścią implementacji narzędzia do modelowania UML. Na przykład `ShapeElement` w tym fragmencie nie jest taki sam jak UML `IShape`. Aby zmniejszyć ryzyko wprowadzenia modelu UML i diagramów w niespójnym stanie, są lepiej unikać stosowania metod na tych klasach implementacji, poza przypadkami, gdy nie ma żadnej alternatywy.  
  
## <a name="code-sample"></a>Przykładowy kod  
 Projekt musi odwoływać się do następujących [!INCLUDE[TLA2#tla_net](../includes/tla2sharptla-net-md.md)] zestawów:  
  
 **Microsoft.VisualStudio.Modeling.Sdk. [wersja]**  
  
 **Microsoft.VisualStudio.Modeling.Sdk.Diagrams. [wersja]**  
  
 **Przestrzeń nazw System.Windows.Forms**  
  
```  
using Microsoft.VisualStudio.Modeling;    
  // for ElementGroupPrototype  
using Microsoft.VisualStudio.Modeling.Diagrams;    
  // for ShapeElement, DiagramDragEventArgs, DiagramPointEventArgs  
…   
  /// <summary>  
  /// Retrieves UML IElements from drag arguments.  
  /// Works for drags from UML diagrams.  
  /// </summary>  
  private IEnumerable<IElement> GetModelElementsFromDragEvent  
                  (DiagramDragEventArgs dragEvent)  
  {  
     //ElementGroupPrototype is the container for  
     //dragged and copied elements and toolbox items.  
     ElementGroupPrototype prototype =  
        dragEvent.Data.  
        GetData(typeof(ElementGroupPrototype))  
                     as ElementGroupPrototype;  
     // Locate the originals in the implementation store.  
     IElementDirectory implementationDirectory =   
        dragEvent.DiagramClientView.Diagram.Store.ElementDirectory;  
  
     return  prototype.ProtoElements.Select(  
       prototypeElement =>   
       {  
          ModelElement element = implementationDirectory  
                .FindElement(prototypeElement.ElementId);  
          ShapeElement shapeElement = element as ShapeElement;  
          if (shapeElement != null)  
          {   
            // Dragged from a diagram.  
            return shapeElement.ModelElement as IElement;  
          }  
          else  
          {   
            // Dragged from UML Model Explorer.  
            return element as IElement;  
          }  
        });  
    }  
```  
  
 Aby uzyskać więcej informacji na temat `ElementGroupPrototype` i `Store` , w której realizowane są narzędzia modelowania UML, zobacz [zestawu Modeling SDK for Visual Studio — języki specyficzne dla domeny](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Programowanie za pomocą interfejsu API UML](../modeling/programming-with-the-uml-api.md)   
 [Definiowanie polecenia menu na diagramie modelowania](../modeling/define-a-menu-command-on-a-modeling-diagram.md)



