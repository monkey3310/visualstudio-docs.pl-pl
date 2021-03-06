---
title: 'CA1007: Używaj danych generycznych wszędzie, gdzie jest to odpowiednie'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1007
- UseGenericsWhereAppropriate
helpviewer_keywords:
- CA1007
- UseGenericsWhereAppropriate
ms.assetid: eab780ea-3b1f-4d32-b15a-5d48da2df46b
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: d3e03c1028dc310748aff7c8263ce75ace9985be
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551741"
---
# <a name="ca1007-use-generics-where-appropriate"></a>CA1007: Używaj danych generycznych wszędzie, gdzie jest to odpowiednie

|||
|-|-|
|TypeName|UseGenericsWhereAppropriate|
|CheckId|CA1007|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Metoda widoczna na zewnątrz zawiera parametr przekazany przez odwołanie typu <xref:System.Object?displayProperty=fullName>, zawierające cele zestawu i [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)].

## <a name="rule-description"></a>Opis reguły
 Parametr przekazany przez odwołanie jest parametr, który jest modyfikowana przy użyciu `ref` (`ByRef` w [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) — słowo kluczowe. Typ argumentu, który jest dostarczany dla parametru odwołania musi dokładnie odpowiadać typ parametru odwołania. Aby użyć typu, który pochodzi od typu parametru odwołania, typ najpierw należy przypisać do zmiennej typu parametru odwołania i rzutowania. Użyj metody ogólnej umożliwia wszystkich typów podlegających ograniczeniom, które zostaną przekazane do metody bez uprzedniego rzutowania typu do typu parametru odwołania.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, wprowadzić metody rodzajowe i Zastąp <xref:System.Object> parametru za pomocą parametru typu.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 Poniższy przykład pokazuje procedury wymiany ogólnego przeznaczenia, który jest implementowany jako metody zarówno nierodzajowych, jak i ogólnych. Należy pamiętać o tym, jak wydajnie ciągi są zamienione przy użyciu metody rodzajowej, w porównaniu do nierodzajowymi metody.

 [!code-vb[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/VisualBasic/ca1007-use-generics-where-appropriate_1.vb)]
 [!code-csharp[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/CSharp/ca1007-use-generics-where-appropriate_1.cs)]

## <a name="related-rules"></a>Powiązane reguły
 [CA1005: Unikaj nadużywania parametrów w typach ogólnych](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: Kolekcje powinny implementować interfejs ogólny](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: Nie deklaruj składowych statycznych w typach ogólnych](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: Nie ujawniaj list ogólnych](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: Nie zagnieżdżaj typów ogólnych w sygnaturach składowych](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: Metody ogólne powinny udostępniać parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Użyj wystąpień ogólnej procedury obsługi zdarzeń](../code-quality/ca1003-use-generic-event-handler-instances.md)

## <a name="see-also"></a>Zobacz także
 [Typy ogólne](/dotnet/csharp/programming-guide/generics/index)