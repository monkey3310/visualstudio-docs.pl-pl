---
title: Lista wątków polecenie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.listthreads
helpviewer_keywords:
- ListThreads command
- list threads command
- Debug.ListThreads command
ms.assetid: 34b665c0-d46f-4c1a-a066-b678eba5ac54
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cd8e9f96e0f477ba0b83419274d9b2ed0a101195
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696907"
---
# <a name="list-threads-command"></a>Lista wątków — Polecenie
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Lista wątków — polecenie](https://docs.microsoft.com/visualstudio/ide/reference/list-threads-command).  
  
  
Wyświetla listę wątków w bieżącym programem.  
  
## <a name="syntax"></a>Składnia  
  
```  
Debug.ListThreads [index]  
```  
  
## <a name="arguments"></a>Argumenty  
 `index`  
 Opcjonalna. Wybiera wątku za pomocą jego indeksu do bieżącego wątku.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli zostanie określony, `index` argument oznacza wskazany wątek jako bieżącego wątku. Znak gwiazdki (*) jest wyświetlana na liście obok bieżącego wątku.  
  
## <a name="example"></a>Przykład  
  
```  
>Debug.ListThreads   
```  
  
## <a name="see-also"></a>Zobacz też  
 [Lista stosu wywołań — polecenie](../../ide/reference/list-call-stack-command.md)   
 [Lista dezasemblacji — polecenie](../../ide/reference/list-disassembly-command.md)   
 [Visual Studio — polecenia](../../ide/reference/visual-studio-commands.md)   
 [Okno polecenia](../../ide/reference/command-window.md)   
 [Znajdź/Command — pole](../../ide/find-command-box.md)   
 [Visual Studio — aliasy poleceń](../../ide/reference/visual-studio-command-aliases.md)



