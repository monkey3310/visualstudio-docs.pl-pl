---
title: Znaczniki zakresu | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.markers.span
ms.assetid: 736b7765-9c71-44d7-85e5-79787d13d91c
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74919ddaa31bc7857a7bb9c30264830757f336b0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="span-markers"></a>Znaczniki zakresu
Znacznik zakresu reprezentuje fazę opisową aplikacji. Na przykład można użyć zakres do reprezentowania przedział czasu, w którym element roboczy w szczególności jest przetwarzana. Długość jego reprezentuje czas trwania fazy odpowiedniej aplikacji. Ta ilustracja przedstawia zakres w Concurrency Visualizer:  
  
 ![Znacznik zakresu na Concurrency Visualizer](../profiling/media/cvmarkerspan.png "CVMarkerSpan")  
Znacznik zakresu na Concurrency Visualizer  
  
## <a name="span-category"></a>Kategoria zakresu  
 Znacznik zakresu jest wyświetlany w jednym z pięciu różnych kolorach, w zależności od jego kategorii. Kolory są powtarzane, jeśli istnieje więcej niż pięć kategorii. Kategoria może być liczbą całkowitą. Na ilustracji przedstawiono pięć możliwych kolorów:  
  
 ![Pięć zakresów w różnych kategoriach](../profiling/media/cvmarkerspancategory.png "CVMarkerSpanCategory")  
Kolory pierwsze pięć kategorii zakresu  
  
## <a name="span-aggregation-markers"></a>Agregacja znaczniki zakresu  
 Czasami zakresu znaczników występują tak blisko siebie w Concurrency Visualizer, że nie można ich indywidualnie wstawiany. Jeśli ten problem wystąpi, szary *znacznika agregacji zakresu* czy reprezentuje podstawowej zakresy są widoczne. Po wskaźnika myszy na ikony, jest wyświetlana etykieta liczba podstawowej zakresy, które są przedstawiane. Aby wyświetlić zakresy, powiększania. Powiększ do końca, nadal jest wyświetlany znacznik agregacji zakresu można wyświetlić podstawowy znaczniki zakresu w [raport dotyczący znaczników](../profiling/markers-report.md). Na ilustracji przedstawiono znacznika zakresu agregacji:  
  
 ![Wartość zagregowana span znacznik Concurrency Visualizer](../profiling/media/cvmarkerspanaggregate.png "CVMarkerSpanAggregate")  
Znacznik span agregacji  
  
## <a name="see-also"></a>Zobacz też  
 [Znaczniki CONCURRENCY Visualizer](../profiling/concurrency-visualizer-markers.md)   
 [Wizualizatora współbieżności SDK](../profiling/concurrency-visualizer-sdk.md)