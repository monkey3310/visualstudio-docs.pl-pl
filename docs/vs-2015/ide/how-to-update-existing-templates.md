---
title: 'Porady: aktualizowanie istniejących szablonów | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- item templates, updating existing templates
- Visual Studio templates, updating existing templates
- project templates, updating existing templates
ms.assetid: d585e45b-7fe2-45fa-9cf3-7f2bc060f3c4
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9c5d091e58904cae058c5a2a5ade1b8ceec4c738
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670846"
---
# <a name="how-to-update-existing-templates"></a>Porady: aktualizowanie istniejących szablonów
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [porady: Aktualizacja istniejących szablonów](https://docs.microsoft.com/visualstudio/ide/how-to-update-existing-templates).  
  
Po utworzeniu szablonu i Kompresuj pliki w pliku zip, można zmodyfikować szablon. Można to zrobić ręcznie, zmieniając pliki w szablonie, lub przez wyeksportowanie szablonu z projektu, który jest oparty na szablonie.  
  
## <a name="using-the-export-template-wizard-to-update-an-existing-template"></a>Za pomocą Kreatora szablonu eksportu, aby zaktualizować istniejący szablon  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] udostępnia **Eksportuj szablon** kreatora, który może służyć do aktualizacji istniejącego szablonu.  
  
#### <a name="to-use-export-template-to-update-an-existing-template"></a>Aby wyeksportować szablon służy do aktualizacji istniejącego szablonu  
  
1.  Na **pliku** menu, kliknij przycisk **New** a następnie kliknij przycisk **nowy projekt**.  
  
2.  Wybierz szablon, który chcesz zaktualizować, wprowadź nazwę i lokalizację dla swojego projektu tymczasowej, a następnie kliknij przycisk **OK**.  
  
3.  Modyfikowanie projektu w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
4.  Na **pliku** menu, kliknij przycisk **Eksportuj szablon**i użyj **Eksportuj szablon** kreatora, aby utworzyć nowy szablon.  
  
5.  Po zaktualizowany szablon jest skompresowany do pliku zip, należy usunąć stary plik zip szablonu.  
  
## <a name="manually-updating-an-existing-template"></a>Ręczna aktualizacja istniejącego szablonu  
 Możesz zaktualizować istniejący szablon poza [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] przez modyfikowanie plików w pliku skompresowanym .zip.  
  
#### <a name="to-manually-update-an-existing-template"></a>Aby ręcznie zaktualizować istniejący szablon  
  
1.  Zlokalizuj plik .zip zawierający szablon. Domyślnie ten plik znajduje się w \My Studio *wersji*\My wyeksportowane szablony\\.  
  
2.  Wyodrębnij plik zip.  
  
3.  Zmodyfikować lub usunąć bieżące pliki szablonu lub Dodaj nowe pliki do szablonu.  
  
4.  Otwierać, modyfikować i Zapisz plik .vstemplate XML do obsługi zachowanie zaktualizowane lub nowe pliki. Aby uzyskać więcej informacji na temat schematu .vstemplate, zobacz [odwołanie do schematu szablonu Visual Studio](../extensibility/visual-studio-template-schema-reference.md). Aby uzyskać więcej informacji na temat co można sparametryzować w plikach źródłowych, zobacz [parametry szablonu](../ide/template-parameters.md)  
  
5.  Wybierz pliki do szablonu, kliknij prawym przyciskiem myszy, kliknij przycisk **Wyślij do**, a następnie kliknij przycisk **skompresowany Folder (zip)**. Wybrane pliki są kompresowane w pliku zip.  
  
6.  W tym samym katalogu co stary plik zip, należy umieścić nowy plik zip.  
  
7.  Usuń pliki szablonów wyodrębniony i stary plik zip szablonu.  
  
8.  Start (jako administrator), wiersz polecenia dla deweloperów wystąpienia (w start menu w obszarze **programu Visual Studio 2010 / wiersz polecenia narzędzi/dla deweloperów programu Visual Studio**).  
  
9. Uruchom następujące polecenie: `devenv /installvstemplates`.  
  
## <a name="see-also"></a>Zobacz też  
 [Dostosowywanie szablonów](../ide/customizing-project-and-item-templates.md)   
 [Tworzenie szablonów projektów i elementów](../ide/creating-project-and-item-templates.md)   
 [Odwołanie do schematu szablonu Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Parametry szablonu](../ide/template-parameters.md)   
 [Instrukcje: Tworzenie pakietów startowych](../ide/how-to-create-starter-kits.md)



