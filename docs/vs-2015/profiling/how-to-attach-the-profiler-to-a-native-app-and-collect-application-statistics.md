---
title: 'Porady: dołączanie Profiler do natywnej aplikacji autonomicznej i zbieranie statystyk aplikacji przy użyciu wiersza polecenia | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df44fe42-281b-4398-b3fc-277b62ae41f1
caps.latest.revision: 36
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0534686b5cb90bde9bf846c62ea82ffa56bf0249
ms.sourcegitcommit: d705e015cb525bfa87a0b93e93376c3956ec2707
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43231166"
---
# <a name="how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-application-statistics-by-using-the-command-line"></a>Porady: dołączanie profilera do autonomicznej aplikacji natywnej i zbieranie statystyk aplikacji przy użyciu wiersza polecenia
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [jak: dołączyć Profiler do natywnej aplikacji autonomicznej i zbieranie statystyk aplikacji przy użyciu wiersza polecenia](https://docs.microsoft.com/visualstudio/profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-application-statistics-by-using-the-command-line).  
  
W tym temacie opisano sposób użycia [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] narzędzi wiersza poleceń Profiling Tools dołączyć Profiler do aplikacji uruchomionej natywnej autonomicznej (klienta) i zbierania statystyk wydajności przy użyciu metody próbkowania.  
  
> [!NOTE]
>  Ulepszone funkcje zabezpieczeń w systemie Windows 8 i Windows Server 2012 wymagają znaczących zmian w taki sposób, programu Visual Studio profiler zbiera dane na tych platformach. Aplikacje Windows Store również wymagają nowych technik zbierania. Zobacz [narzędzia do oceny wydajności w aplikacjach systemu Windows 8 i Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Narzędzia wiersza poleceń dla narzędzi profilowania znajdują się w podkatalogu \team tools\performance Tools [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] katalogu instalacyjnego. Na komputerach 64-bitowym 64-bitowe i 32-bitowe wersje narzędzia są dostępne. Aby użyć narzędzi profilowania z wiersza polecenia, należy dodać ścieżkę narzędzi do zmiennej środowiskowej PATH okna wiersza polecenia lub dodać do niej samo polecenie. Aby uzyskać więcej informacji, zobacz [Określanie ścieżki do narzędzi wiersza polecenia](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Gdy profiler jest dołączony do aplikacji, można wstrzymywać i wznawiać zbieranie danych. Aby zakończyć sesję profilowania, Profiler musi nie jest już dołączony do aplikacji i Profiler musi być jawnie zamknięty.  
  
## <a name="attach-the-profiler"></a>Dołącz Profiler  
 Aby dołączyć Profiler do aplikacji docelowej, używając Profiler, należy użyć **VSPerfCmd/start** i **/ dołączanie** opcji, aby zainicjować Profiler i dołączyć do aplikacji docelowej. Można określić **/start** i **/ dołączanie** oraz ich odpowiednie opcje w jednym wierszu polecenia. Można również dodać **/globaloff** opcję, aby wstrzymać zbieranie danych przy uruchamianiu aplikacji docelowej. Następnie użyj **globalon** aby rozpocząć zbieranie danych.  
  
#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Aby dołączyć Profiler do działającej aplikacji .NET Framework  
  
1.  Otwórz okno wiersza polecenia.  
  
2.  Uruchom program profiler. Wpisz:  
  
     **/ OUTPUT /start:sample VSPerfCmd:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: Przykładowe** opcja inicjuje profiler.  
  
    -   [/Output](../profiling/output.md)**:** `OutputFile` opcja jest wymagana przy użyciu **/start**. `OutputFile` Określa nazwę i lokalizację pliku danych (Vsp) profilowania.  
  
     Można użyć dowolnego z następujących opcji z **/start:sample** opcji.  
  
    |Opcja|Opis|  
    |------------|-----------------|  
    |[/ User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Określa nazwę domeny i użytkownika konta, które jest właścicielem PROFILOWANEGO procesu. Ta opcja jest wymagana tylko wtedy, gdy proces działa jako użytkownik inny niż zalogowany użytkownik. Właściciel procesu jest wymieniony w kolumnie Nazwa użytkownika na karcie Procesy Menedżera zadań Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Włącza profilowanie procesów w innych sesjach. Ta opcja jest wymagana, jeśli aplikacja ASP.NET jest uruchomiona w innej sesji. Identyfikator sesji jest wymieniony w kolumnie Identyfikator sesji, na karcie Procesy Menedżera zadań Windows. **Skróconej/CS** może być określona jako skrót **/crosssession**.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Określa licznik wydajności Windows mają być zbierane podczas profilowania.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Za pomocą **/wincounter** tylko. Określa liczbę milisekund między zdarzeniami zbierania licznika wydajności Windows. Wartość domyślna to 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Określa zdarzenie śledzenie zdarzeń dla Windows (ETW) mają być zbierane podczas profilowania. Zdarzenia ETW są zbierane w pliku oddzielne (ETL).|  
  
3.  Dołącz profiler do aplikacji docelowej. Wpisz:  
  
     **Narzędzia VSPerfCmd**[/ dołączanie](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [`Sample Event`]    
  
     `PID` Określa identyfikator procesu aplikacji docelowej. `ProcessName` Określa nazwę procesu. Należy pamiętać, że jeśli określisz `ProcessName` i działa wiele procesów, które mają taką samą nazwę, wyniki są nieprzewidywalne. Można wyświetlić identyfikatory i nazwy wszystkich uruchomionych procesów w Menedżerze zadań Windows.  
  
     Domyślnie dane dotyczące wydajności są próbkowane co 10 000 000 niewstrzymanych procesora zegara cykli. Jest to około 100 razy na sekundę w przypadku procesora 1GH. Możesz określić jedną z następujących opcji, aby zmienić interwał cyklu zegara lub określić inne zdarzenie próbkowania.  
  
    |Zdarzenie próbkowania|Opis|  
    |------------------|-----------------|  
    |[/Timer](../profiling/timer.md) **:** `Interval`|Zamienia interwał próbkowania na liczbę cykli zegara niewstrzymanych, które są określone przez `Interval`.|  
    |[Timer](../profiling/pf.md)[**:**`Interval`]|Zamienia zdarzenie próbkowania na błędy stron. Jeśli `Interval` zostanie określona, ustawia liczbę błędów stron pomiędzy próbkami. Domyślna to 10.|  
    |[/ sys](../profiling/sys-vsperfcmd.md) [**:**`Interval`]|Zamienia zdarzenie próbkowania na wywołania systemowe z procesu do jądra systemu operacyjnego (syscalls). Jeśli `Interval` zostanie określona, ustawia liczbę wywołań pomiędzy próbkami. Domyślna to 10.|  
    |[/ Licznik](../profiling/counter.md) **:** `Config`|Zamienia zdarzenie próbkowania i interwał licznik wydajności procesora oraz interwał, który jest określony w `Config`.|  
  
## <a name="controlling-data-collection"></a>Kontrolowanie zbierania danych  
 Gdy uruchomiona jest aplikacja docelowa, można użyć opcji VSPerfCmd.exe, uruchamianie i zatrzymywanie zapisywania danych do pliku danych profilera. Kontrolowanie zbierania danych umożliwia zbieranie danych dla określonej części wykonywania programu, takiej jak uruchamianie lub zamykanie aplikacji.  
  
#### <a name="to-start-and-stop-data-collection"></a>Aby uruchomić i zatrzymać zbieranie danych  
  
-   Następujące pary **VSPerfCmd** opcji uruchamiają i zatrzymują zbieranie danych. Określ każdą opcję w oddzielnym wierszu poleceń. Włączenie funkcji zbierania danych można włączać i wyłączać wiele razy.  
  
    |Opcja|Opis|  
    |------------|-----------------|  
    |[globalon /globaloff](../profiling/globalon-and-globaloff.md)|Uruchamia (**globalon**) lub zatrzymuje (**/globaloff**) zbieranie danych dla wszystkich procesów.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Uruchamia (**/processon**) lub zatrzymuje (**/processoff**) zbieranie danych dla procesu, który jest określony przez `PID`.|  
    |[/ Dołączanie](../profiling/attach.md) **:** `PID` [/ Odłącz](../profiling/detach.md)|**/ Dołączanie** rozpoczyna się zbieranie danych dla procesu określonego przez `PID`. **/ Odłącz** zatrzymuje zbieranie danych dla wszystkich procesów.|  
  
## <a name="ending-the-profiling-session"></a>Kończenie sesji profilowania  
 Aby zakończyć sesję profilowania, profiler musi zostać odłączony od wszystkich profilowanych procesów i program profilujący musi być jawnie zamknięty. Możesz odłączyć profiler od aplikacji, która była profilowana przy użyciu metody próbkowania przez zamknięcie aplikacji lub przez wywołanie **VSPerfCmd / Odłącz** opcji. Następnie wywołaj **VSPerfCmd/shutdown** opcję, aby wyłączyć profiler i zamknąć plik danych profilowania. **VSPerfClrEnv / off** polecenie usuwa zmienne środowiskowe profilowania.  
  
#### <a name="to-end-a-profiling-session"></a>Aby zakończyć sesję profilowania  
  
1.  Wykonaj jedną z następujących czynności, aby odłączyć profiler od aplikacji docelowej.  
  
    -   Typ **VSPerfCmd / Odłącz**  
  
         —lub—  
  
    -   Zamknij aplikację docelową.  
  
2.  Zamknij program profilujący. Wpisz:  
  
     **Narzędzia VSPerfCmd** [ /shutdown](../profiling/shutdown.md)  
  
3.  (Opcjonalnie) Wyczyść zmienne środowiskowe profilowania. Wpisz:  
  
     **VSPerfClrEnv / off**  
  
## <a name="see-also"></a>Zobacz też  
 [Profilowanie aplikacji autonomicznych](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Widok danych metody próbkowania](../profiling/profiler-sampling-method-data-views.md)



