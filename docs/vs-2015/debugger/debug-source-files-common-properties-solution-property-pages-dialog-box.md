---
title: Okno dialogowe strony właściwości rozwiązania źródła plików, typowe właściwości, debugowanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.options.FindSource
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- SQL
- VB
- CSharp
- C++
helpviewer_keywords:
- Debug Source Files property page
- debugging [Visual Studio], specifying source and symbol files
- source files, specifying in debugger
- debugger, source files
ms.assetid: 0af11464-eeb1-4d0b-87a6-0cc96779afb1
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b94306c44b8a19d1fbf924fe361d317dd911110b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630488"
---
# <a name="debug-source-files-common-properties-solution-property-pages-dialog-box"></a>Debugowanie plików źródłowych, typowe właściwości, strony właściwości rozwiązania — Okno dialogowe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [debugowanie plików źródłowych, typowe właściwości — okno dialogowe strony właściwości rozwiązania](https://docs.microsoft.com/visualstudio/debugger/debug-source-files-common-properties-solution-property-pages-dialog-box).  
  
Ta strona właściwości określa, gdzie debuger będzie szukać plików źródłowych, podczas debugowania rozwiązania.  
  
 Aby uzyskać dostęp do **Debuguj pliki źródłowe** strony właściwości, kliknij prawym przyciskiem myszy w rozwiązaniu w **Eksploratora rozwiązań** i wybierz **właściwości** z menu skrótów. Rozwiń **wspólne właściwości** folder, a następnie kliknij przycisk **Debuguj pliki źródłowe** strony.  
  
 **Katalogi zawierające kod źródłowy**  
 Zawiera listę katalogów, w których debuger wyszukuje pliki źródłowe podczas debugowania rozwiązania. Przeszukiwane są również podkatalogi w określonych katalogach.  
  
 **Wyglądają dla tych plików źródłowych**  
 Wprowadź nazwy plików, które nie chcesz, aby debuger do odczytu. Jeśli debuger wykryje jeden z tych plików w jednym z katalogów wymienione powyżej, zignoruje go. Jeśli **Znajdź źródło** okno dialogowe funkcjonuje podczas debugowania, a następnie kliknij **anulować**, plik wyszukiwany pobiera dodana do tej listy, aby debuger nie będzie kontynuowane wyszukiwanie dla tego pliku.  
  
## <a name="see-also"></a>Zobacz też  
 [Zabezpieczenia debugera](../debugger/debugger-security.md)   
 [Ustawienia debugera i przygotowanie](../debugger/debugger-settings-and-preparation.md)



