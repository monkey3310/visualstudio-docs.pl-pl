---
title: Docelowy .NET Framework w wersji programu Visual Studio
ms.date: 02/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- .NET Framework version [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 36599475e743259d8cf09d24172a633b54b09693
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752310"
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>Porady: wersja docelowa platformy .NET Framework

W tym dokumencie opisano, jak wersja docelowa platformy .NET Framework podczas tworzenia projektu oraz jak zmienić wersję docelową w istniejących Visual Basic, C# lub Visual F # projektu.

> [!IMPORTANT]
> Aby dowiedzieć się, jak zmienić docelową wersję dla projektów C++, zobacz [porady: modyfikowanie docelowego framework i zestawu narzędzi platformy](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

## <a name="to-target-a-version-when-you-create-a-project"></a>Aby ukierunkować tworzony projekt na konkretną wersję

Podczas tworzenia projektu dostępne wersje programu .NET Framework są zależne od które wersje są zainstalowane, a następnie wybrany szablon w **nowy projekt** okno dialogowe.

1. Na pasku menu wybierz **pliku** > **nowy** > **projektu**.

1. Na liście zainstalowanych szablonów należy wybrać typ projektu, który chcesz utworzyć, a następnie wprowadź nazwę dla projektu.

1. Z **Framework** listy rozwijanej w dolnej części **nowy projekt** oknie dialogowym Wybierz wersję systemu .NET Framework, które mają projektu docelowego.

    Lista platform pokazuje tylko te wersje, które mają zastosowanie do wybranego szablonu. Niektóre typy projektu, takich jak .NET Core, nie wymagają .NET Framework. W takich przypadkach **Framework** listy rozwijanej jest ukryty.

    ![W ramach listy rozwijanej w oknie dialogowym Nowy projekt](media/vside-newproject-framework.png)

1. Wybierz **OK** przycisku.

## <a name="to-change-the-targeted-version"></a>Aby zmienić wersję docelową

Docelowa wersja programu .NET Framework w projektach Visual Basic, C# lub Visual F # można zmienić, korzystając z następującej procedury.

Aby dowiedzieć się, jak zmienić docelową wersję dla projektów C++, zobacz [porady: modyfikowanie docelowego framework i zestawu narzędzi platformy](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

1. W **Eksploratora rozwiązań**, otwórz menu skrótów projektu, który chcesz zmienić, a następnie wybierz pozycję **właściwości**.

    ![Właściwości Eksploratora rozwiązań programu Visual Studio](../ide/media/vs_slnexplorer_properties.png)

1. W lewej kolumnie **właściwości** okna, wybierz **aplikacji** kartę.

    ![Visual Studio aplikacji właściwości aplikacji kartę](../ide/media/vs_slnexplorer_properties_applicationtab.png)

    > [!NOTE]
    > Po utworzeniu aplikacji platformy uniwersalnej systemu Windows, nie można zmienić docelowej wersji systemu Windows lub programu .NET Framework.

1. W **platformy docelowej** listy, wybierz wersję, która ma.

1. W oknie dialogowym weryfikacji wybierz **tak** przycisku.

    Projekt zostaje wyładowany Gdy się ponownie ładuje, jest ukierunkowany na wybraną wersję .NET Framework.

    > [!NOTE]
    > Jeśli kod zawiera odwołania do innej wersji platformy .NET Framework niż docelowa, podczas kompilacji lub uruchamiania kodu mogą się pojawić komunikaty o błędach. Aby usunąć te błędy, należy zmodyfikować odwołania. Zobacz [Framework .NET Rozwiązywanie problemów z błędami obiektów docelowych](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).

## <a name="see-also"></a>Zobacz także

- [Visual Studio omówienie wielowersyjności kodu](../ide/visual-studio-multi-targeting-overview.md)
- [Rozwiązywanie problemów z błędami obiektów docelowych w programie .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)
- [Strona aplikacji, Projektant projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)
- [Strona aplikacji, Projektant projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)
- [Porady: modyfikowanie docelowego framework i zestawu narzędzi platformy (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)