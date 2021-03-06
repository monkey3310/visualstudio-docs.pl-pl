---
title: Dokumentacja interfejsu API dla rozszerzalności modelowania UML | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML - extending
- UML API
- UML model, API
ms.assetid: 2b2ffe93-c358-4d28-a5e5-3d0474629b58
caps.latest.revision: 11
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: db042d59ce5f7363d9ed45e2baebbea45d3a0de4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42679242"
---
# <a name="api-reference-for-uml-modeling-extensibility"></a>Wykaz interfejsów API dla rozszerzalności modelowania UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [wykaz interfejsów API dla rozszerzalności modelowania UML](https://docs.microsoft.com/visualstudio/modeling/api-reference-for-uml-modeling-extensibility).  
  
Można napisać kod programu do odczytu i modyfikowania modeli utworzonych w programie Visual Studio. Dokumentacja interfejsu API zawiera informacje dotyczące określonej klasy do udzielenia odpowiedzi na to. Aby uzyskać więcej informacji zadań, zobacz Tematy w dziale [modeli i diagramów UML rozszerzyć](../modeling/extend-uml-models-and-diagrams.md). Aby dowiedzieć się, które wersje programu Visual Studio obsługują modeli UML, zobacz [obsługiwana wersja dla narzędzia architektury i modelowania](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="assemblies"></a>Zestawy  
  
|Zestaw|Co to pozwala zrobić|  
|--------------|--------------------------------|  
|Microsoft.VisualStudio.Uml.Interfaces.dll|— Przeczytaj i zmienić elementy modelu, takie jak IUseCase, IAssociation i tak dalej.<br />-Nawigowanie po relacjach między elementami.<br /><br /> Obszary nazw i typy odnoszą się do tych, które są zdefiniowane w specyfikacji UML.|  
|Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll|— Tworzenie nowych wystąpień elementów modelu<br />-Dostęp i Modyfikuj kształty i diagramy.|  
  
## <a name="see-also"></a>Zobacz też  
 [Rozszerzanie modeli i diagramów UML](../modeling/extend-uml-models-and-diagrams.md)   
 [Odwołania API do modelowania SDK dla Visual Studio](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)



