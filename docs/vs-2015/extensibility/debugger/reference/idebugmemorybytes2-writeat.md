---
title: IDebugMemoryBytes2::WriteAt | Dokumentacja firmy Microsoft
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
- IDebugMemoryBytes2::WriteAt
helpviewer_keywords:
- IDebugMemoryBytes2::WriteAt method
- WriteAt method
ms.assetid: 61cc3704-47fa-4d9b-aa62-bb4585ac8fb1
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 69d7cfd4b7e9a0598a8240d9392f1835c30bd561
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630080"
---
# <a name="idebugmemorybytes2writeat"></a>IDebugMemoryBytes2::WriteAt
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [IDebugMemoryBytes2::WriteAt](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmemorybytes2-writeat).  
  
Zapisuje określoną liczbę bajtów pamięci, zaczynając od określonego adresu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT WriteAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory  
);  
```  
  
```csharp  
int WriteAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pStartContext`  
 [in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) obiekt, który określa, gdzie rozpoczyna zapis bajtów.  
  
 `dwCount`  
 [in] Liczba bajtów do zapisania.  
  
 `rgbMemory`  
 [in] Bajty do zapisania. Ta tablica zakłada, że co najmniej `dwCount` bajtów.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca `S_FALSE` Jeśli nie wszystkie wartości bajtowe mogłyby być zapisywane lub zwraca kod błędu (zwykle `E_FAIL`).  
  
## <a name="remarks"></a>Uwagi  
 Jeśli adres początkowy nie jest w obrębie okna pamięci, reprezentowane przez ten [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) obiektu występuje nie zapisywania i kod błędu `E_FAIL` zwróceniem — nawet wtedy, gdy kwota do zapisania nakłada się do obszaru pamięci.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)

