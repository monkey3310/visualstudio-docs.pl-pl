---
title: 'Błąd: Monitor debugera zdalnego Microsoft Visual (MSVSMON.EXE) zdaje się nie być uruchomiony na komputerze zdalnym. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.server_machine_no_default
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 86db9931-50e3-4095-b161-802ed8ef39c9
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a7d1c98c1fd8375776c34338e8bac866f8c8cef3
ms.sourcegitcommit: d705e015cb525bfa87a0b93e93376c3956ec2707
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43231277"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-msvsmonexe-does-not-appear-to-be-running-on-the-remote-computer"></a>Błąd: Monitor debugera zdalnego Microsoft Visual (MSVSMON.EXE) zdaje się nie być uruchomiony na komputerze zdalnym.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [błąd: Microsoft zdalny Monitor debugowania Visual Studio (MSVSMON. Z rozszerzeniem EXE) nie jest uruchomiony na komputerze zdalnym. ](https://docs.microsoft.com/visualstudio/debugger/error-the-microsoft-visual-studio-remote-debugging-monitor-msvsmon-exe-does-not-appear-to-be-running-on-the-remote-computer).  
  
Ten komunikat o błędzie oznacza, że program Visual Studio nie można odnaleźć poprawne wystąpienie programu Visual Studio Monitor zdalnego debugowania na komputerze zdalnym. Visual Studio Monitor zdalnego debugowania musi być zainstalowany dla zdalnego debugowania do pracy. Aby uzyskać informacje dotyczące pobierania i konfigurowania zdalnego debugera, zobacz [Ustaw się narzędzi zdalnych na urządzeniu](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).  
  
> [!IMPORTANT]
>  Jeśli uważasz, że ten komunikat został przesłany z powodu błędu w produkcie, zgłoś ten problem w programie Visual Studio [Wyślij uśmiech](http://msdn.microsoft.com/library/5cc9b67a-54d0-41b0-aa8f-80dff4475a6b). Jeśli potrzebujesz więcej pomocy, zobacz [Porozmawiaj z nami](../ide/talk-to-us.md) sposobów na kontakt z firmą Microsoft.  
  
## <a name="i-got-this-message-while-i-was-debugging-in-visual-studio-2010-or-earlier"></a>Został wyświetlony komunikat, gdy został I debugowania w programie Visual Studio 2010 lub starszy  
 Wersja programu Visual Studio, którego używasz w przypadku programu Visual Studio 2010 lub starszy, ten błąd może również występować Jeśli udostępnianie plików i drukarek nie jest włączona. Aby dowiedzieć się więcej na temat tego problemu, zapoznaj się z programu Visual Studio 2010 w niniejszej dokumentacji: [błąd: Microsoft zdalny Monitor debugowania Visual Studio (MSVSMON. Z rozszerzeniem EXE) nie jest uruchomiony na komputerze zdalnym. — Program visual Studio 2010](https://msdn.microsoft.com/library/ms164726\(v=vs.100\).aspx)  
  
## <a name="i-got-this-message-while-i-was-debugging-locally"></a>Został wyświetlony komunikat, gdy został I debugowanie lokalnie  
 Jeśli otrzymujesz ten komunikat, gdy debugujesz lokalnie, oprogramowanie antywirusowe lub zapory innych firm może być stronę. Visual Studio to 32-bitowej aplikacji, więc używa 64-bitowej wersji zdalnego debugera do debugowania 64-bitowych aplikacji. Dwa procesy komunikacji za pośrednictwem sieci lokalnej na komputerze lokalnym. Żaden ruch opuszcza komputera, ale istnieje możliwość, że oprogramowanie zabezpieczeń innych firm mogą blokować komunikacji.  
  
 W poniższych sekcjach wymieniono niektóre inne przyczyny, dlaczego użytkownik może stają się coraz ten komunikat i co można zrobić, aby rozwiązać ten problem.  
  
## <a name="the-remote-machine-is-not-reachable"></a>Maszyna zdalna nie jest dostępny  
 Spróbuj [ping](https://technet.microsoft.com/library/ee624059\(v=ws.10\).aspx) maszyny zdalnej. Jeśli go nie odpowiada na polecenie ping, narzędzi zdalnych nie będzie można połączyć w jedną. Spróbuj ponownie uruchamiając komputer zdalny, a w przeciwnym razie upewniając się, że została poprawnie skonfigurowana w sieci.  
  
## <a name="the-version-of-the-remote-debugger-doesnt-match-the-version-of-visual-studio"></a>Wersja zdalnego debugera nie pasuje do wersji programu Visual Studio  
 Wersję programu Visual Studio, które działają lokalnie musi być zgodna z wersją monitor debugera zdalnego działa na komputerze zdalnym. Aby rozwiązać ten problem, należy pobrać i zainstalować zgodną wersję monitor debugera zdalnego. Przejdź do [Centrum pobierania](http://www.microsoft.com/download) można znaleźć właściwą wersję zdalnego debugera.  
  
## <a name="the-local-and-remote-machines-have-different-authentication-modes"></a>Maszyny lokalne i zdalne mają tryby uwierzytelniania innego  
 Maszyn lokalnych i zdalnych muszą używać tego samego trybu uwierzytelniania. Aby rozwiązać ten problem, upewnij się, że obie maszyny będą używać trybu uwierzytelniania. Aby uzyskać więcej informacji na temat trybów uwierzytelniana, zobacz [omówienie uwierzytelniania Windows](https://technet.microsoft.com/library/hh831472.aspx).  
  
## <a name="the-remote-debugger-is-running-under-a-different-user-account"></a>Debuger zdalny jest uruchomiony w ramach konta innego użytkownika  
 Problem można rozwiązać w jednym z następujących sposobów:  
  
-   Można zatrzymać debuger zdalny i uruchom go ponownie przy użyciu konta, którego używasz na komputerze lokalnym.  
  
-   Zdalny debuger można uruchomić z wiersza polecenia za pomocą **/ allow \<username >** parametru: `msvsmon /allow <username@computer>`  
  
-   Można dodać użytkownika do zdalnego debugera uprawnień (w oknie debugera zdalnego **narzędzia / uprawnienia**).  
  
-   Jeśli nie możesz użyć metody w poprzednich krokach, możesz zezwolić użytkownikowi przeprowadzać debugowanie zdalne. W oknie zdalnego debugera, przejdź do **/Options narzędzia** okna dialogowego. Po wybraniu **bez uwierzytelniania**, można sprawdzić **Zezwalaj dowolnemu użytkownikowi na debugowanie**. Jednak należy używać tej opcji tylko wtedy, gdy możesz nie mieć wyboru, czy znajdują się w sieci prywatnej.  
  
## <a name="the-firewall-on-the-remote-machine-doesnt-allow-incoming-connections-to-the-remote-debugger"></a>Zapora na zdalnym komputerze nie zezwala na połączenia przychodzące do zdalnego debugera  
 Zapora na komputerze programu Visual Studio, a zapora na zdalnym komputerze musi być skonfigurowany do zezwalania na komunikację między Visual Studio i zdalnym debugerem. Aby uzyskać informacji o portach używa zdalnego debugera, zobacz [zdalnego przypisania portów debugera](../debugger/remote-debugger-port-assignments.md). Aby uzyskać informacje o konfigurowaniu zapory Windows, zobacz [skonfigurować zaporę Windows do zdalnego debugowania](../debugger/configure-the-windows-firewall-for-remote-debugging.md).  
  
## <a name="anti-virus-software-is-blocking-the-connections"></a>Oprogramowanie antywirusowe blokuje połączenia  
 Program antywirusowy Windows zezwala na połączenia zdalnego debugera, ale niektóre programy antywirusowe innej firmy mogą je zablokować. Sprawdź w dokumentacji oprogramowanie antywirusowe dowiedzieć się, jak umożliwić tych połączeń.  
  
## <a name="network-security-policy-is-blocking-communication-between-the-remote-machine-and-visual-studio"></a>Zasady zabezpieczeń sieci blokuje komunikację między komputerem zdalnym i programu Visual Studio  
 Przejrzyj zabezpieczenia sieci, aby upewnić się, że nie blokuje komunikacji. Aby uzyskać więcej informacji na temat zasad zabezpieczeń sieci Windows zobacz [Zarządzanie zabezpieczeniami](https://msdn.microsoft.com/library/windows/desktop/ms721855\(v=vs.85\).aspx).  
  
## <a name="the-network-is-too-busy-to-support-remote-debugging"></a>Sieć jest zbyt zajęty, aby zapewnić obsługę zdalnego debugowania  
 Może być konieczne przeprowadzać debugowanie zdalne w innym czasie lub Zmień harmonogram pracy w sieci inny czas.  
  
## <a name="more-help"></a>Więcej pomocy  
 Aby Pomoc zdalny debuger, łącznie z przełączników wiersza polecenia, kliknij przycisk **pomocy / użycia** w oknie debugera zdalnego. Jeśli nie masz otwarty zostanie wyświetlona strona sieci web, kopiując następujący wiersz do **Eksploratora plików** okna. (Należy zastąpić \<katalogu instalacyjnego programu Visual Studio > z lokalizacji instalacji programu Visual Studio.)  
  
 res: / /*\<katalogu instalacyjnego programu Visual Studio >* \Common7\IDE\Remote%20Debugger\x64\msvsmon.exe/help.htm  
  
## <a name="see-also"></a>Zobacz też  
 [Błędy związane z debugowaniem zdalnym i rozwiązywanie problemów](../debugger/remote-debugging-errors-and-troubleshooting.md)



