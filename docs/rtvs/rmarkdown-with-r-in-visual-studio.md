---
title: Znaczniki R Markdown
description: Jak utworzyć R Markdown dokumenty w Visual Studio do tworzenia wysokiej jakości raportów, prezentacji i pulpitów nawigacyjnych.
ms.date: 11/16/2017
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 1bb6779e0e8174dd10f209d9825ffb861d00455d
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238350"
---
# <a name="create-r-markdown-documents"></a>Tworzenie dokumentów R Markdown

[R Markdown](https://rmarkdown.rstudio.com/) to format dokumentu, który włącza analizę w R do dokumentów wysokiej jakości, raportów, prezentacji i pulpitów nawigacyjnych.

R narzędzi dla programu Visual Studio (RTVS) zawiera szablon elementu R Markdown, Edytor obsługuje (w tym IntelliSense dla kodu języka R w edytorze), możliwości generowania pliku i na żywo w wersji zapoznawczej.

## <a name="using-r-markdown"></a>Przy użyciu języka znaczników Markdown R

1. Zamknij program Visual Studio.
1. (Tylko jeden raz) Zainstaluj `pandoc` z [pandoc.org](http://pandoc.org/installing.html).
1. Uruchom ponownie program Visual Studio, który należy pobrać instalacji pandoc.
1. Zainstaluj `knitr` i `rmarkdown` pakiety, które można wykonać z [okna interaktywnego](interactive-repl-for-r-in-visual-studio.md):

    ```R
    install.packages("knitr")
    install.packages("rmarkdown")

    ```
1. Tworzenie nowego pliku R Markdown, przy użyciu **pliku** > **nowy** > **pliku** polecenia menu i wybierając **R**  >  **R Markdown** z listy. W kontekście projektu, kliknij prawym przyciskiem myszy projekt w Eksploratorze rozwiązań i wybierz **dodać Markdown R** (lub **Dodaj** > **nowy element** i wybierając **R Markdown** z listy).

1. Domyślna zawartość nowego pliku są następujące:

    ~~~markdown
    ---
    title: "Untitled"
    output: html_document
    ---

    This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and Microsoft Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

    When you click the **R Tools | Publish | Preview** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:

    ```{r}
    summary(cars)
    ```

    You can also embed plots, for example:

    ```{r, echo=FALSE}
    plot(cars)
    ```

    Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

    ~~~

## <a name="previews"></a>Wersje zapoznawcze

Visual Studio 2017 wersji 15.5 i nowszych automatycznie udostępnić na żywo Podgląd R Markdown. Aby włączyć funkcję automatycznej synchronizacji między edytorze i podglądu, wybierz **narzędzia R** > **Markdown** > **synchronizacji automatycznej** ( **CTRL**+**Shift**+**Y**). Jeśli nie używasz synchronizacji, można odświeżyć przy użyciu podglądu **narzędzia R** > **Markdown** > **Podgląd Markdown R Załaduj ponownie**.

Można również wyświetlić podgląd pliku w formacie HTML, PDF, i Microsoft Word formatuje prawym przyciskiem myszy w edytorze i wybierając jedną z **Podgląd** poleceń. Te same polecenia są również dostępne na **narzędzia R** > **Markdown** menu. (W starszych wersjach programu Visual Studio te polecenia znajdują się na **narzędzia R** > **publikowania** menu.)

![Podgląd aktywny RMarkdown i innych poleceń menu podglądu](media/rmarkdown-live-preview.png)
