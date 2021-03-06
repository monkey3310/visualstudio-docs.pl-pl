---
title: Idiastackwalkframe — | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame interface
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c525d2c19f3bc4ab7ea540ac129931583064db01
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628149"
---
# <a name="idiastackwalkframe"></a>IDiaStackWalkFrame
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [idiastackwalkframe —](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkframe).  
  
Utrzymuje kontekst stosu między wywołań [idiaframedata::EXECUTE —](../../debugger/debug-interface-access/idiaframedata-execute.md) metody.  
  
## <a name="syntax"></a>Składnia  
  
```  
IDiaStackWalkFrame : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody w Vtable kolejności  
 W poniższej tabeli przedstawiono metody `IDiaStackWalkFrame`.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[IDiaStackWalkFrame::get_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|Pobiera wartość rejestru.|  
|[IDiaStackWalkFrame::put_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|Ustawia wartość rejestru.|  
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|Odczytuje pamięć z obrazu.|  
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|Wyszukuje ramki określonego stosu, dla najbliższej adres zwrotny funkcji.|  
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|Wyszukuje ramki określonego stosu, dla adres zwrotny po lub w pobliżu podanym adresem.|  
  
## <a name="remarks"></a>Uwagi  
 Ten interfejs jest używany podczas wykonywania programu odczytu i zapisu rejestrów, a także uzyskiwania dostępu do pamięci oraz znaleźć adres zwrotny.  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 Aplikacja kliencka implementuje ten interfejs i przekazanie wystąpienia interfejsu do [idiaframedata::EXECUTE —](../../debugger/debug-interface-access/idiaframedata-execute.md) metody. To samo wystąpienie elementu ten interfejs jest używany wielokrotnie w celu zachowania stanu rejestrów podczas każdego wywołania elementu `execute` metody. `execute` Metoda również używa tego interfejsu do określenia adres zwrotny.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: Dia2.h  
  
 Biblioteka: diaguids.lib  
  
 Biblioteki DLL: msdia80.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy (debugowanie zestaw SDK dostępu do interfejsu)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)



