---
title: IDebugPort2 | Microsoft Docs
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
- IDebugPort2
helpviewer_keywords:
- IDebugPort2 interface
ms.assetid: 8fd87f05-a950-4d14-b925-98be29d4facc
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 74e0bb9b53e955372f33c2e27f280f7bf5b87f2e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692388"
---
# <a name="idebugport2"></a>IDebugPort2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [IDebugPort2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugport2).  
  
Ten interfejs reprezentuje port debugowania na komputerze.  
  
## <a name="syntax"></a>Składnia  
  
```  
IDebugPort2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 Dostawcy niestandardowego portu implementuje ten interfejs do reprezentowania port debugowania na komputerze.  
  
 Jeśli port obsługuje wysyłanie zdarzeń do portu, musi implementować też <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> obsługiwany przez interfejs <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> interfejs, który z kolei udostępnia [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) interfejsu.  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 Wywołania [GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md) lub [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) zwraca ten interfejs reprezentujący żądanym porcie.  
  
## <a name="methods-in-vtable-order"></a>Metody w Vtable kolejności  
 W poniższej tabeli przedstawiono metody `IDebugPort2`.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugport2-getportname.md)|Zwraca nazwę portu.|  
|[GetPortId](../../../extensibility/debugger/reference/idebugport2-getportid.md)|Zwraca identyfikator portu.|  
|[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)|Zwraca żądanie użyty do utworzenia portu (jeśli jest dostępny).|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)|Zwraca dostawcy portu dla tego portu.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)|Zwraca interfejs do procesu, który został podany identyfikator procesu.|  
|[Enumprocesses —](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)|Wylicza wszystkie procesy, które są uruchomione na porcie.|  
  
## <a name="remarks"></a>Uwagi  
 Port lokalny zapewnia dostęp do wszystkich procesów i programy uruchomione na komputerze lokalnym. Inne porty może reprezentować połączenia kabel szeregowy do urządzenia z systemem Windows CE lub połączenie sieciowe z komputerem bez modelu DCOM. `IDebugPort2` Interfejs jest używany, aby znaleźć nazwy i identyfikatora portu wyliczyć wszystkie procesy uruchomione na porcie i zapewnić urządzeń uruchomienie i zakończenie procesów na porcie.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy podstawowe](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)

