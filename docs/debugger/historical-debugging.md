---
title: Debugowanie historyczne | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7cc5ddf2-2f7c-4f83-b7ca-58e92e9bfdd2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a622fcb91ad40e7d0777f37ce87e9a2cb950695
ms.sourcegitcommit: a749c287ec7d54148505978e8ca55ccd406b71ee
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2018
ms.locfileid: "46542406"
---
# <a name="historical-debugging"></a>Debugowanie historyczne
Debugowanie historyczne jest tryb debugowania, która jest zależna od informacji zbieranych przez IntelliTrace. Umożliwia on przenoszenie do tyłu i do przodu przez wykonanie aplikacji i sprawdzić jego stan.  
  
 Za pomocą funkcji IntelliTrace w programie Visual Studio Enterprise (ale nie w wersjach Professional lub Community).  
  
## <a name="why-use-historical-debugging"></a>Dlaczego warto używać debugowania historycznego?  
 Ustawianie punktów przerwania, aby znaleźć błędy mogą być raczej hit-or-miss affair. Możesz ustawić punkt przerwania w pobliżu miejsca w kodzie gdzie podejrzenie błędu można, a następnie uruchom aplikację w debugera i mamy nadzieję, że odsyłania punkt przerwania, naciśnij klawisz i że to miejsce, gdzie przerywa wykonywanie może ujawnić źródła błędu. W przeciwnym razie trzeba będzie spróbować ustawić punkt przerwania w innym miejscu w kodzie i ponownie uruchom debuger, wykonywanie do kroków testu wiele razy, aż znajdziesz problem.  
  
 ![ustawienie punktu przerwania](../debugger/media/breakpointprocesa.png "BreakpointProcesa")  
  
 Możesz użyć IntelliTrace i debugowanie historyczne są przenoszone wokół w aplikacji i sprawdzić jego stan (stos wywołań i zmienne lokalne) bez konieczności ustawiania punktów przerwania, uruchom ponownie debugowanie i powtórz kroki testu. To może zaoszczędzić dużo czasu, szczególnie gdy usterka znajduje się w scenariuszu testu, który zajmuje dużo czasu, aby wykonać.  
  
## <a name="how-do-i-start-using-historical-debugging"></a>Jak uruchomić debugowania historycznego  
 Funkcja IntelliTrace jest domyślnie włączone. To wszystko, co należy zrobić, zdecyduj, które zdarzenia i wywołania funkcji są przydatne, czy chcesz wyświetlić migawki z pełnym stanem aplikacji. Aby uzyskać więcej informacji na temat definiowania mają być wyszukiwane, zobacz [funkcji IntelliTrace](../debugger/intellitrace-features.md).  

 - Aby wyświetlić migawki za pomocą debugowania historycznego, zobacz [Sprawdź poprzednie Stany aplikacji za pomocą funkcji IntelliTrace](../debugger/view-historical-application-state.md)
 - Aby dowiedzieć się, jak sprawdzanie zmiennych i przechodzenie do kodu, zobacz [sprawdzanie aplikacji za pomocą debugowania historycznego](../debugger/historical-debugging-inspect-app.md)
 - Aby dowiedzieć się więcej na temat debugowania z uwzględnieniem zdarzeń IntelliTrace, zobacz [Instruktaż: przy użyciu funkcji IntelliTrace](../debugger/walkthrough-using-intellitrace.md).