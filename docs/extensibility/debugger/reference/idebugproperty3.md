---
title: IDebugProperty3 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty3
helpviewer_keywords:
- IDebugProperty3 interface
ms.assetid: 8f9be68d-4490-4eca-8f6b-8a10ed77e226
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3ae93a9f88bdee3c4648f803eaf174567fe771c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122785"
---
# <a name="idebugproperty3"></a>IDebugProperty3
Ten interfejs obsługuje:  
  
-   Pobieranie długi ciąg skojarzony z właściwością.  
  
-   Kojarzenie Unikatowy identyfikator razem z właściwością.  
  
-   Pobieranie listy przeglądarek niestandardowe właściwości.  
  
-   Ustawienie wartości właściwości z możliwością zgłoszonych błędów, wynikowy  
  
## <a name="syntax"></a>Składnia  
  
```  
IDebugProperty3 : IDebugProperty2  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 Aparat debugowania (DE) implementuje ten interfejs dla tego samego obiektu, który implementuje [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) do zapewnienia obsługi długich ciągów, identyfikatory właściwości i niestandardowych przeglądarki.  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 Wywołanie [QueryInterface](/cpp/atl/queryinterface) na `IDebugProperty2` interfejs do uzyskania tego interfejsu.  
  
## <a name="methods-in-vtable-order"></a>Metody w kolejności Vtable  
 Oprócz dziedziczone z metody `IDebugProperty2`, `IDebugProperty3` interfejsu udostępnia następujące metody.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)|Zwraca długość ciągu skojarzonego z właściwością.|  
|[GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md)|Zwraca ciąg w buforze dostarczone przez użytkownika.|  
|[CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)|Tworzy unikatowy identyfikator dla tej właściwości.|  
|[DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)|Niszczy Unikatowy identyfikator dla tej właściwości.|  
|[GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)|Zwraca liczbę niestandardowych przeglądarek, które tej właściwości można wyświetlić w programie.|  
|[GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)|Zwraca listę przeglądarek niestandardowych, które tej właściwości można wyświetlić w programie.|  
|[SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)|Ustawia wartość tej właściwości, zwracając komunikat o błędzie, jeśli niczego poszło źle.|  
  
## <a name="remarks"></a>Uwagi  
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) jest preferowany sposób Menedżera sesji debugowania (SDM), aby ustawić wartości właściwości.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy Core](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)