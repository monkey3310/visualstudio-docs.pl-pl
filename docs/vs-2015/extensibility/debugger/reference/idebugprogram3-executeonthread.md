---
title: IDebugProgram3::ExecuteOnThread | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugProgram3::ExecuteOnThread
ms.assetid: 2f5211e3-7a3f-47bf-9595-dfc8b4895d0d
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8ad46418897f4cdd2521209dd6643362e81bfcb6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685238"
---
# <a name="idebugprogram3executeonthread"></a>IDebugProgram3::ExecuteOnThread
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [IDebugProgram3::ExecuteOnThread](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram3-executeonthread).  
  
Wykonuje program debugera. Wątek jest zwracany do przedstawienia informacji debugera, na który wątek użytkownika jest wyświetlana podczas wykonywania programu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT ExecuteOnThread(  
   [in] IDebugThread2* pThread)  
```  
  
```csharp  
int ExecuteOnThread(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) obiektu.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Istnieją trzy różne sposoby wznowić wykonywanie po zatrzymaniu debugera:  
  
-   Wykonaj: Anulowanie wszelkich w poprzednim kroku, a następnie uruchom aż do następnego punktu przerwania i tak dalej.  
  
-   Krok Anulować stary którykolwiek z kroków i uruchamianie aż do zakończenia nowego kroku.  
  
-   Kontynuuj: Uruchom ponownie i pozostawianie aktywnej stare którykolwiek z kroków.  
  
 Wątek jest przekazywany do `ExecuteOnThread` jest przydatne w przypadku podejmowania decyzji, który krok, aby anulować. Jeśli nie znasz wątek systemu wykonaj anuluje wszystkie kroki. Przy zachowaniu wiedzy o wątku wystarczy anulować kroku na aktywnym wątkiem.  
  
## <a name="see-also"></a>Zobacz też  
 [Wykonywanie](../../../extensibility/debugger/reference/idebugprogram2-execute.md)   
 [IDebugProgram3](../../../extensibility/debugger/reference/idebugprogram3.md)

