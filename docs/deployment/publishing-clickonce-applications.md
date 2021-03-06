---
title: Publikowanie aplikacji ClickOnce | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.Options
- Microsoft.VisualStudio.Publish.ClickOnceProvider.PublishWizard.Help
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- ClickOnce applications, publishing
- applications [Visual Studio], ClickOnce deployment
- deploying applications [ClickOnce], publishing ClickOnce applications
ms.assetid: eb6dfe79-f54c-4331-8e36-073688e70973
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9a8ef8f2ae6ed1f198fc5f7661b79764d0a790bd
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279816"
---
# <a name="publish-clickonce-applications"></a>Publikowanie aplikacji ClickOnce
Podczas publikowania [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] właściwości publikowania aplikacji po raz pierwszy, można ustawić za pomocą Kreatora publikacji. Tylko niektóre właściwości są dostępne w Kreatorze; wszystkie pozostałe właściwości są ustawione na wartości domyślne.  
  
 Kolejne zmiany do publikowania właściwości są dokonywane na **Publikuj** strony w **projektanta projektu**.  
  
## <a name="publish-wizard"></a>Kreator publikacji  
 W Kreatorze publikacji można użyć do skonfigurowania podstawowych ustawień do publikowania aplikacji. Dane te obejmują następujące właściwości publikacji:  
  
-   Lokalizacja folderu publikowania — gdzie Visual Studio skopiuje pliki (komputer lokalny, sieciowego udziału plików, serwer FTP lub witryny sieci Web)  
  
-   Lokalizacja folderu instalacji — gdzie użytkownicy będą instalować z (sieciowym udziale plików, serwer FTP, witryny sieci Web, dysk CD/DVD)  
  
-   Online lub Offline dostępność — Jeśli użytkownicy końcowi mogą uzyskiwać dostęp do aplikacji, z lub bez połączenia sieciowego  
  
-   Zaktualizuj częstotliwość — jak często Aplikacja sprawdza dostępność nowych aktualizacji.  
  
 Aby uzyskać więcej informacji, zobacz [porady: publikowanie aplikacji ClickOnce za pomocą Kreatora publikacji](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
## <a name="publish-page"></a>Strona publikowania  
 **Publikuj** strony **projektanta projektu** służy do konfigurowania właściwości dla wdrażania ClickOnce. Poniższa tabela zawiera listę tematów.  
  
|Tytuł|Opis|  
|-----------|-----------------|  
|[Porady: Określanie lokalizacji kopiowania plików w programie Visual Studio](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)|W tym artykule opisano sposób ustawiania, gdzie program Visual Studio umieści pliki aplikacji i manifestów.|  
|[Porady: Określanie lokalizacji, w której użytkownicy końcowi będą przeprowadzać instalacje](../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)|Opisuje sposób ustawiania lokalizacji, z którego użytkownicy używają do pobrania i zainstalowania aplikacji.|  
|[Porady: Określanie ClickOnce w trybie offline lub online instalowania tryb](../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)|W tym artykule opisano, jak określić, czy aplikacja będzie dostępna w trybie offline lub online.|  
|[Porady: ustawienie ClickOnce wersji publikacji](../deployment/how-to-set-the-clickonce-publish-version.md)|W tym artykule opisano sposób ustawiania ClickOnce **opublikować wersję** właściwość, która określa, czy w przypadku publikowania aplikacji będzie traktowane jako aktualizację.|  
|[Porady: automatyczne zwiększenie ClickOnce wersji publikacji](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)|Opisuje sposób automatycznie zwiększ numer poprawki **PublishVersion** każdorazowo, możesz opublikować aplikację.|  
  
 Aby uzyskać więcej informacji, zobacz [strona publikowania, Projektant projektu](../ide/reference/publish-page-project-designer.md)  
  
### <a name="application-files-dialog-box"></a>Okno dialogowe pliki aplikacji  
 To okno dialogowe umożliwia określenie, jak pliki w projekcie są podzielone na publikowanie, dynamicznego pobierania i aktualizowania. Zawiera ona siatki, który wyświetla listę plików projektu, które nie zostały wyłączone domyślnie, lub które mają grupa pobierania.  
  
 Aby wykluczyć pliki, oznaczyć pliki jako pliki danych lub wymagania wstępne i tworzyć grupy plików instalacji warunkowe w interfejsie użytkownika programu Visual Studio, zobacz [porady: Określanie plików publikowanych za pomocą technologii ClickOnce](../deployment/how-to-specify-which-files-are-published-by-clickonce.md). Można również oznaczyć pliki danych przy użyciu Mage.exe. Aby uzyskać więcej informacji, zobacz [porady: uwzględnianie pliku danych w aplikacji ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
### <a name="prerequisites-dialog-box"></a>Wstępnie wymagane składniki — Okno dialogowe  
 To okno dialogowe określa, które wstępnie wymagane składniki są zainstalowane, a także jak są one zainstalowane. Aby uzyskać więcej informacji, zobacz [porady: Instalowanie wymagań wstępnych przy użyciu aplikacji ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md) i [wstępnie wymagane składniki, okno dialogowe](../ide/reference/prerequisites-dialog-box.md).  
  
### <a name="application-updates-dialog-box"></a>Okno dialogowe aktualizacji aplikacji  
 To okno dialogowe określa, jak instalacja aplikacji ma sprawdzać dostępność aktualizacji. Aby uzyskać więcej informacji, zobacz [porady: Zarządzanie aktualizacji dla aplikacji ClickOnce](../deployment/how-to-manage-updates-for-a-clickonce-application.md).  
  
### <a name="publish-options-dialog-box"></a>Okno dialogowe Opcje publikowania  
 Okno dialogowe opcji publikowania Określa opcje wdrażania aplikacji.  
  
|||  
|-|-|  
|[Porady: Zmienianie języka publikacji dla aplikacji ClickOnce](../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)|Opisuje sposób określania języka i kultury, aby dopasować zlokalizowanej wersji.|  
|[Porady: Określanie nazwy menu Start dla aplikacji ClickOnce](../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)|W tym artykule opisano, jak zmienić nazwę wyświetlaną dla aplikacji ClickOnce.|  
|[Porady: Określanie linku do pomocy technicznej](../deployment/how-to-specify-a-link-for-technical-support.md)|W tym artykule opisano sposób ustawiania **adres URL pomocy technicznej** właściwość, która identyfikuje strony sieci Web lub udziału plików, gdzie użytkownicy mogą przejść w celu uzyskania informacji o aplikacji.|  
|[Porady: Określanie adresu URL pomocy technicznej dla indywidualnych wstępnie wymaganych składników wdrożenia ClickOnce](../deployment/how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment.md)|Pokazano, jak ręcznie zmienić manifest aplikacji, aby uwzględnić adresy URL poszczególnych pomocy technicznej dla poszczególnych wymagań wstępnych.|  
|[Porady: określanie strony publikowania dla aplikacji ClickOnce](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)|W tym artykule opisano sposób generowania i opublikować domyślna strona internetowa (publish.htm) wraz z aplikacji|  
|[Porady: Dostosowywanie domyślnej strony sieci Web technologii ClickOnce](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)|Opisuje sposób dostosowywania strony sieci Web, która jest automatycznie generowany i opublikowanych wraz z aplikacji.|  
|[Porady: włączenie funkcji AutoStart dla instalacji z dysku CD](../deployment/how-to-enable-autostart-for-cd-installations.md)|W tym artykule opisano, jak włączyć automatyczne uruchamianie aplikacji ClickOnce jest uruchamiane automatycznie, gdy znajduje się nośnik.|  
  
## <a name="related-tpics"></a>Powiązane tpics  
  
|Tytuł|Opis|  
|-----------|-----------------|  
|[Porady: Tworzenie skojarzeń plików aplikacji do ClickOnce](../deployment/how-to-create-file-associations-for-a-clickonce-application.md)|W tym artykule opisano sposób dodawania obsługi rozszerzenia nazw plików dla aplikacji ClickOnce.|  
|[Porady: pobieranie informacji o ciągu zapytania w aplikacji ClickOnce w trybie online](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)|Pokazuje, jak pobrać parametry przekazywane w adresie URL, używanych do uruchamiania aplikacji ClickOnce.|  
|[Porady: wyłączanie aktywacji adresu URL aplikacji ClickOnce przy użyciu narzędzia Projektant](../deployment/how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer.md)|Opisuje sposób wymuszenie użytkowników, aby uruchomić aplikację z **Start** menu przy użyciu projektanta.|  
|[Porady: wyłączanie aktywacji adresu URL aplikacji ClickOnce](../deployment/how-to-disable-url-activation-of-clickonce-applications.md)|Opisuje sposób wymuszenie użytkowników, aby uruchomić aplikację z **Start** menu.|  
|[Wskazówki: Pobieranie zestawów na żądanie z wdrożeniem ClickOnce interfejsu API przy użyciu narzędzia Projektant](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)|Wyjaśnia, jak można pobrać zestawów aplikacji tylko wtedy, gdy najpierw są one używane przez aplikację za pomocą projektanta.|  
|[Wskazówki: Pobieranie zestawów na żądanie przy użyciu wdrażania interfejsu API ClickOnce](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Wyjaśnia, jak można pobrać zestawów aplikacji tylko wtedy, gdy najpierw są one używane przez aplikację.|  
|[Wskazówki: Pobieranie zestawów satelickich na żądanie przy użyciu wdrażania interfejsu API ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Opisuje sposób oznaczania zestawy satelickie jako opcjonalną i Pobierz tylko zestaw na komputerze klienckim musi uzyskać bieżące ustawienia kultury.|  
|[Wskazówki: Ręczne wdrażanie aplikacji ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)|W tym temacie omówiono wdrażanie aplikacji ClickOnce przy użyciu narzędzia .NET Framework.|  
|[Wskazówki: Ręczne wdrażanie aplikacji ClickOnce, które nie wymagają ponownego podpisywania i zachowują informacje o znakowaniu](../deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required.md)|Wyjaśnia, jak wdrożyć aplikację ClickOnce bez ponownego podpisywania manifestów za pomocą narzędzia .NET Framework.|  
|[Porady: Konfigurowanie projektów pod kątem platform docelowych](../ide/how-to-configure-projects-to-target-platforms.md)|Opisano sposób publikowania dla 64-bitowy procesor, zmieniając **Procesora docelowego** lub **platformę docelową** właściwość w projekcie.|  
|[Przewodnik: Włączanie aplikacji ClickOnce do uruchamiania na wielu wersji programu .NET Framework](https://msdn.microsoft.com/library/7f4383af-ed87-4853-b4d4-02a3967a5fd9)|Wyjaśnia, jak umożliwić aplikacji ClickOnce zainstalować i uruchomić przy użyciu wielu wersji programu .NET Framework.|  
|[Przewodnik: Tworzenie niestandardowego Instalatora dla aplikacji ClickOnce](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md)|Wyjaśnia sposób tworzenia niestandardowego Instalatora, aby zainstalować aplikację ClickOnce.|  
|[Porady: publikowanie aplikacji WPF przy użyciu włączonej funkcji stylów wizualnych](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md)|Zawiera instrukcje krok po kroku, aby rozwiązać błąd, który jest wyświetlany, gdy spróbujesz opublikować aplikację WPF, która ma włączonej funkcji stylów wizualnych.|  
  
## <a name="see-also"></a>Zobacz także  
 [Wdrażania i zabezpieczeń ClickOnce](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce — odwołanie](../deployment/clickonce-reference.md)