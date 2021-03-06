---
title: 'Krok 4: Dodawanie obsługi zdarzeń kliknięcia do każdej etykiety'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 16bdbc7c-4129-411d-bace-f4a3e5375975
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f95a58c1e816c448a641a81282aaecf9d51a63ea
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748117"
---
# <a name="step-4-add-a-click-event-handler-to-each-label"></a>Krok 4: Dodawanie obsługi zdarzeń kliknięcia do każdej etykiety
Gra w dopasowywanie działa w następujący sposób:

1.  Gdy gracz wybiera jeden z kwadratów z ukrytą ikoną, program pokazuje graczowi ikonę, zmieniając jej kolor na czarny.

2.  Następnie gracz wybiera inną ukrytą ikonę.

3.  Jeśli ikony pasują, pozostają widoczne. Jeśli tak nie jest, obie ikony są ukrywane ponownie.

 Aby pobrać program do pracy w ten sposób, należy dodać <xref:System.Windows.Forms.Control.Click> obsługi zdarzeń, który zmienia kolor etykiety, dla której zostanie wybrany.

## <a name="to-add-a-click-event-handler-to-each-label"></a>Aby dodać obsługi zdarzeń kliknięcia do każdej etykiety

1.  Otwórz formularz w **Projektant formularzy systemu Windows**. W **Eksploratora rozwiązań**, wybierz *pliku Form1.cs* lub *Form1.vb*. Na pasku menu wybierz **widoku** > **projektanta**.

2.  Wybierz pierwszy formant etykiety, aby go zaznaczyć. Następnie, przytrzymaj **Ctrl** klucza podczas wybierz wszystkie inne etykiety, aby je zaznaczyć. Pamiętaj, że każda etykieta jest zaznaczona.

3.  Wybierz **zdarzenia** przycisk na pasku narzędzi w **właściwości** okna, aby wyświetlić **zdarzenia** strony **właściwości** okna. Przewiń w dół do **kliknij** zdarzeń, a następnie wprowadź **label_Click** w polu, jak pokazano na poniższej ilustracji.

     ![Okno właściwości przedstawiający kliknij zdarzenie](../ide/media/express_labelclick.png)
**właściwości** okno **kliknij** zdarzeń

4.  Wybierz **Enter** klucza. Dodaje IDE `Click` wywołuje program obsługi zdarzeń `label_Click()` w kodzie i przechwytuje go do każdej etykiety w formularzu.

5.  Wypełnij resztę kodu w następujący sposób:

     [!code-csharp[VbExpressTutorial4Step2_3_4#4](../ide/codesnippet/CSharp/step-4-add-a-click-event-handler-to-each-label_1.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#4](../ide/codesnippet/VisualBasic/step-4-add-a-click-event-handler-to-each-label_1.vb)]

    > [!NOTE]
    >  Jeśli kopiowanie i wklejanie `label_Click()` blok kodu, a nie ręczne wprowadzenie kodu, upewnij się zastąpić istniejącą `label_Click()` kodu. W przeciwnym razie otrzymasz zduplikowany blok kodu.

    > [!NOTE]
    >  Może rozpoznać `object sender` w górnej części programu obsługi zdarzeń jako taka sama jak używane w [samouczek 2: tworzenie kwizu matematycznego](../ide/tutorial-2-create-a-timed-math-quiz.md) samouczka. Ponieważ użytkownik argumentów podłączono kontrolą inną etykietę zdarzenia do metody obsługi pojedyncze zdarzenie kliknięcia, ta sama metoda jest wywoływana, niezależnie od tego, które etykiety użytkownik wybierze. Metoda obsługi zdarzeń musi wiedzieć, które etykieta została wybrana, więc używa nazwy `sender` do identyfikacji formantu etykiety. W pierwszym wierszu metody informuje program, że nie jest obiekt generyczny, ale w szczególności formantu etykiety i korzysta z nazwą `clickedLabel` dostępu do właściwości i metod etykiety.

     Ta metoda najpierw sprawdza, czy `clickedLabel` został pomyślnie przekonwertowany (rzutowania) z obiektu do formantu etykiety. Jeśli nie powiodło się, ma wartość `null` (C#) lub `Nothing` (Visual Basic), a użytkownik nie chce wykonać do końca kod w metodzie. Następnie metoda sprawdza kolor tekstu etykiety wybrany za pomocą etykiety **ForeColor** właściwości. Jeśli kolor tekstu etykiety jest czarny, oznacza to, że ikona jest już wybrana, a metoda jest wykonana. (Co to jest `return` instrukcja nie wykonuje: informuje program można zatrzymać wykonywania metody.) W przeciwnym razie ikona nie została wybrana, więc program zmienia kolor tekstu etykiety na czarny.

6.  Na pasku menu wybierz **pliku** > **Zapisz wszystko** Aby zapisać postęp, a następnie na pasku menu wybierz **debugowania** > **Start Debugowanie** do uruchomienia programu. Powinien zostać wyświetlony pusty formularz z niebieskim tłem. Wybierz którąś komórkę w formularzu, jedna z ikon powinna się stać widoczna. Kontynuuj wybieranie różnych miejsc w formularzu. Ikony powinny się pojawiać w miarę wybierania.

## <a name="to-continue-or-review"></a>Aby kontynuować lub przeglądnąć

-   Aby przejść do następnego kroku samouczka, zobacz [krok 5: Dodawanie odwołań do etykiet](../ide/step-5-add-label-references.md).

-   Aby powrócić do poprzedniego kroku samouczka, zobacz [krok 3: przypisanie losowej ikony do każdej etykiety](../ide/step-3-assign-a-random-icon-to-each-label.md).
