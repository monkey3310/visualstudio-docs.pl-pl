---
title: Aplikacje warstwowe — Przegląd
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- presentation tier
- middle tier
- data tier
- n-tier applications, about n-tier applications
ms.assetid: 1020581d-eaaa-41a2-aca4-bf4c212895f6
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 4e386c052b43ee62ddde0516fa203298fe1babe5
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089033"
---
# <a name="n-tier-data-applications-overview"></a>Omówienie aplikacji warstwowych
*N-warstwowa* dane aplikacji są dane aplikacji, które są podzielone na wielu *warstw*. Ich inne nazwy to „aplikacje rozproszone” i „aplikacje wielowarstwowe”. Aplikacje n-warstwowe dzielą przetwarzanie na dyskretne warstwy, które są rozkładane między klienta i serwer. Podczas tworzenia aplikacji uzyskujących dostęp do danych należy jednoznacznie odseparować różne warstwy tworzące aplikację.

Typowa aplikacja n-warstwowa zawiera warstwę prezentacji, warstwę środkową i warstwę danych. Najłatwiejszym sposobem rozdzielenia różnych warstw w n-warstwowej aplikacji jest utworzenie dyskretnych projektów dla każdej warstwy, która ma się znaleźć w aplikacji. Na przykład warstwą prezentacji może być aplikacja środowiska Windows Forms, podczas gdy logiką dostępu do danych może być biblioteka klas umieszczona w warstwie środkowej. Ponadto warstwa prezentacji może się komunikować z logiką dostępu do danych w warstwie środkowej za pośrednictwem usługi. Rozdzielanie składników aplikacji w oddzielne warstwy ułatwia konserwację i zwiększa skalowalność aplikacji. Wynika to z możliwości łatwiejszego wprowadzania nowych technologii do poszczególnych warstw, bez konieczności zmiany projektu całego rozwiązania. Dodatkowo zazwyczaj n-warstwowe aplikacje przechowują wrażliwe informacje w środkowej warstwie, która utrzymuje izolację od warstwy prezentacji.

Program Visual Studio zawiera kilka funkcji, które ułatwiają deweloperom tworzenie aplikacji n-warstwowych:

-   Zestaw danych zawiera **projektu DataSet** właściwość, która umożliwia dataset (dane jednostki layer) i TableAdapters (Warstwa dostępu do danych) w projektach dyskretnych.

-   [Narzędzi LINQ do SQL w programie Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) zawiera ustawienia do generowania klasy DataContext i dane w oddzielnych przestrzeni nazw. Takie rozwiązania pozwala logicznie rozdzielić warstwy dostępu do danych i jednostek danych.

-   [LINQ do SQL](/dotnet/framework/data/adonet/sql/linq/index) zapewnia <xref:System.Data.Linq.Table%601.Attach%2A> metodę, która umożliwia zbieranie DataContext z różnych warstw w aplikacji. Aby uzyskać więcej informacji, zobacz [N-warstwowa oraz zdalnych aplikacji za pomocą LINQ do SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql).

## <a name="presentation-tier"></a>Warstwa prezentacji
*Warstwy prezentacji* warstwa, w którym użytkownicy korzystają z aplikacji. Często zawiera także dodatkową logikę aplikacji. Oto typowe składniki warstwy prezentacji:

-   Składniki powiązania danych, takie jak <xref:System.Windows.Forms.BindingSource> i <xref:System.Windows.Forms.BindingNavigator>.

-   Obiekt dane, takie jak [LINQ do SQL](/dotnet/framework/data/adonet/sql/linq/index) klas jednostek do użycia w warstwie prezentacji.

Warstwa prezentacji zwykle uzyskuje dostęp do warstwy środkowej przy użyciu odwołania do usługi (na przykład [usług Windows Communication Foundation oraz usługi danych WCF w programie Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) aplikacji). Warstwa prezentacji nie uzyskuje bezpośredniego dostępu do warstwy danych. Warstwa prezentacji komunikuje się z warstwą danych za pomocą składnika dostępu do danych w warstwie środkowej.

## <a name="middle-tier"></a>Warstwa środkowa
*Warstwy środkowej* jest warstwie warstwą prezentacji a danych warstwy używają do komunikowania się ze sobą. Oto typowe składniki warstwy środkowej:

-   Logika biznesowa, taka jak reguły biznesowe i mechanizmy sprawdzania poprawności danych.

-   Składniki i logika dostępu do danych, w tym:

    -   [TableAdapters](create-and-configure-tableadapters.md) i [obiektów DataAdapter i DataReaders](/dotnet/framework/data/adonet/dataadapters-and-datareaders).

    -   Obiekt dane, takie jak [LINQ do SQL](/dotnet/framework/data/adonet/sql/linq/index) klas jednostek.

    -   Wspólne usługi aplikacji, takie jak uwierzytelnianie, autoryzacja i personalizacja.

Na ilustracji poniżej widać funkcje i technologie, które są dostępne w programie Visual Studio i mogą być umieszczone w środkowej warstwie aplikacji n-warstwowej.

![Środkowy składników warstwy](../data-tools/media/ntiermid.png) bliski warstwy

Warstwa środkowa zazwyczaj łączy się z warstwą danych przy użyciu połączenia danych. To połączenie danych jest zazwyczaj przechowywane w składniku dostępu do danych.

## <a name="data-tier"></a>Warstwa danych
*Warstwy danych* jest zasadniczo serwera, która przechowuje dane aplikacji (na przykład serwera z systemem [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]).

Na ilustracji poniżej widać funkcje i technologie, które są dostępne w programie Visual Studio i mogą być umieszczone w warstwie danych aplikacji n-warstwowej.

![Składniki warstwy danych](../data-tools/media/ntierdatatier.png) warstwy danych

Warstwa danych nie może być dostępna bezpośrednio z klienta w warstwie prezentacji. Zamiast tego składnik dostępu do danych w warstwie środkowej obsługuje komunikację między warstwami prezentacji i danych.

## <a name="help-for-n-tier-development"></a>Pomoc dla rozwoju n warstwowa
Poniższe tematy zawierają informacje dotyczące pracy z aplikacjami n-warstwowymi:

[Rozdzielanie zestawów danych i adapterów TableAdapter do różnych projektów](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)

[Wskazówki: Tworzenie aplikacji warstwowych](../data-tools/walkthrough-creating-an-n-tier-data-application.md)

[N-warstwowa oraz zdalnych aplikacji za pomocą LINQ do SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)

## <a name="see-also"></a>Zobacz także

- [Wskazówki: Tworzenie aplikacji warstwowych](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [Hierarchiczna aktualizacja](../data-tools/hierarchical-update.md)
- [Narzędzia zestawu danych w programie Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
- [Uzyskiwanie dostępu do danych w programie Visual Studio](../data-tools/accessing-data-in-visual-studio.md)