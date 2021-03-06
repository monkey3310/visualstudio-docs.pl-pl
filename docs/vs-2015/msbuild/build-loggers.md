---
title: Rejestratory kompilacji | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, writing loggers
- MSBuild, logging
- logging [MSBuild]
ms.assetid: fa34810d-185a-4d22-92bd-9852915e5f1d
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e2e16c7ad611be9c1fa26056279b0085dd57c91f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682930"
---
# <a name="build-loggers"></a>Rejestratory kompilacji
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [rejestratory kompilacji](https://docs.microsoft.com/visualstudio/msbuild/build-loggers).  
  
  
Rejestratory umożliwiają umożliwiające dostosowanie dane wyjściowe kompilacji i wyświetlanie wiadomości, błędy lub ostrzeżenia w odpowiedzi na zdarzenia w konkretnej kompilacji. Każdy rejestrator jest implementowany jako klasa .NET, która implementuje <xref:Microsoft.Build.Framework.ILogger> interfejs, który jest zdefiniowany w zestawie Microsoft.Build.Framework.dll.  
  
 Istnieją dwie metody, których można użyć podczas implementowania Rejestrator:  
  
-   Implementowanie <xref:Microsoft.Build.Framework.ILogger> interfejs bezpośrednio.  
  
-   Pochodną klasy z klasy Pomocnika <xref:Microsoft.Build.Utilities.Logger>, który jest zdefiniowany w zestawie Microsoft.Build.Utilities.dll. <xref:Microsoft.Build.Utilities.Logger> implementuje <xref:Microsoft.Build.Framework.ILogger> i zawiera domyślne implementacje niektórych <xref:Microsoft.Build.Framework.ILogger> elementów członkowskich.  
  
 W tym temacie wyjaśniono, jak napisać prosty rejestratora, która pochodzi od klasy <xref:Microsoft.Build.Utilities.Logger>, i wyświetla komunikaty na konsoli w odpowiedzi na niektóre zdarzenia kompilacji.  
  
## <a name="registering-for-events"></a>Rejestracja nasłuchiwania zdarzeń  
 Rejestrator ma na celu zbierania informacji o postępie kompilacji, zgłoszonej przez aparat kompilacji, a następnie zgłaszanie tych informacji w wygodny sposób. Należy zastąpić wszystkie rejestratory <xref:Microsoft.Build.Utilities.Logger.Initialize%2A> metoda, która jest, gdy rejestruje rejestratora dla zdarzeń. W tym przykładzie rejestruje rejestratora <xref:Microsoft.Build.Framework.IEventSource.TargetStarted>, <xref:Microsoft.Build.Framework.IEventSource.ProjectStarted>, i <xref:Microsoft.Build.Framework.IEventSource.ProjectFinished> zdarzenia.  
  
 [!code-csharp[msbuild_SimpleConsoleLogger#2](../snippets/csharp/VS_Snippets_Misc/msbuild_SimpleConsoleLogger/CS/msbuild_SimpleConsoleLogger.cs#2)]  
  
## <a name="responding-to-events"></a>Odpowiadanie na zdarzenia  
 Teraz, gdy rejestratora jest zarejestrowany dla określonych zdarzeń, musi obsługiwać te wydarzenia w momencie ich wystąpienia. Aby uzyskać <xref:Microsoft.Build.Framework.IEventSource.ProjectStarted>, i <xref:Microsoft.Build.Framework.IEventSource.ProjectFinished> zdarzenia, rejestratora zapisuje po prostu krótkich fraz i nazwę pliku projektu zaangażowanych w zdarzeniu. Wszystkie komunikaty z Rejestratora są zapisywane w oknie konsoli.  
  
 [!code-csharp[msbuild_SimpleConsoleLogger#3](../snippets/csharp/VS_Snippets_Misc/msbuild_SimpleConsoleLogger/CS/msbuild_SimpleConsoleLogger.cs#3)]  
  
## <a name="responding-to-logger-verbosity-values"></a>Reagowanie na wartości poziom szczegółowości rejestratora  
 W niektórych przypadkach możesz tylko rejestrować informacje ze zdarzenia, jeśli MSBuild.exe **/verbosity** przełącznik zawiera określoną wartość. W tym przykładzie <xref:Microsoft.Build.Framework.IEventSource.TargetStarted> programu obsługi zdarzeń tylko rejestruje wiadomość, jeśli <xref:Microsoft.Build.Utilities.Logger.Verbosity%2A> właściwość, która została ustawiona przez **/verbosity** przełącznika, jest równa <xref:Microsoft.Build.Framework.LoggerVerbosity> `Detailed`.  
  
 [!code-csharp[msbuild_SimpleConsoleLogger#4](../snippets/csharp/VS_Snippets_Misc/msbuild_SimpleConsoleLogger/CS/msbuild_SimpleConsoleLogger.cs#4)]  
  
## <a name="specifying-a-logger"></a>Określanie Rejestrator  
 Gdy rejestratora jest kompilowany do zestawu, należy przekazać [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] do użycia tego rejestratora podczas kompilacji. Odbywa się przy użyciu **/logger** przełącznik z MSBuild.exe. Aby uzyskać więcej informacji na temat parametrów, które są dostępne dla MSBuild.exe, zobacz [odwołanie do wiersza polecenia](../msbuild/msbuild-command-line-reference.md).  
  
 Następujące polecenie w wierszu tworzy projekt `MyProject.csproj` i wykorzystuje klasy rejestratora zaimplementowane w `SimpleLogger.dll`. **/Nologo** przełącznika ukrywa transparent i komunikat o prawach autorskich oraz **/noconsolelogger** przełącznika wyłącza domyślne [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] rejestratora konsoli.  
  
```  
MSBuild /nologo /noconsolelogger /logger:SimpleLogger.dll  
```  
  
 Następujące polecenie w wierszu tworzy projekt za pomocą tego samego rejestratora, ale z `Verbosity` poziom `Detailed`.  
  
```  
MSBuild /nologo /noconsolelogger /logger:SimpleLogger.dll /verbosity:Detailed  
```  
  
## <a name="example"></a>Przykład  
  
### <a name="description"></a>Opis  
 Poniższy przykład zawiera kompletny kod dla rejestratora.  
  
### <a name="code"></a>Kod  
 [!code-csharp[msbuild_SimpleConsoleLogger#1](../snippets/csharp/VS_Snippets_Misc/msbuild_SimpleConsoleLogger/CS/msbuild_SimpleConsoleLogger.cs#1)]  
  
### <a name="comments"></a>Komentarze  
  
## <a name="example"></a>Przykład  
  
### <a name="description"></a>Opis  
 Poniższy przykład pokazuje, jak zaimplementować rejestrator, który zapisuje dziennik do pliku, a nie jej wyświetlania w oknie konsoli.  
  
### <a name="code"></a>Kod  
 [!code-csharp[msbuild_BasicLogger#1](../snippets/csharp/VS_Snippets_Misc/msbuild_BasicLogger/CS/msbuild_BasicLogger.cs#1)]  
  
### <a name="comments"></a>Komentarze  
  
## <a name="see-also"></a>Zobacz też  
 [Uzyskiwanie dzienników kompilacji](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Pojęcia dotyczące programu MSBuild](../msbuild/msbuild-concepts.md)



