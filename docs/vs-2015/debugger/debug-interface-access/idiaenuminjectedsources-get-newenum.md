---
title: Idiaenuminjectedsources::get__newenum — | Dokumentacja firmy Microsoft
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
- IDiaEnumInjectedSources::get__NewEnum method
ms.assetid: f56cdcdb-dc71-43c7-82fe-e2500986f5bc
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a7077a6ec2e00ae8feafd3307b3998491f786b3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630162"
---
# <a name="idiaenuminjectedsourcesgetnewenum"></a>IDiaEnumInjectedSources::get__NewEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [idiaenuminjectedsources::get__newenum —](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenuminjectedsources-get-newenum).  
  
Pobiera <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> wersję tego modułu wyliczającego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out, retval] Zwraca `IUnknown` interfejs, który reprezentuje <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> wersję tego modułu wyliczającego.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="see-also"></a>Zobacz też  
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)



