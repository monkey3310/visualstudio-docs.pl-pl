---
title: Dyrektywy T4 dotyczące szablonu tekstowego
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, import directive
- text templates, include directive
- text templates, assembly directive
- text templates, output directive
- text templates, directives
- text templates, template directive
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: c01bea709d551e970ed8c44ec861ff348c7081ad
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947849"
---
# <a name="t4-text-template-directives"></a>Dyrektywy T4 dotyczące szablonu tekstowego
Dyrektywy zawierają instrukcje dla aparatu przekształceń szablonu tekstu.

 Składnia dyrektyw jest następująca:

```
<#@ DirectiveName [AttributeName = "AttributeValue"] ... #>
```

 Wszystkie wartości atrybutów muszą być ujęte w podwójny cudzysłów. Jeśli sama wartość zawiera znaki cudzysłowu, muszą je poprzedzać znaki ucieczki \.

 Dyrektywy to zazwyczaj pierwsze elementy w pliku szablonu lub pliku dołączanym. Nie należy umieszczać je w bloku kodu `<#...#>`, ani po bloku funkcji klasy `<#+...#>`.

 [Dyrektywa T4 dotycząca szablonu](../modeling/t4-template-directive.md)
 ```
<#@ template [language="VB"] [hostspecific="true|TrueFromBase"] [debug="true"] [inherits="templateBaseClass"] [culture="code"] [compilerOptions="options"] [visibility="internal"] [linePragmas="false"] #>
```

 [Dyrektywa T4 dotycząca parametru](../modeling/t4-parameter-directive.md)
 ```
<#@ parameter type="Full.TypeName" name="ParameterName" #>
```

 [Dyrektywa T4 dotycząca danych wyjściowych](../modeling/t4-output-directive.md)
 ```
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>
```

 [Dyrektywa T4 dotycząca zestawu](../modeling/t4-assembly-directive.md)
 ```
<#@ assembly name="[assembly strong name|assembly file name]" #>
```

 [Dyrektywa T4 dotycząca importowania](../modeling/t4-import-directive.md)
 ```
<#@ import namespace="namespace" #>
```

 [Dyrektywa T4 dotycząca dołączania](../modeling/t4-include-directive.md)
 ```
<#@ include file="filePath" #>
```

 [Dyrektywa T4 dotycząca działania CleanUpBehavior](../modeling/t4-cleanupbehavior-directive.md)
 ```
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>
```

 Ponadto można tworzyć własne dyrektywy. Aby uzyskać więcej informacji, zobacz [tworzenie procesory dyrektywy szablonu niestandardowego T4 tekstu](../modeling/creating-custom-t4-text-template-directive-processors.md). Jeśli używasz wizualizacji i modelowania SDK do tworzenia języka specyficznego dla domeny (DSL), procesor dyrektywy zostanie wygenerowany jako część DSL.