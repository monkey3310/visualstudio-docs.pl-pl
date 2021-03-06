---
title: Co&#39;s Nowość w wersji programu Visual Studio 2017 SDK | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 10/31/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 9efcf0a3-dbde-4cab-8ed3-425826a48b2e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6f2a003bc19764aa07262552d3f0cc41316835b6
ms.sourcegitcommit: ef828606e9758c7a42a2f0f777c57b2d39041ac3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2018
ms.locfileid: "39566911"
---
# <a name="what39s-new-in-the-visual-studio-2017-sdk"></a>Co&#39;s Nowość w wersji programu Visual Studio 2017 SDK

Visual Studio SDK zawiera następujące nowe i zaktualizowane funkcje programu Visual Studio 2017.

## <a name="vsix-v3-format"></a>VSIX v3 format

Aby zapewnić obsługę nowej instalacji lekki programu Visual Studio 2017, format manifestu rozszerzenia VSIX został zaktualizowany do wersji 3 (rozszerzeniu VSIX v3).

Nowy format zapewnia obsługę:

* Deklarowanie jawnie warunków wstępnych, aby zostać wykryte i zainstalowane przez Instalator VSIX.
* Zestawy ngen w instalacji rozszerzenia.
* Instalowanie zasobów poza katalog główny zwykle rozszerzenia.

Aby dowiedzieć się więcej o tych zmianach, zobacz następujące tematy:

* [Zmiany w rozszerzalności dla 2017 r.](breaking-changes-2017.md)
* [Obsługa Ngen w rozszerzeniu VSIX v3](ngen-support.md)
* [Instalowanie poza folderem rozszerzeń](set-install-root.md)
* [Często zadawane pytania dotyczące rozszerzalności programu Visual Studio 2017](faq-2017.md)

## <a name="migrate-extensibility-project-to-visual-studio-2017"></a>Migrowanie projektów rozszerzalności do programu Visual Studio 2017

Aby dowiedzieć się, jak zaktualizować ich manifesty VSIX i Twoich projektów rozszerzalności do programu Visual Studio 2017, zobacz [instrukcje: Migrowanie projektów rozszerzalności do programu Visual Studio 2017](how-to-migrate-extensibility-projects-to-visual-studio-2017.md).

## <a name="custom-project-and-item-templates"></a>Niestandardowych szablonów projektów i elementów

Począwszy od programu Visual Studio 2017, skanowanie w poszukiwaniu szablonów elementów i projektów niestandardowych zostanie już wykonane. Zamiast tego rozszerzenia, należy podać plik manifestu szablonu, które opisują lokalizację instalacji tych szablonów. Za pomocą programu Visual Studio 2017 można zaktualizować rozszerzenia VSIX. W przypadku wdrożenia przy użyciu Instalatora MSI rozszerzenia, musisz ręcznie wygenerować plik manifestu szablonu. Aby uzyskać więcej informacji, zobacz [uaktualnianie niestandardowych szablonów projektów i elementów dla programu Visual Studio 2017](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md). Schematu manifestu szablonu jest udokumentowany w [odwołanie do schematu manifestu szablonu Visual Studio](../extensibility/visual-studio-template-manifest-schema-reference.md).

## <a name="updated-extension-performance-guidelines"></a>Wytyczne dotyczące wydajności zaktualizowane rozszerzenie

Pojawiły się nowe [porady: diagnozowanie wydajności rozszerzenia](how-to-diagnose-extension-performance.md) artykuł w obszarze [Zarządzanie pakietami VSPackage](managing-vspackages.md) i pokazuje, jak wykrywać i analizowanie wpływu rozszerzeń w programie Visual Studio uruchamiania i ładowania rozwiązań razy.
