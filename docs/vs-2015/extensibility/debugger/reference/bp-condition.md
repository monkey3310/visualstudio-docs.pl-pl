---
title: BP_CONDITION | Dokumentacja firmy Microsoft
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
- BP_CONDITION
helpviewer_keywords:
- BP_CONDITION structure
ms.assetid: 407f87a3-2878-429b-8c65-b68feb36622a
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 569588d108de05823a733feef4137d35e1b79693
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680305"
---
# <a name="bpcondition"></a>BP_CONDITION
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [BP_CONDITION](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-condition).  
  
Opisuje warunki, na których jest uruchamiany punkt przerwania.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
typedef struct _BP_CONDITION {   
   IDebugThread2* pThread;  
   BP_COND_STYLE  styleCondition;  
   BSTR           bstrContext;  
   BSTR           bstrCondition;  
   UINT           nRadix;  
} BP_CONDITION;  
```  
  
```csharp  
public struct BP_CONDITION {   
   public IDebugThread2 pThread;  
   public uint          styleCondition;  
   public string        bstrContext;  
   public string        bstrCondition;  
   public uint          nRadix;  
};  
```  
  
## <a name="members"></a>Elementy członkowskie  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) obiekt, który reprezentuje aktywnego wątku dla aplikacji, która zawiera punkt przerwania.  
  
 `styleCondition`  
 Wartość z zakresu od [BP_COND_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md) wyliczenie opisujące styl ten warunek punktu przerwania.  
  
 `bstrContext`  
 Lokalizacja punktu przerwania.  
  
 `bstrCondition`  
 Stan uruchomieniu którego punkt przerwania.  
  
 `nRadix`  
 Podstawy do użycia podczas obliczania wszelkie dane liczbowe.  
  
## <a name="remarks"></a>Uwagi  
 Ta struktura jest elementem członkowskim [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) i [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.  
  
 Ta struktura również jest przekazywany jako parametr do [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md) i [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md) metody.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Struktur i Unii](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [BP_COND_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md)

