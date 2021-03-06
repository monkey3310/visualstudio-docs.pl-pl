---
title: Kompilowanie i tworzenie
description: W tym artykule opisano sposób skompilować i utworzyć projekty i rozwiązania w programie Visual Studio dla komputerów Mac
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: FB253757-DB00-4889-A6BF-E44722E25BD1
ms.openlocfilehash: a66cc250b0d019b3efa4873b89eef252af44b8a6
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283707"
---
# <a name="compiling-and-building-in-visual-studio-for-mac"></a>Kompilowanie i tworzenie w programie Visual Studio dla komputerów Mac

Program Visual Studio for Mac może służyć do tworzenia aplikacji i tworzyć zestawy podczas tworzenia projektu. Jest ważne skompilować i utworzyć kod wcześnie i często, dzięki czemu można zidentyfikować niezgodności typów i inne błędy kompilacji.

## <a name="building-from-the-ide"></a>Kompilacja z IDE

Za pomocą programu Visual Studio dla komputerów Mac umożliwia tworzenie i uruchamianie opiera się natychmiast, zapewniając nadal kontrolować funkcje kompilacji. Program Visual Studio for Mac używa programu MSBuild jako podstawowej systemu kompilacji.

Wszystkie projekty i rozwiązania utworzone w środowisku IDE ma domyślnej konfiguracji kompilacji, definiującą kontekst dla kompilacji. Te konfiguracje mogą być edytowane, lub możesz utworzyć swój własny. Tworzenie lub modyfikowanie tych konfiguracji automatycznie aktualizuje plik projektu, który jest następnie używany przez program MSBuild do kompilowania projektu.

Aby uzyskać więcej informacji na temat sposobu tworzenia projektów i rozwiązań w środowisku IDE, zobacz [kompilowanie oraz Oczyszczanie projektów i rozwiązań](building-and-cleaning-projects-and-solutions.md) przewodnik.

Program Visual Studio for Mac można również wykonać następujące czynności:

* Zmienianie ścieżki wyjściowej. To jest edytowany w opcjach projektu:

    ![Zmień ścieżkę wyjściową](media/compiling-and-building-image4.png)

* Zmień poziom szczegółowości danych wyjściowych kompilacji:

    ![Zmień poziom szczegółowości](media/compiling-and-building-image5.png)

* Dodaj niestandardowe polecenia przed, w trakcie lub po Tworzenie lub czyszczenie:

    ![Dodawanie poleceń niestandardowych](media/compiling-and-building-image6.png)

## <a name="building-from-command-line"></a>Tworzenie z wiersza polecenia

Można użyć aparatu kompilacji MSBuild do kompilowania aplikacji z poziomu wiersza polecenia.

Zobacz [MSBuild](/visualstudio/msbuild/msbuild) zawartości, aby uzyskać więcej informacji na temat korzystania z programu MSBuild.

## <a name="building-from-azure-pipelines"></a>Tworzenie z potoków platformy Azure

* [Tworzenie aplikacji platformy Xamarin](/vsts/pipelines/apps/mobile/xamarin?view=vsts&tabs=vsts)
* [Ciągła integracja za pomocą platformy Xamarin](https://developer.xamarin.com/guides/cross-platform/ci/)