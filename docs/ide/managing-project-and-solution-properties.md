---
title: Zarządzanie właściwościami projektów i rozwiązań
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 96581fbaff9c2ddc85fbb92d73096f2a369d4c7b
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746315"
---
# <a name="manage-project-and-solution-properties"></a>Zarządzanie właściwościami projektów i rozwiązań

Projekty mają właściwości, które będą zarządzały sposobem wiele aspektów kompilacji, debugowanie, testowania i wdrażania. Niektóre właściwości są wspólne dla wszystkich typów projektów, a niektóre są unikatowe dla określonego języka lub platformy. Aby dostęp do właściwości projektu, prawym przyciskiem myszy węzeł projektu w **Eksploratora rozwiązań** i wybierając polecenie **właściwości**, lub wpisując "właściwości" w **Szybkie uruchamianie** pole wyszukiwania na pasku menu.

![Menu kontekstowe projektu](../ide/media/vs2015_proj_prop_menu.gif)

Projekty .NET mogą także mieć węzeł właściwości w drzewo projektu.

![Właściwości węzła drzewa Eksploratora rozwiązań](../ide/media/vs2015_props_se.png)

## <a name="project-properties"></a>Właściwości projektu

Właściwości projektu są zorganizowane w grupy, a każda grupa ma swoją własną stronę właściwości. Strony może być różna dla różnych języków i typów projektów.

### <a name="c-visual-basic-and-f-projects"></a>Projektów C#, VB i F #

W projektach C#, VB i F #, właściwości są widoczne w **projektanta projektu**. Na poniższej ilustracji pokazano **kompilacji** stronę właściwości projektu WPF w języku C#:

![Projektant projektu programu Visual Studio](../ide/media/vs2015_proppage_build.png)

Aby uzyskać informacje o poszczególnych stron właściwości w **projektanta projektu**, zobacz [właściwości odwołanie do projektu](../ide/reference/project-properties-reference.md).

> [!TIP]
> Rozwiązania ma kilka właściwości i dlatego projektu elementów; te właściwości są dostępne w [okna właściwości](../ide/reference/properties-window.md), a nie **projektanta projektu**.

### <a name="c-and-javascript-projects"></a>Projekty C++ i JavaScript

Projekty C++ i JavaScript ma inny użytkownik interfejsu do zarządzania właściwości projektu. Na ilustracji przedstawiono strony właściwości projektu C++ (stron JavaScript są podobne):

![Visual C&#43; &#43; właściwości projektu](../ide/media/vs2015_projprops_cpp.png)

Informacji o właściwościach projektu C++, zobacz [pracować z właściwości projektu (C++)](/cpp/ide/working-with-project-properties). Aby uzyskać więcej informacji o właściwościach JavaScript, zobacz [strony właściwości, JavaScript](../ide/reference/property-pages-javascript.md).

## <a name="solution-properties"></a>Właściwości rozwiązania

Aby uzyskać dostęp do właściwości w ramach rozwiązania, kliknij prawym przyciskiem myszy węzeł rozwiązania w **Eksploratora rozwiązań** i wybierz polecenie **właściwości**. W oknie dialogowym można ustawić konfiguracje projektu dla **debugowania** lub **wersji** kompilacji, wybierz projekty, do których powinny być uruchamiania projektu podczas **F5** naciśnięty i kod zestawu Opcje analizy.

## <a name="see-also"></a>Zobacz także

- [Rozwiązania i projekty w programie Visual Studio](../ide/solutions-and-projects-in-visual-studio.md)
