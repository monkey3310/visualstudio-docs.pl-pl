---
title: 'CA1501: Unikaj nadmiernego dziedziczenia'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1501
- AvoidExcessiveInheritance
helpviewer_keywords:
- AvoidExcessiveInheritance
- CA1501
ms.assetid: 9e934746-1a4d-492a-91e4-085201abafa4
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0627d246fe9f9f72a95cded7daf8d2c94bf20b3a
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546970"
---
# <a name="ca1501-avoid-excessive-inheritance"></a>CA1501: Unikaj nadmiernego dziedziczenia

|||
|-|-|
|TypeName|AvoidExcessiveInheritance|
|CheckId|CA1501|
|Kategoria|Microsoft.Maintainability|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Typ jest głęboki na więcej niż cztery poziomy w hierarchii dziedziczenia.

## <a name="rule-description"></a>Opis reguły
 Hierarchie typów głęboko zagnieżdżonych mogą być trudne do śledzenia, zrozumienia i utrzymania. Ta zasada ogranicza analizy do hierarchii, w tym samym module.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, typ lub pochodzić od typu podstawowego, który jest mniej szczegółowa w hierarchii dziedziczenia eliminują część pośredniego typów podstawowych.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Jest bezpieczne pominąć ostrzeżenie od tej reguły. Jednak kod może być trudne do utrzymania. Należy pamiętać, że w zależności od widoczność typów podstawowych, rozpoznawanie naruszenie tej zasady może utworzyć przełomowe zmiany. Na przykład usunięcie publicznej typów podstawowych jest istotną zmianę.

## <a name="example"></a>Przykład
 Poniższy przykład pokazuje typ, który narusza regułę.

 [!code-csharp[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/CSharp/ca1501-avoid-excessive-inheritance_1.cs)]
 [!code-vb[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/VisualBasic/ca1501-avoid-excessive-inheritance_1.vb)]