---
title: 'CA2142: Kod przezroczysty nie powinien być chroniony za pomocą LinkDemands | Dokumentacja firmy Microsoft'
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
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 744ca0b6b988591b646c66d349cc39649d323116
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900810"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: Jawny kod nie powinien być chroniony za pomocą LinkDemands
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA2142: kod przezroczysty nie powinien być chroniony za pomocą LinkDemands](https://docs.microsoft.com/visualstudio/code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands).

|||
|-|-|
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2142|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Metoda przezroczysta pod względem wymaga <xref:System.Security.Permissions.SecurityAction> lub inne żądanie zabezpieczeń.

## <a name="rule-description"></a>Opis reguły
 Ta reguła jest uruchamiana na przezroczystych metodach wymagających żądania LinkDemands, aby uzyskać do nich dostęp. Przezroczysty kod zabezpieczeń nie powinien być odpowiedzialny za weryfikację zabezpieczeń operacji, a zatem nie powinien wymagać uprawnień. Ponieważ metody przezroczyste powinna być zabezpieczeń neutralne, ich powinna nie ustawienie wszystkie decyzje dotyczące bezpieczeństwa. Ponadto bezpieczny kod krytyczny, który decyzje dotyczące zabezpieczeń, nie należy polegać na przejrzysty kod będzie mieć wcześniej podjętych decyzji.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, usuń zapotrzebowania na łącza na metoda przezroczysta pod względem lub oznaczyć metody <xref:System.Security.SecuritySafeCriticalAttribute> sprawdza atrybut, jeśli działa zabezpieczeń, takie jak żądania kontroli zabezpieczeń.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 W poniższym przykładzie reguła jest uruchamiana na metodzie, ponieważ metoda jest przejrzysta i jest oznaczona za pomocą LinkDemand <xref:System.Security.PermissionSet> zawierający <xref:System.Security.Permissions.SecurityAction>.

 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2142.transparentmethodsshouldnotbeprotectedwithlinkdemands/cs/ca2142 -transparentmethodsshouldnotbeprotectedwithlinkdemands.cs#1)]

 Nie pomijaj ostrzeżeń dla tej reguły.



