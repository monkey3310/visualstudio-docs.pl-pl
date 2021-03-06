---
title: Rozwiązywanie problemów z szablonu projektu programu Visual Studio i szablon elementu ładowania
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: troubleshooting
helpviewer_keywords:
- templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 4bb6a10e92bf8f26ffbcb81796b3c5c8371600b5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31943322"
---
# <a name="how-to-troubleshoot-templates"></a>Porady: Rozwiązywanie problemów z szablonami

Jeśli szablon nie może załadować w środowisku programistycznym, istnieje kilka sposobów, aby zlokalizować ten problem.

## <a name="validate-the-vstemplate-file"></a>Sprawdź poprawność pliku vstemplate

Jeśli *vstemplate* pliku w szablonie nie stosować się do schematu szablonu Visual Studio, szablon nie może występować w **nowy projekt** okno dialogowe.

### <a name="to-validate-the-vstemplate-file"></a>Aby sprawdzić poprawność pliku vstemplate

1. Zlokalizuj *zip* plik, który zawiera szablon.

1. Wyodrębnij *.zip* pliku.

1. Na **pliku** menu w programie Visual Studio, wybierz **Otwórz** > **pliku**.

1. Wybierz *vstemplate* pliku szablonu, a następnie wybierz pozycję **Otwórz**.

1. Upewnij się, że plik XML *vstemplate* pliku zgodnego ze schematu szablonu. Aby uzyskać więcej informacji na temat *vstemplate* schematu, zobacz [odwołanie do schematu szablonu](../extensibility/visual-studio-template-schema-reference.md).

    > [!NOTE]
    > Aby uzyskać pomoc techniczną IntelliSense podczas tworzenia *vstemplate* plików, dodawanie `xmlns` atrybutu `VSTemplate` element i przypisz jej wartość http://schemas.microsoft.com/developer/vstemplate/2005.

1. Zapisz i Zamknij *vstemplate* pliku.

1. Wybierz pliki zawarte w szablonie, kliknij prawym przyciskiem myszy i wybierz polecenie **przesyłają** > **skompresowanego folderu (zip)**. Wybrane pliki są skompresowane w *.zip* pliku.

1. Umieść nowe *.zip* pliku w tym samym katalogu co stary *.zip* pliku.

1. Usuń pliki szablonów wyodrębnionego i starego szablonu *.zip* pliku.

## <a name="enable-diagnostic-logging"></a>Włączanie rejestrowania diagnostyki

Można włączyć rejestrowania diagnostycznego w celu odnajdywania szablonu, wykonując kroki opisane w [Rozwiązywanie problemów dotyczących odnajdywania szablonu (rozszerzalność)](../extensibility/troubleshooting-template-discovery.md).

## <a name="see-also"></a>Zobacz także

- [Rozwiązywanie problemów z odnajdywania szablonu (rozszerzalność)](../extensibility/troubleshooting-template-discovery.md)
- [Dostosowywanie szablonów](../ide/customizing-project-and-item-templates.md)
- [Tworzenie szablonów projektów i elementów](../ide/creating-project-and-item-templates.md)
- [Odwołanie do schematu szablonu](../extensibility/visual-studio-template-schema-reference.md)