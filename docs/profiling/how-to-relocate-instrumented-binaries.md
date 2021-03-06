---
title: 'Porady: przemieszczanie instrumentowanych plików binarny | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.binaries
helpviewer_keywords:
- binaries, instrumented
- instrumentation, instrumented binaries
- instrumented binaries and relocating
- profiling tools, instrumented binaries
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a060506f818ac000611fc0c29988ed324ae89226
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2018
ms.locfileid: "34843656"
---
# <a name="how-to-relocate-instrumented-binaries"></a>Porady: przemieszczanie instrumentowanych plików binarny

Podczas Instrumentacji sond są wstawiane do pliku binarnego do pomiaru wydajności aplikacji. Wybierając może przenosić instrumentowanego pliku binarnego, kopia oryginalnego pliku binarnego jest instrumentowany i umieszcza w określonej lokalizacji. Ta opcja jest przydatna, jeśli nie chcesz profilera, aby zmienić nazwę z oryginalnego pliku binarnego. Jeśli plik binarny nie został przeniesiony, jest zastępowany oryginalną wersją pliku binarnego.

## <a name="to-relocate-instrumented-binary"></a>Aby przenieść instrumentowanego pliku binarnego

1. W **Eksplorator wydajności**, kliknij prawym przyciskiem myszy sesję wydajności, a następnie kliknij przycisk **właściwości**.

2. W **strony właściwości**, kliknij przycisk **binarne** właściwości.

3. Wybierz **przemieszczanie instrumentowanych plików binarny** pole wyboru.

4. Określ lokalizację dla instrumentowanego pliku binarnego.

## <a name="see-also"></a>Zobacz także

[Konfigurowanie sesji wydajności](../profiling/configuring-performance-sessions.md)  
[VSInstr](../profiling/vsinstr.md)
