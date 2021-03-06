---
title: 'Porady: dołączyć Profiler do usługi .NET i zbieranie danych pamięci przy użyciu wiersza polecenia | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aeac39af-ad99-479f-aa36-4104356ca512
caps.latest.revision: 33
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6c82556e649dd5538b10874ee501672fb77b4f9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680198"
---
# <a name="how-to-attach-the-profiler-to-a-net-service-to-collect-memory-data-by-using-the-command-line"></a>Porady: dołączanie profilera do usługi .NET i zbieranie danych pamięci przy użyciu wiersza polecenia
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [jak: dołączyć Profiler do usługi .NET i zbieranie danych pamięci przy użyciu wiersza polecenia](https://docs.microsoft.com/visualstudio/profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-memory-data-by-using-the-command-line).  
  
W tym temacie opisano sposób użycia [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] wiersza polecenia narzędzi Profilujących do dołączenia programu profilującego do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] usługi i zbierania danych pamięci. Możesz zbierać dane dotyczące liczby i rozmiaru alokacji pamięci i może również zbierać dane dotyczące okresu istnienia obiektów pamięci.  
  
> [!NOTE]
>  Ulepszone funkcje zabezpieczeń w systemie Windows 8 i Windows Server 2012 wymagają znaczących zmian w taki sposób, programu Visual Studio profiler zbiera dane na tych platformach. Aplikacje Windows Store również wymagają nowych technik zbierania. Zobacz [narzędzia do oceny wydajności w aplikacjach systemu Windows 8 i Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Narzędzia wiersza poleceń dla narzędzi profilowania znajdują się w podkatalogu \team tools\performance Tools [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] katalogu instalacyjnego. Na komputerach 64-bitowym 64-bitowe i 32-bitowe wersje narzędzia są dostępne. Aby użyć narzędzi profilowania z wiersza polecenia, należy dodać ścieżkę narzędzi do zmiennej środowiskowej PATH okna wiersza polecenia lub dodać do niej samo polecenie. Aby uzyskać więcej informacji, zobacz [Określanie ścieżki do narzędzi wiersza polecenia](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Zbieranie danych pamięci z [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] usługi, użyj [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) narzędzia do inicjowania odpowiednich zmiennych środowiskowych na komputerze, który hostuje usługę. Aby skonfigurować go na potrzeby profilowania, należy ponownie uruchomić komputer.  
  
 Następnie użyj [VSPerfCmd](../profiling/vsperfcmd.md) narzędzia, aby dołączyć profiler do procesu usługi. Gdy profiler jest dołączony do usługi, można wstrzymywać i wznawiać zbieranie danych.  
  
 Aby zakończyć sesję profilowania, profiler musi zostać odłączony od usługi, a następnie program profilujący musi być jawnie zamknięty. W większości przypadków zaleca się wyczyszczenie zmiennych środowiskowych profilowania na końcu sesji.  
  
## <a name="attaching-the-profiler"></a>Dołączanie Profiler  
  
#### <a name="to-attach-the-profiler-to-a-net-framework-service"></a>Aby dołączyć Profiler do usługi .NET Framework  
  
1.  Jeśli to konieczne, zainstaluj usługę.  
  
2.  Otwórz okno wiersza polecenia.  
  
3.  Należy zainicjować zmienne środowiskowe profilowania. Wpisz:  
  
     **VSPerfClrEnv** {**/globalsamplegc /globalsamplegclife**} [**/samplelineoff**]  
  
    -   Opcje **/globalsamplegclife** i **/globalsamplegclife** określenie typu pamięci dane mają być zbierane. Określ jeden i tylko jeden z następujących opcji.  
  
     **/globalsamplegc**  
     Umożliwia zbieranie danych alokacji pamięci.  
  
     **/globalsamplegclife**  
     Umożliwia zbieranie danych alokacji pamięci i danych o okresie istnienia obiektu.  
  
    -   **/Samplelineoff** opcja wyłącza kolekcję danych numeru wiersza kodu źródłowego.  
  
4.  Uruchom ponownie komputer, aby ustawić nową konfigurację środowiska.  
  
5.  Jeśli to konieczne, uruchom usługę.  
  
6.  Otwórz okno wiersza polecenia. Jeśli to konieczne, należy dodać ścieżkę profilera do zmiennej środowiskowej PATH.  
  
7.  Uruchom program profiler. Wpisz:  
  
     **Narzędzia VSPerfCmd**[/start](../profiling/start.md) **: Przykładowe**[/output](../profiling/output.md) **:** `OutputFile` [`Options`]      
  
    -   **/Start:sample** opcja inicjuje profiler.  
  
    -   **/Output:** `OutputFile` opcja jest wymagana przy użyciu **/start**. `OutputFile` Określa nazwę i lokalizację pliku danych (Vsp) profilowania.  
  
     Można użyć co najmniej jeden z następujących opcji z **/start:sample** opcji.  
  
    > [!NOTE]
    >  **/User** i **/crosssession** opcje są zazwyczaj wymagane dla usług.  
  
    |Opcja|Opis|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Określa nazwę domeny i użytkownika konta, które jest właścicielem procesu. Ta opcja jest wymagana, jeśli proces działa jako użytkownik inny niż zalogowany użytkownik. Właściciel procesu jest wymieniony w kolumnie Nazwa użytkownika na karcie Procesy Menedżera zadań Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Włącza profilowanie procesów w innych sesjach logowania. Ta opcja jest wymagana, jeśli aplikacja ASP.NET jest uruchomiona w innej sesji. Identyfikator sesji jest wymieniony w kolumnie Identyfikator sesji, na karcie Procesy Menedżera zadań Windows. **Skróconej/CS** może być określona jako skrót **/crosssession**.|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Określa opcjonalny nazwę domeny i użytkownika konta logowania, w którym działa usługa. Konto logowania znajduje się w kolumnie Logowanie jako usługa w Menedżerze sterowania usługami Windows.|  
    |[/ crosssession&#124;cs](../profiling/crosssession.md)|Włącza profilowanie procesów w innych sesjach logowania.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Określa licznik wydajności Windows mają być zbierane podczas profilowania.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Za pomocą **/wincounter** tylko. Określa liczbę milisekund między zdarzeniami zbierania licznika wydajności Windows. Wartość domyślna to 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Określa zdarzenie śledzenie zdarzeń dla Windows (ETW) mają być zbierane podczas profilowania. Zdarzenia ETW są zbierane w pliku oddzielne (ETL).|  
  
8.  Dołącz profiler do usługi. Wpisz:  
  
     **Narzędzia VSPerfCmd**[/ dołączanie](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [[/targetclr](../profiling/targetclr.md)**:**`Version`]    
  
    -   Określ identyfikator procesu lub nazwę procesu usługi. Można wyświetlić identyfikatory i nazwy wszystkich uruchomionych procesów w Menedżerze zadań Windows.  
  
    -   **targetclr:** `Version` Określa wersję środowiska uruchomieniowego języka wspólnego (CLR) do profilu, gdy więcej niż jedna wersja środowiska wykonawczego jest załadowana w aplikacji. Opcjonalna.  
  
## <a name="controlling-data-collection"></a>Kontrolowanie zbierania danych  
 Usługa jest uruchomiona, ale można używać **VSPerfCmd.exe** opcje do zatrzymywania i uruchamiania zapisywania danych do pliku danych profilera. Kontrolowanie zbierania danych umożliwia zbieranie danych dla określonej części wykonywania programu, takiej jak uruchamianie lub zamykanie aplikacji.  
  
#### <a name="to-start-and-stop-data-collection"></a>Aby uruchomić i zatrzymać zbieranie danych  
  
-   Następujące pary **VSPerfCmd** opcji uruchamiają i zatrzymują zbieranie danych. Określ każdą opcję w oddzielnym wierszu poleceń. Włączenie funkcji zbierania danych można włączać i wyłączać wiele razy.  
  
    |Opcja|Opis|  
    |------------|-----------------|  
    |[globalon /globaloff](../profiling/globalon-and-globaloff.md)|Uruchamia (**globalon**) lub zatrzymuje (**/globaloff**) zbieranie danych dla wszystkich procesów.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Uruchamia (**/processon**) lub zatrzymuje (**/processoff**) zbieranie danych dla procesu określonego przez identyfikator procesu (`PID`).|  
    |**/ Dołączanie:**{`PID`&#124;`ProcName`} [/ Odłącz](../profiling/detach.md)[: {`PID`&#124;`ProcName`}]|**/ Dołączanie** rozpoczyna się zbieranie danych dla procesu określonego przez identyfikator procesu lub nazwę procesu. **/ Odłącz** zatrzymuje zbieranie danych dla określonego procesu lub dla wszystkich procesów, jeśli nie określono określonego procesu.|  
  
## <a name="ending-the-profiling-session"></a>Kończenie sesji profilowania  
 Aby zakończyć sesję profilowania, profiler nie może zbierać dane. Możesz zatrzymać zbieranie danych z aplikacji profilowanej metodą próbkowania, przez zatrzymanie usługi lub wywołując **VSPerfCmd / Odłącz** opcji. Następnie wywołaj **VSPerfCmd** [/shutdown](../profiling/shutdown.md) opcję, aby wyłączyć profiler i zamknąć plik danych profilowania. **VSPerfClrEnv /globaloff** polecenie usuwa zmienne środowiskowe profilowania, ale konfiguracja systemu nie jest resetowana do ponownego uruchomienia komputera.  
  
#### <a name="to-end-a-profiling-session"></a>Aby zakończyć sesję profilowania  
  
1.  Wykonaj jedną z następujących czynności, aby odłączyć program profiler od aplikacji docelowej:  
  
    -   Zatrzymaj usługę.  
  
         —lub—  
  
    -   Typ **VSPerfCmd / Odłącz**  
  
2.  Zamknij program profilujący. Wpisz:  
  
     **Narzędzia VSPerfCmd/shutdown**  
  
3.  (Opcjonalnie) Wyczyść zmienne środowiskowe profilowania. Wpisz:  
  
     **VSPerfClrEnv /globaloff**  
  
4.  Uruchom ponownie komputer.  
  
## <a name="see-also"></a>Zobacz też  
 [Usługi profilowania](../profiling/command-line-profiling-of-services.md)   
 [Widoki danych pamięci .NET](../profiling/dotnet-memory-data-views.md)



