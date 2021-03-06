---
title: Dopasowanie przekształcenia tekstu T4 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
ms.assetid: 62cd9a3c-a6e1-4b29-93f5-f2a0cf47dc92
caps.latest.revision: 30
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: e304b38979b80c1d67d3f88accdbfa584406c9cb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684765"
---
# <a name="customizing-t4-text-transformation"></a>Dopasowanie przekształcenia tekstu T4
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Dostosowywanie przekształcenia tekstu T4](https://docs.microsoft.com/visualstudio/modeling/customizing-t4-text-transformation).  
  
Szablony tekstowe są funkcją [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] umożliwiającą generować kod programu lub innych plików tekstowych, proces przekształcenia. Za pomocą [!INCLUDE[vssdk_current_short](../includes/vssdk-current-short-md.md)], można rozszerzyć proces przekształcania szablonu domyślnego, dostosowując procesora dyrektywy szablonu tekstu lub hosta szablonu tekstu.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Proces przekształcania szablonu tekstowego](../modeling/the-text-template-transformation-process.md)  
 W tym artykule opisano, jak działa Transformacja tekstu i opisano rolę hosta szablonu i procesorów dyrektyw.  
  
 [Tworzenie niestandardowych procesorów dyrektywy T4 dotyczącej szablonu tekstowego](../modeling/creating-custom-t4-text-template-directive-processors.md)  
 Procesor dyrektywy zajmuje się dyrektywy w szablonie, takich jak `<#@template#>.` jest uruchamiany podczas kompilacji szablonu i mogą ładować zestawy i innych zasobów. Można także wstawić kod, który załaduje zasobów w czasie wykonywania. Definiując procesor dyrektywy, można zmniejszyć złożoność szablonów.  
  
 [Wywoływanie transformacji tekstu w rozszerzeniu VS](../modeling/invoking-text-transformation-in-a-vs-extension.md)  
 Jeśli piszesz [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozszerzenia takich jak obsługa polecenia lub zdarzenia menu, rozszerzenia użyć usługi szablonów tekstowych do przekształcania dowolnego szablonu tekstu. Można przekazać danych parametru do szablonu, za pomocą obiektu sesji i uzyskać wartości z w ramach szablonu za pomocą `<#@parameter#>` dyrektywy.  
  
 [Przetwarzanie szablonów tekstowych przy użyciu hosta niestandardowego](../modeling/processing-text-templates-by-using-a-custom-host.md)  
 Podczas wykonywania kodu szablonu tekstu, host zapewnia dostęp do plików zewnętrznych i stan aplikacji. Na przykład host, który uruchamia przekształcenia tekstu w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] można zapewnić dostęp do Eksploratora rozwiązań. Wyświetla również błędy w oknie komunikat o błędzie. Jeśli chcesz uruchomić przekształcenia tekstu w innym kontekście, można zdefiniować własnego hosta, który zapewnia dostęp do usług, które są dostępne w tym kontekście.  
  
 Jeśli piszesz [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozszerzenie, należy wziąć pod uwagę przy użyciu istniejącej usługi przekształcenia tekstu zamiast pisania własnego hosta. Aby uzyskać więcej informacji, zobacz [wywoływanie transformacji tekstu w rozszerzeniu VS](../modeling/invoking-text-transformation-in-a-vs-extension.md).  
  
## <a name="reference"></a>Tematy pomocy  
 [Pisanie szablonu tekstowego T4](../modeling/writing-a-t4-text-template.md)  
  
 Udostępnia składnia dyrektyw szablonu tekstu i bloki sterujące.



