---
title: IDebugBreakpointRequest2 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBreakpointRequest2
helpviewer_keywords:
- IDebugBreakpointRequest2 interface
ms.assetid: 01ac4013-96f9-4235-b289-f55f9e99558f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 03403a09ea5cd66839bf31fe5c690262fd55f3a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103312"
---
# <a name="idebugbreakpointrequest2"></a>IDebugBreakpointRequest2
Ten interfejs reprezentuje informacje niezbędne do tworzenia i powiązać dowolnego typu punktu przerwania.  
  
## <a name="syntax"></a>Składnia  
  
```  
IDebugBreakpointRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 Menedżer debugowania sesji (SDM) zwykle implementuje ten interfejs.  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 Aparat debugowania (DE) odbiera ten interfejs poprzez wywołanie [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) aby można było utworzyć oczekującym punktem przerwania. Wywołanie [GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md) DE może pobrać tego interfejsu.  
  
## <a name="methods-in-vtable-order"></a>Metody w kolejności Vtable  
 W poniższej tabeli przedstawiono metody `IDebugBreakpointRequest2`.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)|Pobiera typ lokalizacji punktu przerwania tego żądania punktu przerwania.|  
|[GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)|Pobiera informacje o żądanie przerwania, opisujący to żądanie przerwania.|  
  
## <a name="remarks"></a>Uwagi  
 Po program debugowany został załadowany, wywołanie [powiązać](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) wiąże oczekującym punktem przerwania do żądanej lokalizacji w programie.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)   
 [GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)   
 [BIND](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)