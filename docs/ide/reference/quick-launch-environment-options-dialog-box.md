---
title: Szybkie uruchamianie, środowisko, opcje — okno dialogowe
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.QuickLaunch
- vs.quicklaunch
helpviewer_keywords:
- searching IDE
- IDE, searching
ms.assetid: 4200f297-d065-4723-9a30-d91ff2e26c9d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad37856e8692d5182ddba4f80ec1c07aa095f674
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31946783"
---
# <a name="quick-launch-environment-options-dialog-box"></a>Szybkie uruchamianie, środowisko, opcje — okno dialogowe
Można użyć **Szybkie uruchamianie** szybkie wyszukiwanie i wykonać akcje dla IDE zasobów, takich jak opcje, szablony, menu. Nie można użyć **Szybkie uruchamianie** wyszukiwania kodu i symbole. **Szybkie uruchamianie** pole wyszukiwania znajduje się w prawym górnym rogu paska menu i jest dostępny, wybierając klawisze Ctrl + Q. Po prostu wprowadź ciąg wyszukiwania w polu. Do wyszukiwania ciągów zawierających @, użyj ”@@”. 

 **Szybkie uruchamianie** jest włączona domyślnie po zainstalowaniu programu Visual Studio. Na pasku menu można wyświetlić lub ukryć **Szybkie uruchamianie** , wybierając **narzędzia**, **opcje**. Rozwiń węzeł **środowisk** węzeł, a następnie wybierz pozycję **Szybkie uruchamianie**. Wybierz lub wyczyść **Włącz szybkie uruchamianie** pole wyboru. Można również włączyć lub wyłączyć kategorie wyszukiwania na tej stronie.

## <a name="category-list"></a>Lista kategorii
 Wyniki wyszukiwania w usłudze szybkiego uruchamiania są wyświetlane w czterech kategorii: **ostatnio używanych**, **menu**, **opcje**, i **otwarte dokumenty**, wraz z programem Liczba elementów w kategorii. Przechodzenie przez wyniki wyszukiwania według kategorii, wybierz klawisze Ctrl + Q, aby wyświetlić wszystkie wyniki z kategorii dalej. Po wykonaniu ostatniego kategorii pojawi się klawisze Ctrl + Q zawiera kilka wyników z każdej kategorii. Ctrl + Shift + Q umożliwia przeglądanie kategorii w odwrotnej kolejności. Aby wyświetlić wszystkie wyniki wyszukiwania w kategorii, wybierz nazwę kategorii.

 Następujące skróty umożliwia ograniczyć wyszukiwanie do poszczególnych kategorii.

|Kategoria|Skrót|Opis elementu skrótów|
|--------------|--------------|--------------------------|
|Ostatnio używane|@mru<br /><br /> Na przykład:`@mru font`|Wyświetla maksymalnie pięć elementów, które **ostatnio używanych**.|
|Menu|@menu<br /><br /> Na przykład:`@menu font`|Ogranicza wyszukiwanie do elementów menu.|
|Opcje|@opt<br /><br /> Na przykład:`@opt font`|Ogranicza wyszukiwanie do ustawienia w **opcje** okno dialogowe.|
|Dokumenty|@doc<br /><br /> Na przykład:`@doc font`|Ogranicza wyszukiwanie do nazwy pliku i ścieżki otwartych dokumentów spełniających kryteria wyszukiwania, ale nie wyszukiwanego tekstu wewnątrz same pliki.|

> [!NOTE]
> Klawisze skrótu można zmienić na **ogólne**, **klawiatury** strony **opcje** okno dialogowe.


## <a name="show-previous-results"></a>Pokaż wyniki poprzedniego
 Domyślnie terminu wyszukiwania, które można wprowadzić nie jest zachowywane między sesjami wyszukiwania. Ciąg wyszukiwania jest wyczyszczone, jeśli wyszukać termin, przesuń kursor poza **Szybkie uruchamianie** obszaru, a następnie przejdź kopii. Aby zachować wyniki wyszukiwania, przejdź do **opcje** okno dialogowe Wybierz **Szybkie uruchamianie**, a następnie wybierz **wyszukiwania Pokaż wyniki poprzedniego wyszukiwania, gdy pasek Szybkie uruchamianie jest aktywny.** pole wyboru. Przy następnym wyszukiwania, pozostaw obszaru Szybkie uruchamianie i wrócić, Szybkie uruchamianie spowoduje zachowanie terminu wyszukiwania ostatniego użycia i również wyświetlić wyniki wyszukiwania.

 Aby uzyskać najnowsze porady i wskazówki dotyczące korzystania z **Szybkie uruchamianie**, zobacz [blogu programu Visual Studio](http://go.microsoft.com/fwlink/?LinkId=236054).

## <a name="see-also"></a>Zobacz też

- [Ogólne elementy interfejsu użytkownika (Visual Studio)](../../ide/reference/general-user-interface-elements-visual-studio.md)
- [Środowisko, Opcje — okno dialogowe](../../ide/reference/environment-options-dialog-box.md)