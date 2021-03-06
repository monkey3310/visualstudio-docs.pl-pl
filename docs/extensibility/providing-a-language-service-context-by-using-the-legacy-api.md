---
title: Dostarczanie kontekstu usługi języka za pomocą starszej wersji interfejsu API | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - language service context
ms.assetid: daa2df22-9181-4bad-b007-a7d40302bce1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d9daef780847da99463811a9c10399102dc7b808
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39637435"
---
# <a name="provide-a-language-service-context-by-using-the-legacy-api"></a>Zapewnianie kontekstu usługi języka przy użyciu starszej wersji interfejsu API
Dostępne są dwie opcje usługi języka zapewnić kontekst użytkownika za pomocą [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] podstawowy edytor: dostarczy w kontekście znacznika tekstu, lub wszystkie kontekstu użytkownika. Różnice między nimi opisano w tym miejscu.  
  
 Aby uzyskać więcej informacji na temat podawania kontekstu usługi języka, który jest podłączony do własnego edytora, zobacz [porady: dostarczanie kontekstu edytory](../extensibility/how-to-provide-context-for-editors.md).  
  
## <a name="provide-text-marker-context-to-the-editor"></a>Podaj w kontekście znacznika tekstu do edytora  
 Aby zapewnić kontekst dla błędów kompilatora wskazywanym przez znaczników tekstu w [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] core editor, implementować <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> interfejsu. W tym scenariuszu Usługa językowa udostępnia kontekst, tylko wtedy, gdy kursor znajduje się na znacznika tekstu. Dzięki temu w edytorze — słowo kluczowe w lokalizacji kursora, aby zapewnić **dynamiczna Pomoc** okno z żadnych atrybutów.  
  
## <a name="provide-all-user-context-to-the-editor"></a>Podaj wszystkie kontekstu użytkownika do edytora  
 Jeśli tworzysz usługi językowej i korzystają z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] podstawowe edytora, a następnie można wdrożyć <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> interfejsu do zapewniania kontekstu usługi języka.  
  
 Do wykonania `IVsLanguageContextProvider`, pakiet z kontekstu (kolekcję) jest dołączony do edytora, który jest odpowiedzialny za aktualizowanie zbiór kontekstu. Gdy **dynamiczna Pomoc** wywołania okna <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.Update%2A> interfejsu na ten zbiór kontekstu w czasie bezczynności, zbiór kontekst zapytania edytor dla aktualizacji. Edytor następnie powiadamia użytkownika usługa językowa, że powinna zostać zaktualizowana w edytorze i przekazuje wskaźnik do zbioru kontekstu. Jest to realizowane przez wywołanie <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider.UpdateLanguageContext%2A> metody za pomocą edytora do usługi języka. Za pomocą wskaźnika do zbioru kontekstu, usługa językowa można teraz dodawać i usuwać atrybutów i słów kluczowych. Aby uzyskać więcej informacji, zobacz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider>.  
  
 Istnieją dwa różne sposoby, aby zaimplementować `IVsLanguageContextProvider`:  
  
-   Zapewniają słowo kluczowe do zbioru kontekstu  
  
     Po wywołaniu edytora można zaktualizować pakiet kontekstu przekazać odpowiednie słowa kluczowe i atrybutów, a następnie wróć `S_OK`. Zwrócona wartość powoduje, że edytor, aby zachować kontekst — słowo kluczowe i atrybutów, a nie zapewniają słowa kluczowego w lokalizacji kursora do zbioru kontekstu.  
  
-   Uzyskaj słowa kluczowego from — słowo kluczowe pod kursorem  
  
     Po wywołaniu edytora można zaktualizować pakiet kontekstu przekazać odpowiednich atrybutów, a następnie wróć `E_FAIL`. Zwrócona wartość powoduje, że edytor, aby zachować atrybutów w zbiorze kontekstu, ale zaktualizować pakiet kontekstu ze słowem kluczowym przy kursorze.  
  
 Poniższy diagram przedstawia, jak podano kontekstu usługi języka, który implementuje `IVsLanguageContextProvider`.  
  
 ![LangServiceImplementation2 — grafika](../extensibility/media/vslanguageservice2.gif "vsLanguageService2")  
Kontekst dla usługi językowej  
  
 Jak widać na diagramie [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] podstawowy edytor tekstu ma zbiór kontekstu podłączone do niego. Ten zbiór kontekstu wskazuje na trzy osobne kontekst podrzędny zbiory: Usługa języka domyślnego edytora i znacznika tekstu. Język usługi i tekstu znacznika kontekst podrzędny zbiory zawierać atrybuty i słowa kluczowe dla usługi w języka, jeśli <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> interfejs jest implementowany, znaczniki tekstu i jeśli <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> interfejs jest implementowany. Jeśli nie należy implementować jeden z tych interfejsów, następnie Edytor udostępnia kontekst for — słowo kluczowe w lokalizacji kursora w zbiorze kontekst podrzędny domyślny edytor.  
  
## <a name="context-guidelines-for-editors-and-designers"></a>Kontekst wytyczne dotyczące projektanci i edytory  
 Projektanci i edytory, musisz podać ogólne — słowo kluczowe dla edytora lub okna projektanta. Odbywa się tak, aby rodzajowy, ale właściwe, będzie on wyświetlany na projektancie lub edytorze, po naciśnięciu klawisza **F1**. Edytor musi oprócz tego podać bieżące słowo kluczowe pod kursorem lub podać klucza termin, na podstawie bieżącego zaznaczenia. W ten sposób zapewnić, że utworzenia tematu Pomocy dotyczącego tekstu lub elementu interfejsu użytkownika wskazywany Wyświetla wybrany, gdy użytkownik naciśnie **F1**. Projektant dostarcza kontekst dla elementu zaznaczonego w projektancie, takich jak przycisku w formularzu. Projektanci i edytory również musi połączyć się z usługą języka zgodnie z opisem w [podstawowe informacje o usłudze starszej wersji języka](../extensibility/internals/legacy-language-service-essentials.md).