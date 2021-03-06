---
title: Odpowiadanie na zmiany i propagowanie zmian
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, events
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: d87a93016f2004a45a572374d68a20d2e59073da
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31954008"
---
# <a name="responding-to-and-propagating-changes"></a>Odpowiadanie na zmiany i propagowanie zmian
Gdy element jest tworzony, usunięte lub zaktualizowane, można napisać kod Propaguj zmiany do innych części modelu lub do zasobów zewnętrznych, takich jak pliki, bazy danych lub innych składników.

## <a name="in-this-section"></a>W tej sekcji
 Przyjąć należy wziąć pod uwagę następujące techniki w następującej kolejności:

|Metoda|Scenariusze|Więcej informacji|
|---------------|---------------|--------------------------|
|Definiuje właściwości domeny obliczona.|Właściwość domeny, którego wartość jest obliczana na podstawie innych właściwości w modelu. Na przykład cen, który jest sumą ceny powiązanych elementów.|[Obliczone i niestandardowe właściwości przechowywania](../modeling/calculated-and-custom-storage-properties.md)|
|Zdefiniuj właściwość domeny niestandardowej magazynu.|Właściwość domeny przechowywane w innych częściach modelu lub zewnętrznie. Na przykład można przeanalizować wyrażenia ciągu w drzewie w modelu.|[Obliczone i niestandardowe właściwości przechowywania](../modeling/calculated-and-custom-storage-properties.md)|
|Programy obsługi, takie jak OnValueChanging i OnDeleting zmienić zastąpienia|Synchronizowanie różnych elementów i synchronizowania zewnętrznych wartości z modelu.<br /><br /> Ograniczenie wartości do określonych zakresów.<br /><br /> Wywoływana tuż przed i po wartości właściwości i innych zmian. Zmiana można rozwiązać przez Zgłaszanie wyjątku.|[Obsługa zmian wartości właściwości domeny](../modeling/domain-property-value-change-handlers.md)|
|Reguły|Można zdefiniować reguły, które są umieszczane w kolejce do wykonania bezpośrednio przed zakończeniem transakcji, w którym wystąpiło zdarzenie zmiany. Nie są one wykonywane na cofania lub ponownego wykonywania. Ich używać, aby zachować synchronizację z innego jedną część magazynu.|[Reguły propagujące zmiany w modelu](../modeling/rules-propagate-changes-within-the-model.md)|
|Zdarzenia magazynu|Magazyn modelowania udostępnia powiadomienia zdarzenia, takie jak dodanie lub usunięcie elementu lub łącze lub zmiana wartości właściwości. Zdarzenie jest również wykonywane na Cofnij i ponów. Użyj magazynu, aby zaktualizować wartości, które nie znajdują się w magazynie.|[Programy obsługi zdarzeń propagujące zmiany poza modelem](../modeling/event-handlers-propagate-changes-outside-the-model.md)|
|Zdarzenia platformy .NET|Kształty mają procedury obsługi zdarzeń, które odpowiadają na kliknięcie myszą i innych gestów. Należy zarejestrować dla tych zdarzeń dla każdego obiektu. Rejestracja jest zazwyczaj wykonywane w zastąpieniu InitializeInstanceResources i należy ją odtworzyć dla każdego elementu.<br /><br /> Zdarzenia te występują zazwyczaj poza transakcją.|[Instrukcje: Przechwytywanie kliknięć w kształcie lub elemencie Decorator](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md)|
|Granice reguły|Zasada granic jest używany w szczególności, aby ograniczyć zakresem kształtu.|[BoundsRules — ograniczenie lokalizacji i rozmiaru kształtu](../modeling/boundsrules-constrain-shape-location-and-size.md)|
|Reguły wyboru|W szczególności reguł wyboru ograniczyć, co użytkownik może wybrać.|[Instrukcje: Ograniczanie bieżącego wyboru i uzyskiwanie dostępu do niego](../modeling/how-to-access-and-constrain-the-current-selection.md)|
|OnAssocatedPropertyChanged|Wskazuje stanów elementów modelu przy użyciu funkcji kształtów lub łączników, takich jak cień, strzałek, kolor i szerokości linii i styl.|[Aktualizowanie kształtów i łączników, aby odzwierciedlały model](../modeling/updating-shapes-and-connectors-to-reflect-the-model.md)|

## <a name="comparing-rules-and-store-events"></a>**Porównanie reguł i magazynu**
 Zmiany powiadamiających, reguł i zdarzenia są uruchamiane w przypadku wystąpienia zmian w modelu.

 Reguły są zwykle stosowane w transakcji końcowego zostało zmienione, a zdarzenia są stosowane po zmian w transakcji.

 Użyj magazynu można zsynchronizować modelu z obiektami poza magazynu i reguł, aby zachować spójność w magazynie.

-   **Tworzenie niestandardowych reguł** utworzyć regułę niestandardową jako klasy pochodnej z reguły abstrakcyjny. Należy również powiadomić framework o reguły niestandardowej. Aby uzyskać więcej informacji, zobacz [reguły propagowanie zmian w modelu](../modeling/rules-propagate-changes-within-the-model.md).

-   **Subskrybowanie zdarzeń** zanim będzie możliwe subskrybowanie zdarzeń, tworzenie obsługi zdarzeń i delegata. Następnie użyj <xref:Microsoft.VisualStudio.Modeling.Store.EventManagerDirectory%2A>właściwości, aby subskrybować zdarzenia. Aby uzyskać więcej informacji, zobacz [obsługi Propaguj zmiany poza Model zdarzeń](../modeling/event-handlers-propagate-changes-outside-the-model.md).

-   **Cofanie zmian** wycofać transakcji, zdarzenia są generowane, ale nie są stosowane zasady. Reguła zmienia wartość Cofnij tę zmianę, wartość jest resetowany do oryginalnej wartości w trakcie akcji cofania. Gdy zdarzenie jest zgłaszane, należy ręcznie zmienić wartość do oryginalnej wartości. Aby dowiedzieć się więcej na temat transactons i cofania, zobacz [porady: użycie transakcji do aktualizacji modelu](../modeling/how-to-use-transactions-to-update-the-model.md).

-   **Przekazywanie argumentów zdarzenia do zasad i zdarzenia** obu zdarzeń i reguły są przekazywane `EventArgs` parametr, który zawiera informacje o tym, jak model został zmieniony.

## <a name="see-also"></a>Zobacz też

- [Instrukcje: Przechwytywanie kliknięć w kształcie lub elemencie Decorator](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md)
- [Pisanie kodu pod kątem dostosowywania języka specyficznego dla domeny](../modeling/writing-code-to-customise-a-domain-specific-language.md)