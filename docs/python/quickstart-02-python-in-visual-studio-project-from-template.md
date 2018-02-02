---
title: "Szybki Start — Tworzenie projektu języka Python w programie Visual Studio przy użyciu szablonu | Dokumentacja firmy Microsoft"
description: "Rozpoczynanie pracy, szybko tworząc projektu programu Visual Studio przy użyciu jednej z wbudowanych szablonów przy użyciu języka Python."
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: quickstart
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 9651c306506967830cf7593bfae87bc2ebd30e99
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2018
---
# <a name="quickstart-create-a-python-project-from-a-template-in-visual-studio"></a>Szybki Start: Tworzenie projektu języka Python z szablonu w programie Visual Studio

Po wprowadzeniu [zainstalowane obsługę języka Python w Visual Studio 2017](installing-python-support-in-visual-studio.md), ułatwia tworzenie nowego projektu Python przy użyciu różnych szablonów.

1. Uruchom program Visual Studio.

1. Wybierz **Plik > Nowy > Projekt** (Ctrl + Shift + N). W **nowy projekt** okno dialogowe, wyszukaj "Python", a następnie wybierz odpowiedni szablon. Należy pamiętać, że wybranie szablonu wyświetla krótki opis zawiera jakie szablonu. (Zobacz też [projektów języka Python](managing-python-projects-in-visual-studio.md#project-templates).)

    ![Okno dialogowe Nowy projekt VS2017 z szablonu Python](media/projects-new-project-dialog2.png)

1. Dla tego przewodnika Szybki Start, wybierz szablon "Python aplikacji", nadaj projektu nazwę (na przykład "MakePI") i lokalizację i wybierz **OK**.

1. Program Visual Studio tworzy plik projektu ( `.pyproj` pliku na dysku) oraz inne pliki zgodnie z opisem w szablonie. Przy użyciu szablonu "Python aplikacji" Projekt zawiera tylko jeden pusty plik o nazwie takiej jak projektu. Plik jest otwarty w edytorze programu Visual Studio domyślnie.

    ![Projekt wynikowy przy użyciu szablonu aplikacji Python](media/projects-new-structure.png)

1. Dodaj kodu do otwartego pliku, takie jak kod poniżej oblicza i wyświetla cyfr 1000 pi:

    ```python
    """ Print digits of PI; code adapted from the second, shorter solution
    at http://www.codecodex.com/wiki/Calculate_digits_of_pi#Python
    """

    from time import perf_counter

    def pi_digits_Python(digits):
        scale = 10000
        maxarr = int((digits / 4) * 14)
        arrinit = 2000
        carry = 0
        arr = [arrinit] * (maxarr + 1)
        output = ""

        for i in range(maxarr, 1, -14):
            total = 0
            for j in range(i, 0, -1):
                total = (total * j) + (scale * arr[j])
                arr[j] = total % ((j * 2) - 1)
                total = total / ((j * 2) - 1)

            output += "%04d" % (carry + (total / scale))
            carry = total % scale

        return output;

    def test_py():
        digits = 1000;

        start = perf_counter()
        output = pi_digits_Python(digits);
        elapsed = perf_counter() - start;

        print("PI to " + str(digits) + " digits in " + str(int(elapsed * 10000)/10000) + " seconds:")

        ## replace inserts the decimal point
        print(output.replace("3", "3.", 1))

    if __name__ == "__main__":
        test_py();
    ```

1. Uruchom program, naciskając klawisze Ctrl + F5 lub wybranie **Debuguj > Uruchom bez debugowania** w menu. Wyniki są wyświetlane w oknie konsoli.

## <a name="next-steps"></a>Następne kroki

> [!div class="nextstepaction"]
> [Samouczek: Praca z języka Python w programie Visual Studio](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Zobacz także

- [Tworzenie środowiska dla istniejących interpreter języka Python](managing-python-environments-in-visual-studio.md#creating-an-environment-for-an-existing-interpreter).
- [Zainstaluj obsługę języka Python w programie Visual Studio 2015 i starszych wersji](installing-python-support-in-visual-studio.md).
- [Lokalizacje instalacji](installing-python-support-in-visual-studio.md#install-locations).