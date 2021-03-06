---
title: Obsługa usługi języka dla debugowania | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 59c044f6ffc3f2cdf0749f0192f4b8fa458b00cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128661"
---
# <a name="language-service-support-for-debugging"></a>Obsługa usługi języka do debugowania
Usługa języka zapewniają funkcje, które obsługują debugera za pośrednictwem <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo> interfejsu. Te funkcje obejmują sprawdzanie poprawności punktów przerwania i dostarczenie lista wyrażeń w celu **automatycznych** okna.  
  
 Jednak należy mieć ewaluatora wyrażeń debugowania języka. Ewaluator wyrażeń jest odpowiedzialny za obliczenia wyrażenia w celu utworzenia wartości podczas debugowania. Aby uzyskać informacje dotyczące wdrożenia ewaluatorów wyrażeń CLR zobacz:  
  
-   [Ewaluatory wyrażeń CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)  
  
-   [Przykładowe ewaluatora wyrażenia zarządzanych](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)  
  
## <a name="compiler-output"></a>Dane wyjściowe kompilatora  
 Typ kompilatora Określa, co należy zrobić, aby zaimplementować debugowania dla danego języka. Jeśli Twoje kompilatora jest przeznaczony dla systemu operacyjnego Windows i zapisuje plik PDB można debugować programy z kodu natywnego, debugowania aparatem, który jest zintegrowany z programu Visual Studio. Jeśli Twoje kompilatora języka pośredniego firmy Microsoft (MSIL), można debugować programy z zarządzanym kodem debugowania aparat, który również jest zintegrowany z programu Visual Studio. Jeśli kompilujący celem własny system operacyjny lub innego środowiska, należy napisać aparat debugowania.  
  
 Aby uzyskać więcej informacji dotyczących wdrażania debugowania dla danego języka, zobacz [wprowadzenie](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) w Visual Studio SDK debugowania.