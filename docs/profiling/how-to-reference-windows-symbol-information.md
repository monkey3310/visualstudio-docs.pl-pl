---
title: "Porady: odwołania informacji o symbolach w systemie Windows | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, symbol servers
- servers, symbol servers
- profiling tools, symbol servers
- symbol servers
ms.assetid: b7c67318-6be2-4b1e-a161-077b1f4a7c30
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 09e17cc1e28ad520f76d60c3411de4803a2b4b96
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-reference-windows-symbol-information"></a>Porady: odwołania do informacji o symbolach w systemie Windows
Visual Studio Profiling Tools pliki symboli (.pdb) są używane do rozpoznawania nazw symbolicznych, takich jak funkcja nazw plików binarnych programu. Można wykonaj następujące kroki, aby automatycznie pobrać i aktualizować pliki .pdb poprawne dla wersji systemu Windows na komputerze lokalnym.  
  
> [!NOTE]
>  To ustawienie nie ma wpływu na istniejące raporty. Tylko raporty utworzone po określaniu serwera symboli będzie miał informacji o symbolach.  
  
 Aby uzyskać więcej informacji, zobacz [Określ symboli (.pdb) i pliki źródłowe](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
### <a name="to-use-the-microsoft-symbol-server"></a>Aby użyć serwera Microsoft symbol server  
  
1.  Utwórz folder zawierający informacje o pliku symboli, takie jak C:\SymbolCache.  
  
2.  Na **narzędzia** menu, kliknij przycisk **opcje**.  
  
     **Opcje** zostanie wyświetlone okno dialogowe.  
  
3.  Rozwiń węzeł **debugowanie** drzewa, a następnie kliknij przycisk **symbole**.  
  
4.  W **symboli (.pdb) lokalizacje**, wybierz pozycję **serwerów symboli firmy Microsoft**  
  
5.  W **pamięci podręcznej symboli z serwera symboli w tym katalogu**, wpisz ścieżkę do folderu, który został utworzony w kroku 1, na przykład:  
  
     **C:\SymbolCache**  
  
     Możesz również kliknąć przycisk wielokropka (**...** ), a następnie wybierz katalog z **przeglądanie w poszukiwaniu folderu** okno dialogowe.  
  
## <a name="see-also"></a>Zobacz też  
 [Konfigurowanie sesji wydajności](../profiling/configuring-performance-sessions.md)   
 [Porady: Serializuj informacje dotyczące symboli](../profiling/how-to-serialize-symbol-information.md)