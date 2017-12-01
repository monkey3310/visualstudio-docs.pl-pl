---
title: "Użyj jednostki Microsoft testowania Framework dla języka C++ w programie Visual Studio | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d08de69-c32e-4f0b-89aa-75347b15fb82
caps.latest.revision: "11"
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2905f606d47eff8c210ccd66adfd983c11c65a98
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="use-the-microsoft-unit-testing-framework-for-c-in-visual-studio"></a>Użyj jednostki Microsoft testowania Framework dla języka C++ w programie Visual Studio 

Framework testów jednostkowych Microsoft dla języka C++ jest domyślnie włączone w **projektowania aplikacji w języku C++** obciążenia. 

##  <a name="separate_project"></a>Aby napisać testy jednostkowe w oddzielny projekt  
Zazwyczaj uruchomieniu kodu testowego w własny projekt, w tym samym rozwiązaniu jako kod, który ma zostać przetestowana. Do instalowania i konfigurowania nowego projektu testowego, zobacz [dla C/C++ pozwala pisać testy jednostkowe](writing-unit-tests-for-c-cpp.md).

##  <a name="same_project"></a>Można zapisać w tym samym projekcie testy jednostkowe  
W niektórych przypadkach, na przykład podczas testowania-eksportowane funkcje w bibliotece DLL może być konieczne do utworzenia testów w tym samym projekcie jako program, który podczas testowania. Pisania testów jednostkowych w tym samym projekcie:
  
1.  Modyfikowanie właściwości projektu, aby uwzględnić nagłówki i pliki bibliotek, które są wymagane w celu przeprowadzania testów jednostkowych.  
  
    1.  W Eksploratorze rozwiązań kliknij prawym przyciskiem myszy węzeł projektu programu testowania, następnie wybierz pozycje **właściwości | Właściwości konfiguracji | Katalogi VC ++**.  
  
    3.  Kliknij strzałkę w dół w kolejnych wierszach i wybierz polecenie  **<Edit>**  :  
  
        |||  
        |-|-|  
        |**Dołącz katalogi**|**$(VCInstallDir)UnitTest\include;$(IncludePath)**|  
        |**Katalogi bibliotek**|**$(VCInstallDir)UnitTest\lib;$(LibraryPath)**|  
  
2.  Dodaj plik testu jednostkowego języka C++:  
  
    -   Kliknij prawym przyciskiem myszy węzeł projektu w **Eksploratora rozwiązań** i wybierz polecenie **Dodaj | Nowy element | Test jednostkowy C++**.  

## <a name="write-the-tests"></a>Pisanie testów
Dowolny plik .cpp z klasami testu musi obejmować "CppUnitTest.h" i używa instrukcji dla `using namespace Microsoft::VisualStudio::CppUnitTestFramework`. Projekt testowy jest już skonfigurowana za użytkownika. Zawiera również definicję przestrzeni nazw, a TEST_CLASS z TEST_METHOD ułatwiające rozpoczęcie pracy. Możesz zmodyfikować nazwę przestrzeni nazw, jak również nazwy w nawiasach makra klasy i metody.

Specjalne makra są definiowane dla inicjowania modułów testu, klasy i metody i oczyszczania resoures po zakończeniu testów. Te makra generować kod, który jest wykonywany przed klasa lub metoda jest najpierw, a po wykonaniu ostatniego testu. Aby uzyskać więcej informacji, zobacz [inicjowanie i oczyszczanie](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#Initialize_and_cleanup).

Użyj metod statycznych w [Assert](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#general_asserts) klasy w celu zdefiniowania warunków testu. Użyj [rejestratora](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#logger) klasa umożliwiająca zapisanie wiadomości **okno danych wyjściowych**. Dodać atrybuty do metod testowych
  
## <a name="run-the-tests"></a>Uruchom testy  
  
1.  Na **testu** menu, wybierz **Windows**, **Eksploratora testów**.  
2. Jeśli wszystkie testy nie są widoczne w oknie, klikając prawym przyciskiem myszy jego węzła w kompilacji projektu testowego **Eksploratora rozwiązań** i wybierając polecenie **kompilacji** lub **odbudować**.
  
2.  W Eksploratorze testów, wybierz **Uruchom wszystkie**, lub wybierz określonych testów, który chcesz uruchomić. Kliknij prawym przyciskiem myszy na test na inne opcje, w tym, uruchomienie jej w trybie debugowania punkty włączone.
3. W **okno danych wyjściowych** wybierz **testy** na liście do widoku komunikaty zapisywane przez `Logger` klasy:
 
  ![Okno danych wyjściowych C++ przedstawiający wiadomości testowe](media/cpp-test-output-window.png "okno danych wyjściowych")

## <a name="define-traits-to-enable-grouping"></a>Definiowanie cech, aby włączyć grupowanie
Można zdefiniować metody testowe, które umożliwiają klasyfikowanie i grupowanie testów w cech **Eksploratora testów**. Aby zdefiniować cechy, należy użyć `TEST_METHOD_ATTRIBUTE` makra. Na przykład, aby zdefiniować cechy o nazwie `TEST_MY_TRAIT`:  
  
```cpp  
#define TEST_MY_TRAIT(traitValue) TEST_METHOD_ATTRIBUTE(L"MyTrait", traitValue)  
```  
  
 Aby użyć cechy zdefiniowanych w testy jednostkowe:  
  
```  
BEGIN_TEST_METHOD_ATTRIBUTE(Method1)  
    TEST_OWNER(L"OwnerName")  
    TEST_PRIORITY(1)  
    TEST_MY_TRAIT(L"thisTraitValue")  
END_TEST_METHOD_ATTRIBUTE()  
  
TEST_METHOD(Method1)  
{     
    Logger::WriteMessage("In Method1");  
    Assert::AreEqual(0, 0);  
}  
```  
  
### <a name="c-trait-attribute-macros"></a>Makra atrybutu cechy języka C++  
  Znaleziono następujące cechy wstępnie zdefiniowane w `CppUnitTest.h`. Aby uzyskać więcej informacji, zobacz [Microsoft Framework testów jednostkowych for C++ — dokumentacja interfejsu API](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md).

|Makra|Opis|  
|-----------|-----------------|  
|`TEST_METHOD_ATTRIBUTE(attributeName, attributeValue)`|Aby zdefiniować cechy użyć makra TEST_METHOD_ATTRIBUTE.|  
|`TEST_OWNER(ownerAlias)`|Użyj wstępnie zdefiniowanego cechy właściciela, aby określić właściciela metody testowej.|  
|`TEST_PRIORITY(priority)`|Wstępnie zdefiniowane cechy priorytet umożliwia przypisywanie priorytetów do metody testu.|  
  
  
## <a name="see-also"></a>Zobacz też
[Szybki Start: Test programowanie sterowane za pomocą narzędzia Eksplorator testów](../test/quick-start-test-driven-development-with-test-explorer.md)
