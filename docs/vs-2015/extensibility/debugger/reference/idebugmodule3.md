---
title: IDebugModule3 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugModule3
helpviewer_keywords:
- IDebugModule3 interface
ms.assetid: 44f8e96e-9c59-4ffc-9a08-9c908a0e4de7
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 10247bf1390d54ee659403c51eba8c98edfe1c69
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682597"
---
# <a name="idebugmodule3"></a>IDebugModule3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [IDebugModule3](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmodule3).  
  
Ten interfejs reprezentuje moduł, który obsługuje alternatywne lokalizacje symboli i JustMyCode stanów.  
  
## <a name="syntax"></a>Składnia  
  
```  
IDebugModule3 : IDebugModule2  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 Aparat debugowania (DE) implementuje ten interfejs obsługuje alternatywne lokalizacje symboli i współpracować ze Stanami JustMyCode (zobacz [słownik debugera w usłudze Visual Studio](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md) definicji "JustMyCode").  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 Wywołanie [getsymbolsearchinfo —](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md) zwraca ten interfejs. Wysyła DE [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) współpracować w celu Menedżer debugowania sesji (SDM) przy użyciu [zdarzeń](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) metody. Ponadto po wywołaniu [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) na [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) interfejsu zwraca ten interfejs.  
  
## <a name="methods-in-vtable-order"></a>Metody w Vtable kolejności  
 Oprócz metod na [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) interfejsu, ten interfejs implementuje następujące metody:  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)|Zwraca listę ścieżek wyszukiwane symboli i wyniki wyszukiwania poszczególnych ścieżek.|  
|[LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)|Ładuje i inicjuje symbole dla bieżącego modułu.|  
|[IsUserCode](../../../extensibility/debugger/reference/idebugmodule3-isusercode.md)|Zwraca flagę, określania, czy moduł reprezentuje kod użytkownika.|  
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugmodule3-setjustmycodestate.md)|Określa, czy moduł należy uznać za kod użytkownika lub nie.|  
  
## <a name="remarks"></a>Uwagi  
 Program Visual Studio jest typowej tego interfejsu.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy podstawowe](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)   
 [Getsymbolsearchinfo —](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)

