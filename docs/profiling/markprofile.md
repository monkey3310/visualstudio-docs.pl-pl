---
title: MarkProfile | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- MarkProfile
ms.assetid: 54dac8c8-c8ee-4023-af27-b25466e3a6ec
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 98530a790963d1c7fc60742dda4bb16e14a28ab4
ms.sourcegitcommit: 269b55b413d2c82e6aa56c6ab8e53da7926fb2e8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/08/2018
ms.locfileid: "35238163"
---
# <a name="markprofile"></a>MarkProfile
`MarkProfile` Metody wstawia znacznik profil w. *Vsp* pliku. Profilowanie dla wątku zawierający `MarkProfile` funkcja musi być ON znaku do wstawienia.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
PROFILE_COMMAND_STATUS PROFILERAPI MarkProfile( long lMarker );  
```  
  
#### <a name="parameters"></a>Parametry  
 `lMarker`  
  
 Znacznik do wstawienia. Znacznika musi być większa lub równa 0 (zero).  
  
## <a name="property-valuereturn-value"></a>Wartość właściwości wartość/powrotu  
 Funkcja wskazuje powodzenie lub Niepowodzenie przy użyciu **PROFILE_COMMAND_STATUS** wyliczenia. Zwracana wartość może być jedną z następujących czynności:  
  
|Moduł wyliczający|Opis|  
|----------------|-----------------|  
|MARK_ERROR_MARKER_RESERVED|Parametr jest mniejsza lub równa 0. Te wartości są zastrzeżone. Znaczników i komentarzy nie są rejestrowane.|  
|MARK_ERROR_MODE_NEVER|Tryb profilowania została ustawiona na nie, gdy została wywołana funkcja. Znaczników i komentarzy nie są rejestrowane.|  
|MARK_ERROR_MODE_OFF|Tryb profilowania została ustawiona wartość OFF, gdy funkcja została wywołana. Znaczników i komentarzy nie są rejestrowane.|  
|MARK_ERROR_NO_SUPPORT|Brak obsługi znacznik, w tym kontekście. Znaczników i komentarzy nie są rejestrowane.|  
|MARK_ERROR_OUTOFMEMORY|Pamięć nie był dostępny do rejestrowania zdarzenia. Znaczników i komentarzy nie są rejestrowane.|  
|MARK_TEXTTOOLONG|Ciąg przekracza maksymalną 256 znaków. Ciąg komentarz został obcięty i znaczników i komentarzy są rejestrowane.|  
|MARK_OK|MARK_OK jest zwracany, informując o powodzeniu.|  
  
## <a name="remarks"></a>Uwagi  
 Wartość znaku jest wstawiana do. *vsp* plików zawsze kod jest uruchamiany, jeśli wątek zawierający funkcję MarkProfile jest poddawany profilowaniu. Możesz wywołać MarkProfile wiele razy.  
  
 Znaczniki profilu są globalne w zakresie. Na przykład profilu znacznik wstawiony w jeden wątek można oznaczyć początek lub koniec segmentu danych w którymkolwiek wątku w. *vsp* pliku.  
  
 Stan profilowania dla wątku, który zawiera funkcję profilu znak musi być na, jeśli znaczniki i komentarze wstawione przy użyciu polecenia znak lub z funkcji API (CommentMarkAtProfile, CommentMarkProfile lub MarkProfile).  
  
> [!IMPORTANT]
>  Metoda MarkProfile powinien być używany z tylko profilowanie instrumentacji.  
  
## <a name="net-framework-equivalent"></a>Odpowiednik w programie .NET framework  
 *Microsoft.VisualStudio.Profiler.dll*  
  
## <a name="function-information"></a>Informacji o funkcji  
 Nagłówek: Zadeklarowany w *VSPerf.h*  
  
 Importuj biblioteki: *VSPerf.lib*  
  
## <a name="example"></a>Przykład  
 Poniższy kod ilustruje funkcja MarkProfile.  
  
```cpp  
void ExerciseMarkProfile()  
{  
    // Declare and initialize variables to pass to   
    // MarkProfile.  The values of these parameters   
    // are assigned based on the needs of the code;  
    // and for the sake of simplicity in this example,   
    // the variables are assigned arbitrary values.  
    int markId = 03;  
  
    // Declare enumeration to hold return value of   
    // call to MarkProfile.  
    PROFILE_COMMAND_STATUS markResult;  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    markResult = MarkProfile(markId);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("MarkProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, markResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Visual Studio interfejsy API profilera (native)](../profiling/visual-studio-profiler-api-reference-native.md)