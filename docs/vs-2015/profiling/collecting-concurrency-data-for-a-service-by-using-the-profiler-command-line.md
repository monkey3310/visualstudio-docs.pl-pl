---
title: Zbieranie danych współbieżności dla usługi przy użyciu wiersza polecenia Profiler | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 275aacba-b2af-4d34-8931-ee30d777a256
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a8d5d646df224f546d338ac7a9b474cafe8902c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676562"
---
# <a name="collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line"></a>Zbieranie danych współbieżności dla usługi przy użyciu wiersza polecenia profilera
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [zbieranie danych współbieżności dla usługi przy użyciu wiersza polecenia Profiler](https://docs.microsoft.com/visualstudio/profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line).  
  
Metoda współbieżności [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Profiling Tools umożliwia zbieranie danych kontencji zasobów i dane o aktywności wątku, który pokazuje wykorzystanie procesora CPU, rywalizacji wątków, migracji wątków, opóźnień synchronizacji, obszary nachodzące We/Wy i inne zdarzenia systemowe.  
  
> [!NOTE]
>  Ulepszone funkcje zabezpieczeń w systemie Windows 8 i Windows Server 2012 wymagają znaczących zmian w taki sposób, programu Visual Studio profiler zbiera dane na tych platformach. Aplikacje Windows Store również wymagają nowych technik zbierania. Zobacz [narzędzia do oceny wydajności w aplikacjach systemu Windows 8 i Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Typowe zadania  
  
|Zadanie|Powiązana zawartość|  
|----------|---------------------|  
|**Dołącz do uruchomionej usługi .NET**|-   [Porady: dołączyć Profiler do usługi .NET w celu zbierania danych współbieżności](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Dodawanie danych interakcji między warstwami**|-   [Zbieranie danych o interakcji między warstwami](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Dołącz do uruchomionej usługi w języka C/C++**|-   [Porady: dołączyć Profiler do usługi natywnej i zbieranie danych współbieżności](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>Informacje o zadaniach pokrewnych  
  
### <a name="profiling-windows-services"></a>Profilowanie usługi Windows  
  
|Zadanie|Powiązana zawartość|  
|----------|---------------------|  
|**Profil przy użyciu metody próbkowania**|-   [Zbieranie statystyk aplikacji przy użyciu metody próbkowania](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**Profil przy użyciu metody Instrumentacji**|-   [Zbieranie szczegółowych danych o chronometrażu przy użyciu metody Instrumentacji](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**Profile.NET pamięć alokacji i odzyskiwanie pamięci**|-   [Zbieranie danych pamięci .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="profiling-concurrency-data"></a>Dane profilowania współbieżności  
  
|Zadanie|Powiązana zawartość|  
|----------|---------------------|  
|**Profil aplikacji autonomicznych**|-   [Zbieranie danych współbieżności](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Profil aplikacji sieci Web ASP.NET**|-   [Zbieranie danych współbieżności](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### <a name="analyzing-concurrency-data-views-and-reports"></a>Analizowanie danych współbieżności widoków i raportów  
 [Widoki danych rywalizacji o zasoby](../profiling/resource-contention-data-views.md)  
  
 [Concurrency Visualizer](../profiling/concurrency-visualizer.md)  
  
## <a name="reference"></a>Tematy pomocy  
 [Dokumentacja wiersza polecenia narzędzia profilowania](../profiling/command-line-profiling-tools-reference.md)


