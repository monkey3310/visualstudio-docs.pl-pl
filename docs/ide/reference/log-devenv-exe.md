---
title: -Log (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3373f1e1a23ae0373a9c49a39a924398ebe143e0
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704775"
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
Loguje wszelką aktywność do pliku dziennika w celu rozwiązywania problemów. Ten plik jest wyświetlany po została wywołana `devenv /log` co najmniej raz. Domyślnie plik dziennika jest:

 *% APPDATA %* \Microsoft\VisualStudio\\*wersji*\ActivityLog.xml

 gdzie *wersji* jest wersją programu Visual Studio. Może jednak określić inną ścieżkę i nazwę.

## <a name="syntax"></a>Składnia

```cmd
Devenv /log Path\NameOfLogFile
```

## <a name="remarks"></a>Uwagi
 Ten przełącznik musi być umieszczony na końcu wiersza polecenia po innych przełącznikach.

 Dziennik jest zapisywany dla wszystkich wystąpień programu Visual Studio, która została wywołana z przełącznikiem/log. Go nie logowania wystąpienia programu Visual Studio, który został wywołany bez utworzenia przełącznika.

## <a name="see-also"></a>Zobacz też

- [Przełączniki wiersza polecenia Devenv](../../ide/reference/devenv-command-line-switches.md)