---
title: Dodawanie tagów do mapowaniach zbioru liczników dla testy obciążeniowe w programie Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, counter set mappings, computer tags
ms.assetid: f52a73e1-036a-4b28-a6c8-848284bf4488
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 96ce122c78c20b741613ed45820f585236a0383b
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2018
ms.locfileid: "39203670"
---
# <a name="how-to-add-computer-tags-to-counter-set-mappings-using-the-load-test-editor"></a>Porady: Dodawanie tagów komputerów do mapowań za pomocą edytora testu obciążenia zestawów liczników

Tagi komputera pozwalają zidentyfikować komputer o nazwie łatwy do rozpoznania. Znaczniki są wyświetlane w **mapowaniach zbioru liczników** węzeł w drzewie w edytorze testu obciążenia. Co ważniejsze, znaczniki są wyświetlane w raportach programu Excel, które pomagają identyfikować zainteresowane strony jaką rolę na komputerze nie ma w teście obciążeniowym. Na przykład "Web serwer1 w lab2" lub "SQL Server2 w pakiecie office Phoenix". Aby uzyskać więcej informacji, zobacz [testy obciążenia raportowanie wyników dla potrzeb porównań testów lub analizy trendów](../test/compare-load-test-results.md).

## <a name="to-add-a-tag-to-a-computer"></a>Aby dodać tag do komputera

1.  Otwórz test obciążenia.

2.  Wybierz **Zarządzaj zbiorem liczników** przycisku.

     — lub —

     Kliknij prawym przyciskiem myszy **zbiorów liczników** folderu obciążenia testów drzewa i wybierz przycisk **Zarządzaj zbiorem liczników**.

     **Zarządzaj zbiorem liczników** zostanie wyświetlone okno dialogowe.

3.  (Opcjonalnie) W **wybrane komputery i zbiory liczników zostaną dodane następujące parametry uruchomieniowe** pola listy, wybierz inne ustawienie uruchamiania.

    > [!NOTE]
    > Dotyczy to tylko, jeśli masz więcej niż jedno ustawienie uruchamiania w teście obciążenia.

4.  W obszarze **komputera i zestawy liczników do monitorowania**, wybierz komputer, który chcesz zastosować do znacznika.

    > [!NOTE]
    > Aby uzyskać informacje o tym, jak dodać komputer, zobacz [porady: Zarządzanie zbiorami liczników](../test/how-to-manage-counter-sets-using-the-load-test-editor.md).

5.  W **tagów** pole tekstowe, wpisz znacznik do skojarzenia z komputera. Na przykład "TestMachine12 w lab3".

6.  Wybierz **OK**.

## <a name="see-also"></a>Zobacz także

- [Analizowanie naruszeń zasady progu](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Analizowanie wyników testów obciążenia](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Określanie zbiorów liczników oraz zasad progu dla komputerów w teście obciążeniowym](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Porady: Zarządzanie zbiorami liczników](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)