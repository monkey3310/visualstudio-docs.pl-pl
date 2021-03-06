---
title: Widok drzewa wywołań - dane Kontencji | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Call Tree view
ms.assetid: 9bd4bde2-2ca3-446c-9ccc-7421522e03ae
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 40e28eb246b2c4611a15dc4ce2cf6b1b02dd0100
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34263184"
---
# <a name="call-tree-view---contention-data"></a>Widok drzewa wywołań - dane kontencji
Widok drzewa wywołań Wyświetla ścieżek wykonywania funkcji, które zostały przechodzić w profilowanych aplikacji. Korzeń drzewa jest punktem wejścia do aplikacji lub składnika. Każdy węzeł funkcja zawiera wszystkie funkcje, które mu, ile razy funkcja została zablokowana i ilość czasu, która funkcja została zablokowana, ponieważ został on Spierających zasobu z innymi wątków i procesów.  
  
 Wartości w widoku drzewa wywołań są dla wystąpień funkcji, które zostały wywołane przez funkcję nadrzędnego w drzewie wywołań. Wartości procentowe są obliczane przez porównanie wartości wystąpienia funkcji łączna liczba rywalizacji w przebiegu profilowania.  
  
## <a name="highlight-the-execution-hot-path"></a>Wyróżnij ścieżkę aktywną wykonywania  
 Widok drzewa wywołań można rozwijać i wyróżnij ścieżkę wykonywania procesu lub funkcja, która utworzyła większości rywalizacji.  
  
-   Aby wyświetlić najbardziej aktywne ścieżki, kliknij prawym przyciskiem myszy proces lub funkcji, a następnie kliknij **rozwiń aktywnej ścieżki**.  
  
## <a name="set-the-call-tree-root-node"></a>Ustaw węzła głównego drzewa wywołań  
 Każdy proces w przebiegu profilowania jest wyświetlany jako węzła głównego. Aby ustawić węzeł początkowy widok drzewa wywołań, kliknij prawym przyciskiem myszy węzeł, który chcesz ustawić jako węzeł początkowy, a następnie kliknij przycisk **ustawić głównego**.  
  
 Po ustawieniu węzła głównego, usuniesz wszystkie wpisy z widoku, z wyjątkiem poddrzewo wybranego węzła. Aby zresetować węzła głównego z powrotem do pierwotnego węzła, kliknij prawym przyciskiem myszy w widoku drzewa wywołań, a następnie kliknij **zresetować głównego**.  
  
|Kolumny|Opis|  
|------------|-----------------|  
|**Wyłączny czasu blokowania**|Czas wykonywania w przebiegu profilowania wystąpień tej funkcji w tej ścieżce wykonanie został zablokowany. Czas nie obejmuje czas blokowania funkcji podrzędne, które zostały wywołane przez funkcję.|  
|**% Wyłącznego czasu blokowania**|Procent wszystkich czas blokowania w przebiegu profilowania, który był własny czas zablokowanych dla tej funkcji w tej ścieżce wykonywania.|  
|**Wyłączny rywalizacji**|Liczba rywalizacji, które wystąpiły w wystąpieniach tej funkcji w tej ścieżce wykonywania. Liczba nie ma rywalizacji wywołanych przez funkcję funkcji podrzędnych.|  
|**% Wyłącznego rywalizacji**|Procent wszystkich rywalizacji w przebiegu profilowania, które były wyłącznego rywalizacji wystąpień tej funkcji, które zostały wywołane przez funkcję nadrzędnego w drzewie wywołań.|  
|**Adres funkcji**|Adres funkcji.|  
|**Nazwa funkcji**|Pełna nazwa funkcji.|  
|**Całkowity czas blokowania**|Łączny czas wykonywania w przebiegu profilowania wystąpień tej funkcji w tej ścieżce wykonanie został zablokowany. Czas obejmuje czas blokowania wywołanych przez funkcję funkcji podrzędnych.|  
|**Całkowity czas blokowania %**|Procent wszystkich czas blokowania w profilowania uruchamiania, która była całkowity czas blokowania wystąpień tej funkcji w tej ścieżce wykonywania.|  
|**Wraz z wartościami granicznymi rywalizacji**|Całkowita liczba rywalizacji, dla których blokowany dostęp do wystąpień tej funkcji w tej ścieżce wykonywania. Liczba obejmuje rywalizacji wywołanych przez funkcję funkcji podrzędnych.|  
|**% Rywalizacji włącznie**|Wartość procentowa rywalizacji wszystkie, w którym profilowania były włącznie rywalizacji wystąpień tej funkcji w tej ścieżce wykonywania.|  
|**poziom**|Poziom w drzewie wywołań funkcji. Tylko w raportach wiersza polecenia VSReport. Aby uzyskać więcej informacji, zobacz w [VSPerfReport](../profiling/vsperfreport.md).|  
|**Numer wiersza — funkcja**|Numer wiersza początku tej funkcji w pliku źródłowym.|  
|**Nazwa modułu**|Nazwa modułu zawiera funkcję.|  
|**Ścieżka modułu**|Ścieżka moduł, który zawiera funkcję.|  
|**Identyfikator procesu**|Identyfikator PID profilowania Uruchom proces.|  
|**Nazwa procesu**|Nazwa procesu.|  
|**Plik źródłowy**|Plik źródłowy, który zawiera definicję dla tej funkcji.|  
  
## <a name="see-also"></a>Zobacz także  
 [Porady: Dostosowywanie kolumn widoku raportu](../profiling/how-to-customize-report-view-columns.md)   
 [Widok drzewa wywołań](../profiling/call-tree-view.md)   
 [Widok drzewa wywołań - Instrumentacja](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [Drzewie wywołań view - próbkowanie](../profiling/call-tree-view-dotnet-memory-sampling-data.md)   
 [Widok drzewa wywołań](../profiling/call-tree-view-instrumentation-data.md)   
 [Widok drzewa wywołań](../profiling/call-tree-view-sampling-data.md)