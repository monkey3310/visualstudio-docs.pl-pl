---
title: Stałe węzły | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c798a50-a2d7-459b-9879-ad4ad8290c9b
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: eeeff91d6c30774d89544ab7cfd5c1f5db759620
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680058"
---
# <a name="constant-nodes"></a>Stałe węzły
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [stałe węzły](https://docs.microsoft.com/visualstudio/designers/constant-nodes).  
  
W projektancie programu do cieniowania stałe węzły przedstawiają wartości literałów i interpolowane wierzchołka atrybutów w obliczeniach cieniowania pikseli. Ponieważ wierzchołek atrybuty są interpolowane — i dlatego są różne dla każdego piksela — każde wystąpienie programu do cieniowania pikseli odbiera nieco innej stałej. Dzięki temu każdego piksela unikatowego wyglądu.  
  
## <a name="vertex-attribute-interpolation"></a>Interpolacja atrybut wierzchołka  
 Obraz scenę 3-D w grach i aplikacjach odbywa się przy ze sobą matematycznie Przekształcanie liczba obiektów — które są definiowane przez wierzchołki, atrybuty wierzchołka i definicje pierwotnych — do wyświetlanymi na ekranie pikseli. Wszystkie informacje, które są wymagane, aby dać jej unikatowego wyglądu piksel jest dostarczany za pomocą atrybutów wierzchołka, które są ze sobą mieszane zgodnie z piksela odległości między elementami do różnych wierzchołków, które tworzą jego *pierwotnych*. Podstawowy jest elementem renderowania podstawowego; oznacza to prostą kształtu, takie jak punkt, linii lub trójkąt. Piksel, który jest bardzo zbliżona do co najmniej jeden wierzchołki otrzymuje stałe, które są niemal identyczne, z tego wierzchołka, ale pikseli, który ma mają równe odstępy między wszystkie wierzchołki podstawowy otrzymuje stałe, które są średnią te wierzchołki. W programowaniu grafiki, stałe, które odbierają pikseli są określane jako *interpolowane*. Dostarcza dane stałej pikseli w ten sposób daje bardzo dobra jakość wizualną i jednocześnie pozwala zmniejszyć wymagania dotyczące zużycia i przepustowość pamięci.  
  
 Mimo że każde wystąpienie programu do cieniowania pikseli odbiera tylko jeden zestaw wartości stałych i nie można zmienić tych wartości, do cieniowania pikseli różnych wystąpień odbierać różne zestawy danych stała. Ten projekt umożliwia program do cieniowania do generowania danych wyjściowych innego koloru dla każdego piksela podstawowego.  
  
## <a name="constant-node-reference"></a>Stałe węzeł odniesienia  
  
|Węzeł|Szczegóły|Właściwości|  
|----------|-------------|----------------|  
|**Wektor kamery**|Wektor prowadzący od bieżącego piksela do kamery w przestrzeni świata.<br /><br /> Służy to do obliczenia odbić w przestrzeni świata.<br /><br /> **Output**<br /><br /> `Output`: `float3`<br /> Wektor od bieżącego piksela do kamery.|Brak|  
|**Stała koloru**|Wartość stała koloru.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Wartość koloru.|**Output**<br /> Wartość koloru.|  
|**Stałe**|Stała wartość skalarną.<br /><br /> **Output**<br /><br /> `Output`: `float`<br /> Wartość skalarna.|**Output**<br /> Wartość skalarna.|  
|**Stała 2W**|Stała dwiema składowymi.<br /><br /> **Output**<br /><br /> `Output`: `float2`<br /> Wartość wektorowa.|**Output**<br /> Wartość wektorowa.|  
|**Stała 3W**|Stała trzema składowymi.<br /><br /> **Output**<br /><br /> `Output`: `float3`<br /> Wartość wektorowa.|**Output**<br /> Wartość wektorowa.|  
|**Stała 4W**|Stała czterema składowymi.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Wartość koloru.|**Output**<br /> Wartość wektorowa.|  
|**Pozycja znormalizowana**|Pozycja bieżącego piksela wyrażona w urządzenia znormalizowanych współrzędnych.<br /><br /> Współrzędne x i współrzędne y mają wartości z zakresu [-1, 1], Współrzędna z ma wartość z zakresu [0, 1], i w składnik zawiera wartość głębię punktów w przestrzeni widoku; w nie jest znormalizowana.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Pozycja bieżącego piksela.|Brak|  
|**Kolor punktu**|Kolor rozpraszania bieżącego piksela jest kombinacją materiału rozpraszania koloru i wierzchołka atrybutów koloru.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Kolor rozpraszania bieżącego piksela.|Brak|  
|**Głębokość punktu**|Głębokość bieżącego piksela w przestrzeni widoku.<br /><br /> **Output**<br /><br /> `Output`: `float`<br /> Głębokość bieżącego piksela.|Brak|  
|**Znormalizowana głębokość punktu**|Głębokość bieżącego piksela wyrażona w urządzenia znormalizowanych współrzędnych.<br /><br /> Wynik zawiera wartość z zakresu [0, 1].<br /><br /> **Output**<br /><br /> `Output`: `float`<br /> Głębokość bieżącego piksela.|Brak|  
|**Pozycja ekranu**|Pozycja bieżącego piksela wyrażona w współrzędne ekranu.<br /><br /> Współrzędne ekranu zależą od bieżącego okienka ekranu. X i y składniki zawierają współrzędne ekranu, składnik z zawiera głębokość znormalizowane do zakresu [0, 1], a w składnik zawiera głębokość w przestrzeni widoku.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Pozycja bieżącego piksela.|Brak|  
|**Normalna powierzchni**|Normalna powierzchni bieżącego piksela w przestrzeni obiektów.<br /><br /> Służy to do obliczenia udziału oświetlenia i odbić w przestrzeni obiektów.<br /><br /> **Output**<br /><br /> `Output`: `float3`<br /> Normalna powierzchni bieżącego piksela.|Brak|  
|**Wektor kamery przestrzeni stycznej**|Wektor prowadzący od bieżącego piksela do kamery w przestrzeni stycznej.<br /><br /> Służy to do obliczenia odbić w przestrzeni stycznej.<br /><br /> **Output**<br /><br /> `Output`: `float3`<br /> Wektor od bieżącego piksela do kamery.|Brak|  
|**Kierunek światła przestrzeni stycznej**|Wektor definiujący kierunek, w którym światła jest rzutowanie ze źródła światła w przestrzeni stycznej bieżącego piksela.<br /><br /> Służy to do obliczenia udziału oświetlenia i odblasków w przestrzeni stycznej.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float3`<br /> Wektor od bieżącego piksela do źródła światła.|Brak|  
|**Normalna świata**|Normalna powierzchni bieżącego piksela w przestrzeni świata.<br /><br /> Służy to do obliczenia udziału oświetlenia i odbić w przestrzeni świata.<br /><br /> **Output**<br /><br /> `Output`: `float3`<br /> Normalna powierzchni bieżącego piksela.|Brak|  
|**Pozycja świata**|Pozycja bieżącego piksela w przestrzeni świata.<br /><br /> **Output**<br /><br /> `Output`: `float4`<br /> Pozycja bieżącego piksela.|Brak|



