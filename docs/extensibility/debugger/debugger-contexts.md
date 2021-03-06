---
title: Konteksty debugera | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 49af504b27afc6171a914d9559a5ff83f3d595eb
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204105"
---
# <a name="debugger-contexts"></a>Konteksty debugera
W [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] debugowania, aparat debugowania (DE) działa jednocześnie w ramach kilku różnych kontekstach, w następujący sposób:  
  
-   Kontekst kodu w tym artykule opisano bieżącej lokalizacji w usłudze stream wykonywania programu.  
  
-   Dokumentacja kontekstu lub pozycji, który opisuje bieżącą pozycję w dokumencie źródłowym.  
  
-   Kontekst oceny wyrażeń, który opisuje kontekst, w wyrażeniu, które odbędzie się oceny.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Kontekst kodu](../../extensibility/debugger/code-context.md)  
 W tym artykule omówiono kontekst kodu jako adresu program strumień instrukcji w współczesnych środowiska wykonawczego architektury i nietradycyjnych języków, gdzie kod nie może być reprezentowany przez instrukcje, ale w inny sposób.  
  
 [Położenie dokumentu](../../extensibility/debugger/document-position.md)  
 Definiuje położenie dokumentu w programie Visual Studio debugowania za pomocą abstrakcję pozycji w pliku źródłowym, ponieważ wiadomo, że środowisko IDE.  
  
 [Kontekst dokumentu](../../extensibility/debugger/document-context.md)  
 W tym artykule omówiono jakie kontekstu dokumentu reprezentuje podczas debugowania programu Visual Studio w odniesieniu do pliku źródłowego. Omówiono również sposób obsługi symboli mapowania kontekst kodu do kontekstu dokumentacji.  
  
 [Kontekst oceny wyrażeń](../../extensibility/debugger/expression-evaluation-context.md)  
 Zawiera informacje dotyczące oceny wyrażenia kontekstu w programie Visual Studio. Na przykład oceny wyrażenia kontekstu skojarzonego z ramką stosu udostępnia kontekst dla ocenianie zmiennych lokalnych, parametrów metod i składowych klasy.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Pojęcia dotyczące debugowania](../../extensibility/debugger/debugger-concepts.md)  
 W tym artykule opisano główne pojęcia dotyczące architektury debugowania.  
  
 [Składniki debugowania](../../extensibility/debugger/debugger-components.md)  
 Zawiera omówienie składników debugowania programu Visual Studio, które obejmują aparat debugowania (DE), Ewaluator wyrażeń (EE) i obsługi symboli (SH).  
  
 [Debugowanie zadań](../../extensibility/debugger/debugging-tasks.md)  
 Zawiera łącza do różnych zadań debugowania, takie jak uruchamianie programu i wyrażeń.