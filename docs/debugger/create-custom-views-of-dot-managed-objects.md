---
title: Tworzenie niestandardowych widoków obiektów zarządzanych | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.data.elements
dev_langs:
- CSharp
- VB
- FSharp
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 970051c5f53c152ea6fee334c3c1f856172b5ed9
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44280548"
---
# <a name="create-custom-views-of-managed-objects"></a>Tworzenie niestandardowych widoków obiektów zarządzanych
Można dostosować sposób, w programie Visual Studio Wyświetla typy danych w oknach zmiennych debugera.  
  
## <a name="attributes"></a>Atrybuty  
 W języku C# i Visual Basic, można dodać rozszerzeń dla niestandardowych danych za pomocą <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, i <xref:System.Diagnostics.DebuggerBrowsableAttribute>.  
  
 W [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] kodu języka Visual Basic nie obsługuje atrybutu DebuggerBrowsable. To ograniczenie zostało usunięte w nowszych wersjach programu .NET Framework.  
  
## <a name="visualizers"></a>Wizualizatory  
 Można napisać visualizer, aby wyświetlić dowolny typ danych zarządzanych. Aby uzyskać więcej informacji, zobacz [porady: pisanie wizualizatora](../debugger/how-to-write-a-visualizer.md).  
  
## <a name="native-code"></a>Kod natywny  
 Dla kodu natywnego można dodać rozszerzenia typu danych niestandardowych do autoexp.dat — plik, który znajduje się w katalogu 11.0\Common7\Packages\Debugger Program Files\Microsoft Visual Studio. Instrukcje dotyczące sposobu pisania `autoexp` zasady znajdują się w samym pliku.  
  
> [!CAUTION]
>  Struktura tego pliku i składnię autoexp reguł mogą ulec zmianie z jednej wersji programu Visual Studio do następnego.  
  
 Typ natywny widoków można dostosować w taki sposób, przez napisanie expression evaluator dodatku. Aby uzyskać więcej informacji, zobacz [EEAddIn próbki: debugowanie Expression Evaluator dodatku](https://msdn.microsoft.com/library/d4f6b068-c812-45bc-9ec0-7e0363c4bb9e).  
  
## <a name="see-also"></a>Zobacz też  
 [Korzystanie z atrybutu DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md)   
 [Korzystanie z atrybutu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)   
 [Wyrażenie kontrolne i QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Udoskonalanie debugowania za pomocą atrybutów wyświetlania debugera](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)