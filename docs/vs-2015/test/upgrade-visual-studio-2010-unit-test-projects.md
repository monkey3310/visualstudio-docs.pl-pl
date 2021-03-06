---
title: Uaktualnianie projektów testów jednostkowych programu Visual Studio 2010 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1502b51-d6db-4894-9fbf-4a5723e4bb1a
caps.latest.revision: 8
ms.author: gewarren
manager: douge
ms.openlocfilehash: e06a58e6015a99db83bf729d16196551c5126d12
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629804"
---
# <a name="upgrade-visual-studio-2010-unit-test-projects"></a>Uaktualnianie projektów testów jednostkowych programu Visual Studio 2010
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] zawiera zgodność projektu testowego z [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] projekty testowe z dodatkiem SP1. Na przykład przetestować projektów, które zostały utworzone z [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] z dodatkiem SP1 można otworzyć w programie [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] bez jakiegokolwiek uaktualnienia. W związku z tym, zespół może używać zarówno [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] z dodatkiem SP1 i [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] do pracy z tym samym projekcie testów. Aby uzyskać więcej informacji, zobacz [aktualizowanie testów z programu Visual Studio 2010](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52).  
  
 [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] wprowadzono kilka zmian w celu przeprowadzania testów jednostkowych. W związku z tym ważne jest, aby zrozumieć problemy ze zgodnością między poprzednich wersji programu Visual Studio i [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. Wśród zmiany testy jednostkowe, znaczące zmiany jest fakt, że [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] zawiera więcej niż jeden szablon projektu testu, łącznie z szablonem projektu testu jednostki. Nowe testy jednostkowe są dodawane do nowego szablonu projektu testu jednostki. Testy jednostkowe można również uwzględnić w innym nowego szablonu projektu testu o nazwie szablon projektu kodowanego testu interfejsu użytkownika. Aby uzyskać więcej informacji na temat nowych szablonów projektu testowego, zobacz [uaktualnianie testów ze starszych wersji programu Visual Studio](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52). Domyślnie nowe projekty testów jednostkowych już nie zawierają pliku ustawień testu. Z wyjątkiem pliku ustawień testu, zwiększa wydajność testów jednostkowych. Aby zapewnić zgodność można nadal używać istniejących projektów testów, które zostały utworzone za pomocą programu Visual Studio 2010. Jednak zaleca się, że usuniesz plik ustawień testu, które są skojarzone z projektu testowego, ze względu na wydajność, chyba że istnieje konkretna potrzeba użycia pliku ustawień testu. Na przykład można przechowywać plik ustawień testu, jeśli testy jednostkowe działają w środowisku rozproszonym, lub należy zebrać szczegółowe dane diagnostyczne. Jeśli masz potrzebę podobne, przy użyciu nowego szablonu projektu testu jednostki lub kodowanego testu interfejsu użytkownika szablonu projektu, ręcznie dodaniem pliku ustawień testu do nich również.  
  
> [!NOTE]
>  Testów jednostkowych istniejącej w Twojej [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] projekty testowe z dodatkiem SP1 będzie działać bezproblemowo między [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] z dodatkiem SP1 i [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. Po otwarciu projektu testowego programu Visual Studio 2010 zawierający testy jednostkowe w plikach projektu testu są wprowadzane żadne zmiany [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], lub na odwrót.  
  
> [!CAUTION]
>  Nie można otworzyć programu Visual Studio 2010 w języku C + +/ CLI projektu tego zestawu narzędzi 11.0 elementy docelowe — oznacza to, że projekt utworzony w programie Visual Studio 2012. To ograniczenie obowiązuje dla wszystkich C + +/ CLI projektów nie po prostu C + +/ projektów testów jednostkowych interfejsu wiersza polecenia.  
  
> [!NOTE]
>  Można uruchomić nowe testy jednostkowe przy użyciu vstest.console.exe z wiersza polecenia. Aby uzyskać więcej informacji o używaniu vstest.console.exe, zobacz [opcje wiersza poleceń VSTest.Console.exe](http://msdn.microsoft.com/library/52e1689d-b1a8-4589-bd98-99a55acd0a11), lub uruchomić polecenie przy użyciu przełącznika pomocy: **vstest.console.exe /?**. Można uruchomić testy jednostkowe istniejących przy użyciu MStest.exe. Aby uzyskać więcej informacji, zobacz [Uruchamianie testów automatycznych z wiersza polecenia przy użyciu przełącznika MSTest](http://msdn.microsoft.com/library/39b61ad0-0055-44b5-963f-25d8a6b51581) i [opcje wiersza polecenia MSTest.exe](http://msdn.microsoft.com/library/8813ba7f-e790-4e92-9f91-7080508a1c36).  
  
 Inna ważna różnica jest nowym Eksploratorze testów. W [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], niektóre z testów systemu windows może być znane z poprzedniej wersji programu Visual Studio zostały wycofane, takich jak okna widoku testu. Eksplorator testów zaprojektowano w celu lepszej obsługi deweloperów i zespołów, które włączają testowanie jednostek w swoich praktyk tworzenia oprogramowania. Aby uzyskać więcej informacji, zobacz [Uruchamianie testów jednostkowych w Eksploratorze testów](../test/run-unit-tests-with-test-explorer.md).  
  
## <a name="compatibility-issues-between-visual-studio-2010-sp1-and-visual-studio-2012"></a>Problemy ze zgodnością między Visual Studio 2010 z dodatkiem SP1 i Visual Studio 2012  
 Poniżej przedstawiono niektóre problemy, aby mieć świadomość, migrując testów między Visual Studio 2010 SP1 i [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]:  
  
|Funkcji testów jednostkowych|Problem|Rozwiązanie|  
|-----------------------------|-----------|--------------|  
|Listy testu (.vsmdi pliki) są przestarzałe w [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)].|Nie można utworzyć nowych list testów (.vsmdi pliki) lub uruchomienie listy testów z programu Visual Studio. **Porada:** kategorie testów zapewniają większą elastyczność niż lista testów ze starszych wersji programu Microsoft Visual Studio. Można używać operatorów logicznych za pomocą kategorii testów, aby uruchomić testy z wielu kategorii razem lub ograniczyć testy, które są uruchamiane do testów, które należą do wielu kategorii. Również kategorie testu są łatwe do dodania, gdy tworzysz swoje metody testowe i nie masz listy testów po utworzeniu swoich metod testowych. Za pomocą kategorii testów, nie trzeba ewidencjonować i zapoznaj się z  **\<Nazwa rozwiązania > .vsmdi** pliku, który obsługuje listy testów. Aby uzyskać więcej informacji, zobacz [Defining Test Categories to Group Your Tests](http://msdn.microsoft.com/library/2c26a648-f068-4d60-99b6-b9747b7bdbc9).|-Aby zachować zgodność z istniejących projektów testów korzystających z listy testów, możesz się nadal edytować pliki .vsmdi, przy użyciu programu Visual Studio.<br />— Mimo że nie można uruchomić listy testów zmigrowanych z programu Visual Studio, nadal można uruchomić je przy użyciu mstest.exe z wiersza polecenia. Aby uzyskać więcej informacji, zobacz [Uruchamianie testów automatycznych z wiersza polecenia przy użyciu przełącznika MSTest](http://msdn.microsoft.com/library/39b61ad0-0055-44b5-963f-25d8a6b51581)<br />— Jeśli była używana lista testów w definicji kompilacji, można nadal z niego korzystać. Aby uzyskać więcej informacji, zobacz [porady: Konfigurowanie i zaplanowane do uruchomienia testów po skompilowaniu aplikacji](http://msdn.microsoft.com/en-us/32acfeb1-b1aa-4afb-8cfe-cc209e6183fd) i [Uruchom testy w procesie kompilacji](http://msdn.microsoft.com/library/d05743a1-c5cf-447e-bed9-bed3cb595e38).|  
|Prywatne Akcesory zostały zaniechane w [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)].<br /><br /> W poprzednich wersjach programu Visual Studio, można użyć do określenia wewnętrznego aplikacji (API) interfejsy programowania i utworzyć odpowiednika publiczny interfejs API, który można wywołać w testach, które z kolei, programie Publicize wywołania w wewnętrznych interfejsach API produktu. Generowanie kodu można używać do tworzenia wycinków testu i generowanie fragmentu kodu wewnątrz tego wycinka.|Nie można utworzyć prywatne Akcesory.|<ul><li>Projekty testowe w usłudze Visual Studio 2010 będzie skompilować i działają w [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. Kompilacja będzie zawierać ostrzeżenia danych wyjściowych.</li><li>Jeśli nadal potrzebujesz do testów wewnętrznych interfejsach API, masz następujące opcje:<br /><br /> <ul><li>Użyj <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject> klasy, które ułatwiają dostęp do wewnętrznych i prywatnych interfejsów API w kodzie. Znaleziono w zestawie Microsoft.VisualStudio.QualityTools.UnitTestFramework.dll.</li><li>Utwórz strukturę odbicia, która będzie mogła odzwierciedlają poza swój kod, aby dostęp do interfejsów API wewnętrznego lub prywatnego.</li><li>W przypadku wewnętrznej kod próbuje uzyskać dostęp można uzyskiwać dostęp za pomocą interfejsów API <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> tak swój kod testu może uzyskiwać dostęp do wewnętrznych interfejsach API.</li></ul></li></ul>|  
|Wpływ na testowanie zostanie usunięty.|||  
|Udostępnianie wyników wykonywania za pomocą dzienników TRX z Eksploratora testów.||Można nadal uzyskać TRX dzienniki pochodzące zarówno z wiersza polecenia i kompilacji zespołowej.|  
  
## <a name="see-also"></a>Zobacz też  
 [Przenoszenie, migrowanie i uaktualnianie projektów programu Visual Studio](../porting/porting-migrating-and-upgrading-visual-studio-projects.md)   
 [Testowanie jednostek kodu](../test/unit-test-your-code.md)   
 [Uaktualnianie testów ze starszych wersji programu Visual Studio](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52)   
 [Uaktualnianie kodowanych testów interfejsu użytkownika programu Visual Studio 2010](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)