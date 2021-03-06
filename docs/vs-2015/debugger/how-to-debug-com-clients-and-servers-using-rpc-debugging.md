---
title: 'Porady: debugowanie klientów i serwerów za pomocą debugowania RPC COM | Dokumentacja firmy Microsoft'
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
- vs.debug.com
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- RPC (Remote Procedure Call), debugging COM clients and servers
- COM, debugging
- RPC (Remote Procedure Call)
- RPC (Remote Procedure Call), debugging
- COM clients, debugging
- COM servers, debugging
- out-of-process remote procedure call debugging
- remote debugging, RPC (Remote Procedure Call)
- in-process remote procedure call debugging
ms.assetid: 3e8526c8-43b5-4b87-8e0d-b22c24f0a3ea
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b64c01f502dbe4194561776f121e21475d61d43
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677779"
---
# <a name="how-to-debug-com-clients-and-servers-using-rpc-debugging"></a>Porady: debugowanie klientów i serwerów COM za pomocą debugowania RPC
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [porady: debugowanie klientów i COM serwerów za pomocą debugowania RPC](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-com-clients-and-servers-using-rpc-debugging).  
  
Debugowanie zdalnego wywołania (procedur RPC) procedury można użyć do debugowania aplikacji typu klient/serwer COM. Konieczne jest włączenie debugowania z niej korzystać RPC. Z włączonym debugowaniem RPC, po kroku do wywołania serwera z klienta, debuger dołącza do serwera i umożliwia debugowanie kodu. Gdy debuger jest dołączony, mogą używać wszystkich funkcji debugera, procesy klienta i serwera.  
  
### <a name="to-enable-rpc-debugging"></a>Aby włączyć debugowanie RPC  
  
1.  Na **narzędzia** menu, kliknij przycisk **opcje**.  
  
2.  W **opcje** okno dialogowe, kliknij przycisk **debugowanie** folderu.  
  
3.  Kliknij przycisk **natywnych** strony.  
  
4.  Wybierz **debugowania RPC** pole wyboru.  
  
    > [!NOTE]
    >  Aby debugować wywołania RPC, musi mieć uprawnienia administratora lub użytkownik zaawansowany.  
  
    > [!NOTE]
    >  Przechodzenie do serwera zdalnego z systemem Microsoft Windows Vista RPC będzie działać tylko wtedy, gdy debuger natywny jest dołączony do serwera zdalnego. W przeciwnym razie wywołania RPC zakończy się niepowodzeniem bez komunikatu o błędzie. W przeciwnym razie wywołania RPC zostanie ukończone, ale wkroczenia do wywołania RPC nie będzie działać.  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie kontenera i serwera COM](../debugger/com-server-and-container-debugging.md)   
 [Debugowanie w programie Visual Studio](../debugger/debugging-in-visual-studio.md)



