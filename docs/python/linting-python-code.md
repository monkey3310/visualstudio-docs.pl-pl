---
title: Używanie narzędzia PyLint do przeanalizowania linterem kodu w języku Python
description: Jak używać PyLint w programie Visual Studio, aby sprawdzić problemy w kodzie języka Python.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: fa037a9e674e6086fd3d558d621f9a7d7be616aa
ms.sourcegitcommit: 0cf1e63b6e0e6a0130668278489b21a6e5038084
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2018
ms.locfileid: "39468744"
---
# <a name="use-pylint-to-check-python-code"></a>Umożliwia sprawdzanie kodu w języku Python PyLint

[PyLint](https://www.pylint.org/), powszechnie używane narzędzie, które sprawdza występowanie błędów w kodzie języka Python i zachęca dobre języka Python, wzorców i jest zintegrowana w programie Visual Studio dla projektów języka Python.

## <a name="run-pylint"></a>Spustit PyLint

Po prostu kliknij prawym przyciskiem myszy projekt w języku Python **Eksploratora rozwiązań** i wybierz **Python** > **Uruchom PyLint**:

![Polecenie PyLint w menu kontekstowym dla projektów języka Python](media/code-pylint-command.png)

Za pomocą tego polecenia monit o zainstalowanie PyLint w środowisku active, jeśli nie jest już obecny.

PyLint ostrzeżenia i błędy są wyświetlane w **lista błędów** okna:

![Lista błędów PyLint](media/code-pylint-error-list.png)

Dwukrotne kliknięcie błąd przejście bezpośrednio do kodu źródłowego, która wygenerowała ten problem.

> [!Tip]
> Zobacz [PyLint funkcji odwołanie](https://pylint.readthedocs.io/en/latest/technical_reference/features.html) szczegółową listę wszystkich PyLint Wyprowadź komunikaty.

## <a name="set-pylint-command-line-options"></a>Opcje wiersza poleceń PyLint

[Opcje wiersza polecenia](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) sekcji dokumentacji PyLint zawiera opis sposobu kontrolowania zachowania PyLint firmy za pośrednictwem *.pylintrc* pliku konfiguracji. Takiego pliku można umieścić w folderze głównym projektu języka Python w programie Visual Studio lub w innym miejscu w zależności od tego, jak często chcesz, aby te ustawienia stosowane (zobacz [opcje wiersza polecenia](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) Aby uzyskać szczegółowe informacje).

Na przykład, aby pominąć ostrzeżenia "Brak docstring" pokazano na poprzedniej ilustracji, za pomocą *.pylintrc* plików w projekcie, wykonaj czynności:

1. W wierszu polecenia przejdź do katalogu głównego projektu (który ma swoje *.pyproj* pliku) i uruchom następujące polecenie, aby wygenerować plik konfiguracji skomentowanej:

   ```command
   pylint --generate-rcfile > .pylintrc
   ```

1. W Eksploratorze rozwiązań w usłudze Visual Studio, kliknij prawym przyciskiem myszy projekt, wybierz **Dodaj** > **istniejący element**, przejdź do nowego *.pylintrc* plików, wybierz ją, a Wybierz **Dodaj**.

1. Otwórz plik do edycji, która ma kilka ustawień, których można pracować. Aby wyłączyć ostrzeżenia, zlokalizuj `[MESSAGES CONTROL]` sekcji, a następnie zlokalizuj `disable` ustawienie w tej sekcji. Jest to długi ciąg określonych wiadomości, do których można dołączyć niezależnie od tego ostrzeżenia, które chcesz. W tym przykładzie w tym miejscu należy dołączyć `,missing-docstring` (w tym oddzielania przecinkami).

1. Zapisz *.pylintrc* pliku i spustit PyLint ponownie, aby zobaczyć, że ostrzeżenia teraz są pomijane.

> [!Tip]
> Aby użyć *.pylintrc* pliku z udziału sieciowego, Utwórz zmienną środowiskową o nazwie `PYLINTRC` z wartością nazwy pliku w sieci udostępnianie przy użyciu ścieżki UNC lub litera dysku zmapowanego. Na przykład `PYLINTRC=\\myshare\python\.pylintrc`.
