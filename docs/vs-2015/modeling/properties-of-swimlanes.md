---
title: Właściwości torów | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.swimlane
helpviewer_keywords:
- Domain-Specific Language, swimlane
ms.assetid: 47edbc2d-09e4-48ac-b4d1-5268a06a27e6
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: dd274d1de99ab4a9dac6dd6c045ef6d313fe9bb7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680933"
---
# <a name="properties-of-swimlanes"></a>Właściwości torów
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [właściwości torów](https://docs.microsoft.com/visualstudio/modeling/properties-of-swimlanes).  
  
Można dodać ścieżek do diagramu. Tory podzielić diagramu obszarów pionowych lub poziomych. Można zdefiniować inne kształty, który będzie wyświetlany w ścieżek. Aby uzyskać więcej informacji, zobacz [sposób definiowania języka specyficznego dla domeny](../modeling/how-to-define-a-domain-specific-language.md). Aby uzyskać więcej informacji o tym, jak korzystać z tych właściwości, zobacz [dostosowywanie i rozszerzanie języka specyficznego dla domeny](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Torów mają właściwości, które są wymienione w poniższej tabeli.  
  
|Właściwość|Opis|Domyślny|  
|--------------|-----------------|-------------|  
|Kolor wypełnienia treści|Kolor wypełnienia dla treści toru.|Biały|  
|Kolor wypełnienia nagłówka|Kolor wypełnienia dla nagłówka toru.|DarkGray|  
|Kolor separatora|Kolor linii separatora.|LightGray|  
|Styl linii separatora|Styl linii separatora (`Solid`, `Dash`, `Dot`, `DashDot`, `DashDotDot`, lub `Custom`).|`Dash`|  
|Szerokość separatora|Grubość linii separatora (w calach).|0.03125|  
|Kolor tekstu|Kolor, który jest używany dla dekoratorów tekstu, które są skojarzone z tego toru.|Czarny|  
|Modyfikator dostępu|Poziom dostępu klasy (`public` lub `internal`).|Public|  
|Atrybuty niestandardowe|Służy do dodawania atrybutów do klasy kod, który jest generowany na podstawie tego toru.|\<Brak >|  
|Generuje Double pochodne|Jeśli `True`, zostaną wygenerowane klasy podstawowej i klasy częściowej (obsługuje dostosowywania przy użyciu zastąpień). Aby uzyskać więcej informacji, zobacz [zastępowanie i rozszerzanie wygenerowanych klas](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Ma konstruktora niestandardowego|Jeśli `True`, konstruktora niestandardowego, które będą dostępne w kodzie źródłowym. Aby uzyskać więcej informacji, zobacz [zastępowanie i rozszerzanie wygenerowanych klas](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Modyfikator dziedziczenia|Opisuje typ dziedziczenia klasy kodu źródłowego, która jest generowany na podstawie tor (`none`, `abstract` lub `sealed`).|brak|  
|Tor podstawowy|Klasa bazowa tego toru.|(Brak)|  
|Nazwa|Nazwa tego toru.|Bieżąca nazwa|  
|Przestrzeń nazw|Przestrzeń nazw, która jest połączona z tego toru.|Bieżąca przestrzeń nazw|  
|Typ etykietki narzędzia|Jak jest zdefiniowany etykietki narzędzia (`fixed`, `variable`, lub `none`). Jeśli `fixed`, następnie wartość `Fixed Tooltip Text` właściwość jest używana; jeśli `variable`, a następnie etykietki narzędzia jest definiowana w kodzie niestandardowym.|\<Brak >|  
|Uwagi|Uwagi informacyjne, które są skojarzone z tego toru.|\<Brak >|  
|Wyrównanie|Wyrównanie w poziomie lub pionie.|W pionie|  
|Początkowa wysokość|Początkowa wysokość tego toru, w calach. Dotyczy tylko torów poziomych.|0|  
|Początkowa szerokość|Początkowa szerokość tego toru, w calach. Dotyczy tylko torów pionowych.|0|  
|Opisuje kolor tekstu|Jeśli `True`, użytkownik może ustawić kolor tor w wygenerowanym projektancie. Aby to ustawić, kliknij prawym przyciskiem myszy kształt toru, a następnie kliknij przycisk **Dodaj udostępniane**.|False|  
|Opis|Umożliwia dokumentowanie wygenerowanego projektanta.|\<Brak >|  
|Nazwa wyświetlana|Nazwa, która będzie wyświetlana w wygenerowanym projektancie do odwoływania się do tej klasy toru.|\<Brak >|  
|Stały tekst etykietki narzędzia|Tekst, który jest używany dla ustalonej etykietki narzędzia.|\<Brak >|  
|Słowo kluczowe pomocy|Słowo kluczowe, które jest używane do indeksowania pomocy F1 dla tego toru.|\<Brak >|  
  
## <a name="see-also"></a>Zobacz też  
 [Słownik narzędzi języka specyficznego dla domeny](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



