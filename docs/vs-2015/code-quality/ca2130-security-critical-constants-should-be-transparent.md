---
title: 'CA2130: Krytyczne stałe zabezpieczeń powinny być przezroczyste | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a74d6fe3c0507914fa4bd9723a53579db230c467
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902281"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: Krytyczne stałe zabezpieczeń powinny być przezroczyste
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA2130: krytyczne stałe zabezpieczeń powinny być przezroczyste](https://docs.microsoft.com/visualstudio/code-quality/ca2130-security-critical-constants-should-be-transparent).

|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|CheckId|CA2130|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Pole stałe lub elementu członkowskiego wyliczenia jest oznaczona za pomocą <xref:System.Security.SecurityCriticalAttribute>.

## <a name="rule-description"></a>Opis reguły
 Wymuszanie przezroczystości nie jest wymuszane dla wartości stałych, ponieważ kompilatory wbudowują stałe wartości, tak aby nie było wymagane żadne wyszukiwanie w czasie wykonywania. Stałe pola powinny być przezroczyste dla zabezpieczeń, tak aby recenzenci kodu nie zakładali, że przezroczysty kod nie może uzyskać dostępu do stałej.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, usuń atrybut SecurityCritical z pól lub wartości.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 W poniższych przykładach wartości wyliczenia `EnumWithCriticalValues.CriticalEnumValue` i stałą `CriticalConstant` podnieść to ostrzeżenie. Aby rozwiązać problemy, Usuń [`SecurityCritical`] atrybutu, aby zwiększyć ich bezpieczeństwo przezroczysty.

 [!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2130.constantsshouldbetransparent/cs/ca2130 - constantsshouldbetransparent.cs#1)]



