---
title: Polecenie VSPerfASPNetCmd | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- profiling tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
ms.assetid: f9e9f895-57bb-41e8-8bd1-cdaa738ec220
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a074edba64f9742f9761754279be35f5c621be2b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633048"
---
# <a name="vsperfaspnetcmd"></a>VSPerfASPNetCmd
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [VSPerfASPNetCmd](https://docs.microsoft.com/visualstudio/profiling/vsperfaspnetcmd).  
  
**VSPerfASPNetCmd.exe** narzędzia wiersza polecenia umożliwia profilu ASP.Net witryn sieci Web bez konieczności ustawiania zmiennych środowiskowych, lub uruchom ponownie komputer. Użyj **VSPerfASPNetCmd.exe** zamiast [VSPerfCmd](../profiling/vsperfcmd.md) podczas profilowany witryn sieci Web platformy ASP.NET i nie są dodatkowe funkcje udostępniane przez **VSPerCmd**. Aby uzyskać więcej informacji na temat **VSPerfASPNetCmd**, zobacz [szybkie profilowanie witryny sieci Web za pomocą polecenia VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md). **Polecenie VSPerfASPNetCmd** to narzędzie wiersza polecenia preferowanych do użycia podczas korzystania z Autonomiczny profiler profilowanie witryny sieci Web ASP.NET.  
  
## <a name="syntax"></a>Składnia  
 **polecenie vsperfaspnetcmd** [/*opcje*] *witryny sieci Web*  
  
## <a name="options"></a>Opcje  
  
|Opcja|Opis|  
|------------|-----------------|  
|**/ Przykładowe** lub **/s**|Profile witryny sieci Web przy użyciu metody próbkowania. **/ Przykładowe** jest domyślną metodą. / Przykładowe nie można używać z **/Trace**.|  
|**/ Trace** lub   **/t**|Profile witryny sieci Web przy użyciu metody instrumentacji. / Śledzenia nie można używać z **/Sample**.|  
|**/ Pamięci**[**:**`Type`] lub **/m**[**:**{**a**&#124;**l**}]|Służą do profilowania alokacji pamięci i opcjonalnie profile czasów istnienia obiektów (wyrzucania elementów bezużytecznych). **/ Pamięci** mogą być używane z pobieranie próbek lub metody instrumentacji.<br /><br /> *Typ* może być jedną z następujących czynności:<br /><br /> -   **Alokacja** (lub **a**) zbiera tylko dane alokacji pamięci.<br />-   **okres istnienia** (lub **l**) zbiera dane okresu istnienia alokacji i obiektu pamięci.<br /><br /> Wartość domyślna `Type` jest **alokacji**.|  
|**/ Porada** lub **/i**|Dodaje szczegółowe żądania programu ASP.NET i informacje o wywołaniach ADO.NET do danych profilowania. **/ Porada** mogą być używane z pobieranie próbek lub metody instrumentacji, i mogą być używane z **/Memory** opcji.|  
|**/ Output:** `File` lub   **/o:**`File`|Określa ścieżkę i nazwę pliku danych (Vsp) profilowania.|  
|**/ NoWait** lub **/n**|Zwraca polecenie prompt natychmiast dzięki dodatkowe polecenia mogą być używane w oknie wiersza polecenia. Należy wpisać **polecenie VSPerfASPNETCmd/shutdown** w osobnym wierszu polecenia, aby wyłączyć profilowania.|  
|**/ PackSymbols**[: {**na**&#124;**poza**} lub **/p**[: {**na**&#124;**poza**}|Osadza symbole (nazwy funkcji i parametr itp.) w profilowania (.vsp) danych.|  
|**/ Shutdown:** `Website`lub   **/d:**`Website`|Włącza profilowanie wyłączone. Użyj jako jedyną opcją, w wierszu polecenia po zakończeniu korzystania z **flagi/nowait** opcji do uruchomienia profilowania, lub jeśli program profilujący zakończy się nieoczekiwanie. Określ ten sam adres url, którego używano w oryginalnym **VSPerfASPNETCmd** polecenia.|  
|`Website`|Adres url witryny sieci Web do profilowania.|  
  
## <a name="see-also"></a>Zobacz też  
 [Szybkie profilowanie za pomocą polecenia VSPerfASPNETCmd witryny sieci Web](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)   
 [Profilowanie aplikacji sieci Web platformy ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)



