---
title: Właściwości sesji wydajności | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,properties
- property pages,Profiling Tools
- performance tools, performance session properties
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ce4fb6b9a57db78e3dbb7f3082a87df9ffb7360
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254696"
---
# <a name="performance-session-properties"></a>Właściwości sesji wydajności

A **sesji wydajności** można skonfigurować ustawienia, które określają, jak jest profilowane aplikacji. Przechowuje raporty, które są generowane dla sesji profilowania.

Możesz utworzyć **sesji wydajności** uruchamiając **kreatora osiągów** lub przez ręczne tworzenie sesji. **Sesji wydajności** jest wyświetlany w **Eksplorator wydajności** po **sesji wydajności** został utworzony.

Aby wyświetlić **sesji wydajności** właściwości, wybierz nazwę sesji w **Eksplorator wydajności**, kliknij go prawym przyciskiem myszy, a następnie wybierz **właściwości**.

Sesja wydajności ma następujące właściwości strony:

## <a name="general"></a>Ogólne

Te ustawienia umożliwiają wybierz metodę, aby dodać kolekcji obiektów platformy .NET i okres istnienia obiektu, a także do określenia domyślnej lokalizacji raportów profilowania i nazewnictwa Konwencji.

Aby uzyskać więcej informacji, zobacz:

[Instrukcje: wybieranie metod zbierania](../profiling/how-to-choose-collection-methods.md)

[Zbieranie danych alokacji pamięci .NET i okresu istnienia](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)

 [Instrukcje: ustawianie opcji nazwy pliku danych wydajności](../profiling/how-to-set-performance-data-file-name-options.md)

## <a name="launch"></a>Uruchom

Te ustawienia umożliwiają wybierz z listy plików binarnych, a także określić kolejność uruchamiania plików binarnych.

Aby uzyskać więcej informacji, zobacz [porady: Określanie plików binarnych do uruchomienia](../profiling/how-to-specify-the-binary-to-start.md)

## <a name="sampling"></a>Pobierania próbek

Te ustawienia umożliwiają wybranie interwału zdarzeń i próbkowania, podczas próbkowania jest używany jako metodę profilowania. Zdarzenie próbkowania służy do zbierania danych profilowania w określonym przedziale czasu. Na przykład, jeśli zdarzenie próbkowania cykli zegara, a interwał próbkowania jest ustawiony na 10 000 000 następnie danych profilowania są zbierane po co 10 milionów cykle zegara. Dostępne są następujące cztery typy zdarzenia próbkowania:

- Cykle zegara - procesora CPU związanego problemów
- Problemy związane z błędów stron - pamięci
- System wywołania — dla operacji We/Wy związane z problemami
- Liczniki wydajności — problemy z wydajnością niskiego poziomu
- Zdarzenia próbkowania dodatkowe można określić oparte na dostępnych liczników wydajności

Aby uzyskać więcej informacji, zobacz [porady: Wybieranie zdarzeń pobierania próbek](../profiling/how-to-choose-sampling-events.md)

## <a name="binary"></a>plików binarnych
Te ustawienia umożliwiają określenie, czy chcesz przenieść instrumentowanego pliku binarnego do innej lokalizacji. Na przykład, jeśli są profilowania *My.DLL* i nie chcesz ich nie przenoś instrumentowanego pliku binarnego kopii zapasowej *My.DLL* o nazwie *My.Orig.DLL* jest tworzony. Następnie *My.DLL* jest modyfikowany przez wstawianie sond do zbierania danych. Jeśli zdecydujesz się przemieszczenie instrumentowanego pliku binarnego, nie zostaje zmieniona oryginalnego pliku binarnego i instrumentowanego pliku binarnego jest kopiowany do określonej lokalizacji do użycia podczas instrumentacji.

Aby uzyskać więcej informacji, zobacz [porady: Określanie plików binarnych do uruchomienia](../profiling/how-to-specify-the-binary-to-start.md)

## <a name="tier-interactions"></a>Interakcje warstw

Aby uzyskać więcej informacji, zobacz [zbierania danych o interakcji między warstwy](../profiling/collecting-tier-interaction-data.md)

## <a name="instrumentation"></a>Oprzyrządowanie

Te ustawienia umożliwiają zbieranie danych wydajności dla kodu języka JScript w [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] strony sieci Web i określ opcje **dokumentu przed** i **POST-instrumentalnych** zdarzenia, które ma być wykonywana przed lub po proces instrumentacji.

Aby uzyskać więcej informacji, zobacz:

[Porady: kodu JavaScript profilu na stronach sieci web](../profiling/how-to-profile-javascript-code-in-web-pages.md)

[Instrukcje: określanie poleceń przed i po instrumentacji](../profiling/how-to-specify-pre-and-post-instrument-commands.md)

## <a name="cpu-counters"></a>Liczniki CPU

Te ustawienia umożliwiają zbieranie danych dotyczących liczników wydajności procesora CPU, gdy używana jest metoda profilowania instrumentacji. Przenośne liczniki wydajności są dostępne niezależnie od producenta lub Procesora projektu. Zdarzenia platformy są specyficzne dla Procesora projektu i producenta. Aby uzyskać więcej informacji na temat liczników wydajności w układzie zobacz dokumentację konkretny procesor.

Aby uzyskać więcej informacji, zobacz [porady: Procesora zbieranie danych licznika](../profiling/how-to-collect-cpu-counter-data.md)

## <a name="windows-events"></a>Zdarzenia systemu Windows

Podczas profilowania, może zbierać dane z dostawców śledzenia zdarzeń. Dane można wyświetlić przy użyciu *VSPerfReport.exe* narzędzia wiersza polecenia `/calltrace` opcji. Aby uzyskać więcej informacji na temat funkcji Śledzenie zdarzeń systemu Windows (), zobacz [o śledzenie zdarzeń](http://go.microsoft.com/fwlink/?linkid=90752).

Aby uzyskać więcej informacji, zobacz:

[Instrukcje: zbieranie danych śledzenia zdarzeń dla systemu Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)

[VSPerfReport](../profiling/vsperfreport.md).

## <a name="windows-counters"></a>Liczniki systemu Windows

Ta opcja służy do zbierania danych z liczników monitora wydajności systemu Windows. Aby zbierać dane, zaznacz pole wyboru **zbierania liczników wydajności systemu Windows**. Interwał kolekcji można ustawić w **interwał zbierania** pole. **Kategoria licznika** i **wystąpienia** mogą być również dostępne. Dostępne są niektóre domyślne liczniki Monitora wydajności systemu Windows.

 Aby uzyskać więcej informacji, zobacz [porady: Windows zbieranie danych licznika](../profiling/how-to-collect-windows-counter-data.md).

## <a name="advanced"></a>Zaawansowane

Te ustawienia umożliwiają dodanie opcje do procesu instrumentacji, przez określenie opcji co najmniej jeden [VSInstr](../profiling/vsinstr.md) narzędzia profilowania wiersza polecenia. Jeśli aplikacja korzysta z więcej niż jednej wersji, można również określić wersji plików wykonywalnych do profilu.

Aby uzyskać więcej informacji, zobacz:

[Instrukcje: określanie środowiska uruchomieniowego programu .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)

[Instrukcje: określanie dodatkowych opcji instrumentacji](../profiling/how-to-specify-additional-instrumentation-options.md)

## <a name="see-also"></a>Zobacz także

[Omówienia](../profiling/overviews-performance-tools.md)  
[Konfigurowanie sesji wydajności](../profiling/configuring-performance-sessions.md)  
[Sterowanie zbieraniem danych](../profiling/controlling-data-collection.md)