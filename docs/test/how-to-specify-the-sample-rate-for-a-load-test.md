---
title: "Porady: określanie wielkości próbki dla ustawień uruchomienia testu obciążenia w programie Visual Studio | Dokumentacja firmy Microsoft"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, run settings
ms.assetid: 51cbe7d6-5dfd-4842-bca3-f7f8a665dc84
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 929946efffe619c81d944e56cf05190b6790f9d9
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-specify-the-sample-rate-for-a-load-test-run-setting"></a>Porady: określanie wielkości próbki dla ustawień testu obciążenia

Po utworzeniu testu obciążenia z **załadować Test Kreatora nowego**, można użyć **edytorze testu obciążenia** Aby zmienić właściwości, aby spełnić potrzeby testowania i cele.

Przy użyciu **edytora testu obciążenia**, można edytować ustawienia wykonywania **częstotliwość próbkowania** wartość właściwości w **właściwości** okna. Aby uzyskać pełną listę właściwości parametry uruchomieniowe i ich opisy, zobacz [właściwości ustawień uruchamiania testu obciążenia](../test/load-test-run-settings-properties.md).

Wybierz odpowiednią **częstotliwość próbkowania** na podstawie właściwości dla testu obciążenia uruchomieniowego na długość testu obciążenia. Mniejszą częstotliwość próbkowania, np. domyślna wartość pięć sekund, wymaga więcej miejsca w bazie danych wyników testu obciążenia. Dłużej testów obciążenia zwiększenie częstotliwości próbkowania powoduje zmniejszenie ilości zbieranych danych. Aby uzyskać więcej informacji, zobacz [porady: określanie wielkości próbki dla ustawień uruchomienia testu obciążenia](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

Poniżej przedstawiono wskazówki dotyczące częstotliwości próbkowania:

|Czas trwania testu obciążenia|Zalecana częstotliwość próbkowania|
|------------------------|-----------------------------|
|\< 1 godzina|5 sekund|
|1 – 8 godzin|15 sekund|
|8 – 24 godziny|30 sekund|
|> 24 godziny|60 sekund|

## <a name="to-specify-performance-counter-sampling-rate-in-a-run-setting"></a>Aby określić częstotliwość próbkowania licznika wydajności w ustawieniach testu

1.  Otwórz testu obciążenia.

     **Edytora testu obciążenia** pojawi się. Zostanie wyświetlone drzewo testu obciążenia.

2.  Obciążenia przetestować drzewa, w **parametrów uruchomieniowych** folderu, wybierz parametr uruchomieniowy, który chcesz określić częstotliwość próbkowania dla.

3.  Na **widoku** menu, wybierz opcję **okna właściwości**.

     Obciążenia Uruchom ustawienia kategorii i właściwości są wyświetlane w oknie właściwości.

4.  W **częstotliwość próbkowania** właściwości, wprowadź wartość czasu, który wskazuje częstotliwość, jaką testu obciążenia zbierania danych licznika wydajności.

5.  Po zmianie właściwości, wybierz **zapisać** na **pliku** menu. Następnie możesz uruchomić test obciążenia przy użyciu nowego **częstotliwość próbkowania** wartość.

## <a name="see-also"></a>Zobacz także

- [Konfigurowanie ustawień testu obciążenia](../test/configure-load-test-run-settings.md)
- [Właściwości scenariusza testów obciążenia](../test/load-test-scenario-properties.md)