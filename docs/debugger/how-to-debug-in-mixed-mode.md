---
title: 'Porady: debugowanie w trybie mieszanym | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 06/19/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 834288c063a4bc0d830f121dcb8589b509c61bcf
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256165"
---
# <a name="how-to-debug-in-mixed-mode"></a>Porady: debugowanie w trybie mieszanym
Poniższe procedury zawierają opis do debugowania kodu zarządzane i natywne, tzw. debugowanie w trybie mieszanym. Istnieją dwa scenariusze w ten sposób, w zależności od tego, czy biblioteka DLL lub aplikacji są zapisywane w kodzie natywnym:  
  
-   Aplikacja wywołująca, która wywołuje biblioteki DLL są zapisywane w kodzie natywnym. W takim przypadku biblioteki DLL jest zarządzana i zarządzane i natywne debugery musi być włączona zarówno debugowania. Można to sprawdzić  **\<projektu > strony właściwości** okno dialogowe. Jak to zrobić, zależy od tego, czy uruchomić debugowanie z projektu DLL lub wywołującym projekt aplikacji.  
  
-   Aplikacja wywołująca, która wywołuje biblioteki DLL są zapisywane w kodzie zarządzanym i biblioteki DLL są zapisywane w kodzie natywnym. Samouczek, który przeprowadzi Cię przez te kroki, zobacz [debugowania kodu zarządzanego i natywnego](../debugger/how-to-debug-managed-and-native-code.md).
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić ustawienia, wybierz **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](../ide/personalizing-the-visual-studio-ide.md).

Jeśli nie masz dostępu do projektu dla wywołania aplikacji można debugować biblioteki DLL z projektu DLL. Aby uzyskać więcej informacji, zobacz [porady: debugowanie z projektu DLL](../debugger/how-to-debug-from-a-dll-project.md). Nie trzeba używać trybu mieszanego do debugowania tylko projektu biblioteki DLL.
  
### <a name="to-enable-mixed-mode-debugging-c-calling-app"></a>Aby włączyć debugowanie w trybie mieszanym (wywołanie aplikacji C++)  
  
1.  W **Eksploratora rozwiązań**, wybierz natywnego projektu.
  
2.  Na **widoku** menu, kliknij przycisk **strony właściwości**.
  
3.  W  **\<projektu > strony właściwości** okna dialogowego rozwiń **właściwości konfiguracji** węzeł, a następnie wybierz **debugowanie**.  
  
4.  Ustaw **debugera typu** do **mieszane** lub **automatycznie**.

    ![Włącz debugowanie w trybie mieszanym](../debugger/media/dbg-mixed-mode-from-native.png "włączyć debugowanie w trybie mieszanym")

### <a name="to-enable-mixed-mode-debugging-c-or-vb-calling-app"></a>Aby włączyć debugowanie w trybie mieszanym (C# lub VB. wywoływania aplikacji)  
  
1.  W **Eksploratora rozwiązań**, wybierz zarządzany projekt.  
  
2.  Na **widoku** menu, kliknij przycisk **strony właściwości**.  
  
3.  W  **\<projektu > strony właściwości** okno dialogowe, wybierz opcję **debugowania** , a następnie wybierz **Włącz debugowanie kodu natywnego**

    ![Włącz debugowanie kodu natywnego](../debugger/media/dbg-mixed-mode-from-csharp.png "Włącz debugowanie kodu natywnego")
  
## <a name="see-also"></a>Zobacz też  
 [Porady: debugowanie z projektu DLL](../debugger/how-to-debug-from-a-dll-project.md)