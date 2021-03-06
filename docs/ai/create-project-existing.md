---
ms.technology: vs-ai-tools
ms.openlocfilehash: b86097cc1e0e531fe6f95a01cfa1cae5e4ac42d7
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
ms.locfileid: "33870619"
---
# <a name="create-an-ai-project-from-existing-code"></a>Tworzenie projektu AI z istniejącego kodu

Po wprowadzeniu [zainstalowany program Visual Studio Tools dla AI](installation.md), łatwo ją przenieść istniejący kod języka Python do projektu programu Visual Studio.

> [!Important]
>
> Proces opisany w tym miejscu nie Przenieś lub skopiuj oryginalnych plików źródłowych. Jeśli chcesz pracować z kopią, najpierw zduplikowane folderu.

1. Uruchom program Visual Studio i wybierz **Plik > Nowy > Projekt**.

1. W **nowy projekt** okno dialogowe, wyszukaj "**narzędzia AI**", wybierz pozycję "**kodu z istniejących Python**" szablonu, nadaj projektu, nazwy i lokalizacji, a następnie wybierz **OK**.

    ![Nowy projekt z istniejących źródeł, krok 1](media\create-project-existing\new-ai-project.png)

1. W oknie kreatora należy ustawić ścieżkę do istniejącego kodu, zdefiniować filtr dla typów plików i określ wszystkie ścieżki wyszukiwania, które Twój projekt wymaga, a następnie wybierz **OK**. Jeśli nie znasz wyszukiwania, jakie są ścieżki wypełniaj tego pola.

![Nowy projekt z istniejących źródeł, krok 2](media\create-project-existing\azurebatch-newproject.png)

> Sprawdź, czy istniejący kod jest częścią projektu usługi Azure Machine Learning, "**uczenia maszynowego Azure jest folder**" w celu zapewnienia pomyślnej konwersji istotne szczegóły konfiguracji usługi Azure Machine Learning, takie jak eksperymenty, które konto, które obszaru roboczego, kontekstów obliczeń do użycia i inne.

1. Aby ustawić pliku startowego, zlokalizuj plik w Eksploratorze rozwiązań, kliknij prawym przyciskiem myszy i wybierz **Ustaw jako plik uruchamiania**.

1. W razie potrzeby, uruchom program naciskając klawisze Ctrl + F5 lub wybranie **Debuguj > Rozpocznij bez debugowanie**.

> [!div class="nextstepaction"]
> [Samouczek: Praca z języka Python w programie Visual Studio](../python/tutorial-working-with-python-in-visual-studio-step-00-installation.md)

## <a name="see-also"></a>Zobacz też

- [Ręcznie Zidentyfikuj istniejącego środowiska Python](../python/managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment)