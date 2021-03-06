---
title: 'Błąd: Serwer sieci Web został zablokowany i blokuje zlecenie DEBUG | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.webdbg_debug_verb_blocked
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2537868da6c72df9a68c492b650c72d8a980fcb
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474001"
---
# <a name="error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb"></a>Błąd: serwer sieci Web został zablokowany i blokuje zlecenie DEBUG
Wkraczanie do usług XML sieci Web lub aplikacji sieci Web nie powiodło się, ponieważ został uruchomiony narzędzia blokady usług IIS i URLScan, zostały zainstalowane i aktywowane. Ten warunek blokuje usług IIS z otrzymywania zlecenia DEBUG.  
  
 URLScan to narzędzie zabezpieczeń, które działa w połączeniu z narzędzia blokady usług IIS, aby zapewnić możliwość Wyłącz niepotrzebne funkcje i ograniczenia typu żądania HTTP, które serwer przetworzy administratorom witryn sieci Web usług IIS. Blokując określone żądania HTTP, narzędzie URLScan zabezpieczeń zapobiega potencjalnie szkodliwych żądań z uzyskiwaniem dostępu do serwera i uszkodzenia.  
  
 Jeśli aplikacja jest uruchomiona w usługach IIS 6.0 w systemie Windows Server 2003, nie muszą działać narzędzia blokady usług IIS, ponieważ usługi IIS 6.0 zapewnia te same funkcje.  
  
### <a name="to-enable-debugging-on-a-web-server-with-urlscan-installed"></a>Aby włączyć debugowanie na serwerze sieci Web za pomocą narzędzia URLScan zainstalowany  
  
1.  Zlokalizuj plik Urlscan.ini. Zazwyczaj znajduje się on w katalogu, który wygląda następująco:  
  
     C:\WINNT\System32\Inetsrv\urlscan  
  
2.  Tworzenie kopii pliku i nadaj mu nazwę **Urlscan.old**.  
  
3.  Otwórz oryginalną kopię pliku Urlscan.ini za pomocą Notatnika lub dowolnego edytora tekstu.  
  
4.  W Urlscan.ini Znajdź sekcję [AllowVerbs]. Dodaj debugowania do sekcji [AllowVerbs]. Jeśli widzisz; debugowania w sekcji [AllowVerbs], Usuń średnik do usuń znaczniki komentarza zlecenia.  
  
5.  Znajdź sekcję [DenyVerbs]. Jeśli debugowania znajduje się w sekcji [DenyVerbs], należy go usunąć.  
  
6.  Zapisz plik.  
  
7.  Uruchom ponownie serwer lub ponownego uruchomienia usług IIS.  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie aplikacji sieci Web: Błędy i rozwiązywanie problemów](../debugger/debugging-web-applications-errors-and-troubleshooting.md)   
 [Błąd: Serwer sieci Web nie mógł znaleźć żądanego zasobu](../debugger/error-the-web-server-could-not-find-the-requested-resource.md)