---
title: Tworzenie niestandardowych widoków obiektów zarządzanych | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.data.elements
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- data types [C#], custom
- custom data types
- managed code, custom data types
- autoexp.dat file
- mcee_cs.dat file
- debugger, expanding data types
- mcee_mc.dat file
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
caps.latest.revision: 37
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a84802e3b4e3c32f917dba56fce95268e39cd4bb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628571"
---
# <a name="create-custom-views-of-managed-objects"></a>Tworzenie niestandardowych widoków obiektów zarządzanych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Tworzenie niestandardowych widoków obiektów zarządzanych](https://docs.microsoft.com/visualstudio/debugger/create-custom-views-of-dot-managed-objects).  
  
Można dostosować sposób, w programie Visual Studio Wyświetla typy danych w oknach zmiennych debugera.  
  
## <a name="attributes"></a>Atrybuty  
 W języku C# i Visual Basic, można dodać rozszerzeń dla niestandardowych danych za pomocą <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, i <xref:System.Diagnostics.DebuggerBrowsableAttribute>.  
  
 W [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)] kodu języka Visual Basic nie obsługuje atrybutu DebuggerBrowsable. To ograniczenie zostało usunięte w nowszych wersjach programu .NET Framework.  
  
## <a name="visualizers"></a>Wizualizatory  
 Można napisać visualizer, aby wyświetlić dowolny typ danych zarządzanych. Aby uzyskać więcej informacji, zobacz [porady: pisanie wizualizatora](../debugger/how-to-write-a-visualizer.md).  
  
## <a name="native-code"></a>Kod natywny  
 Dla kodu natywnego można dodać rozszerzenia typu danych niestandardowych do autoexp.dat — plik, który znajduje się w katalogu 11.0\Common7\Packages\Debugger Program Files\Microsoft Visual Studio. Instrukcje dotyczące sposobu pisania `autoexp` zasady znajdują się w samym pliku.  
  
> [!CAUTION]
>  Struktura tego pliku i składnię autoexp reguł mogą ulec zmianie z jednej wersji programu Visual Studio do następnego.  
  
 Typ natywny widoków można dostosować w taki sposób, przez napisanie expression evaluator dodatku. Aby uzyskać więcej informacji, zobacz [EEAddIn próbki: debugowanie Expression Evaluator dodatku](http://msdn.microsoft.com/en-us/d4f6b068-c812-45bc-9ec0-7e0363c4bb9e).  
  
## <a name="see-also"></a>Zobacz też  
 [Korzystanie z atrybutu DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md)   
 [Korzystanie z atrybutu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)   
 [Wyrażenie kontrolne i QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Udoskonalanie debugowania za pomocą atrybutów wyświetlania debugera](http://msdn.microsoft.com/library/72bb7aa9-459b-42c4-9163-9312fab4c410)



