---
title: Ważne polecenia dotyczące języka usługi filtry | Dokumentacja firmy Microsoft
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
- language services, filters
- language services, commands to support
ms.assetid: 4948c494-3d4d-4f50-b3f9-959e73f90e4d
caps.latest.revision: 17
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7305a8263e62711c711a926289ca570a88cf0d15
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690716"
---
# <a name="important-commands-for-language-service-filters"></a>Ważne polecenia dotyczące filtrów usługi językowej
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [ważne polecenia dotyczące filtrów usługi językowej](https://docs.microsoft.com/visualstudio/extensibility/internals/important-commands-for-language-service-filters).  
  
Jeśli chcesz utworzyć filtr usługi języka w pełni wyposażone, należy rozważyć obsługę następujących poleceń. Pełną listę identyfikatorów poleceń jest zdefiniowany w <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> wyliczenie dla kodu zarządzanego i nagłówek Stdidcmd.h pliku niezarządzanych [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] kodu. Można znaleźć w pliku Stdidcmd.h *ścieżka instalacji programu Visual Studio SDK*\VisualStudioIntegration\Common\Inc.  
  
## <a name="commands-to-handle"></a>Polecenia do uchwytu  
  
> [!NOTE]
>  Nie jest wymagane, aby filtrować dla każdego polecenia w poniższej tabeli.  
  
|Polecenie|Opis|  
|-------------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Wysyłany, gdy użytkownik kliknie prawym przyciskiem myszy. To polecenie wskazuje, że nadszedł czas na Zapewnij menu skrótów. Jeśli nie obsługuje tego polecenia, Edytor tekstu zawiera domyślne menu skrótów, bez żadnych poleceń specyficznych dla języka. Aby dołączyć poleceń w tym menu, obsługi polecenia i wyświetli menu skrótów, samodzielnie.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Typowo wysyłana, gdy użytkownik wpisuje CTRL + J. Wywołaj <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> aby pokazać pole uzupełniania instrukcji.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Wysyłany, gdy użytkownik wpisze jakiś znak. Monitorowanie to polecenie, aby określić po wpisaniu znaku wyzwalacza i zapewnienie instrukcji zakończenia, metoda porady i znaczników tekstu, takie jak kolorowanie składni, dopasowywanie nawiasów i znaczniki błędów. Wywołanie <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> uzupełniania instrukcji i <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow> porady metody. Aby zapewnić obsługę znaczników tekstu, monitorowanie to polecenie, aby określić, czy jest wpisany znak wymaga aktualizacji usługi znaczników.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Wysyłany, gdy użytkownik wpisze klawisz Enter. Monitorowanie tego polecenia, aby określić, kiedy zamknąć okno porad metoda przez wywołanie metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A> metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>. Domyślnie widok tekstu obsługuje tego polecenia.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Wysyłany, gdy użytkownik wpisze klawisz Backspace. Monitor do określenia, kiedy zamknąć okno porad metoda przez wywołanie metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A> metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>. Domyślnie widok tekstu obsługuje tego polecenia.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Wysyłane z menu lub klawisza skrótu. Wywołaj <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateTipWindow%2A> metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> można zaktualizować okno porad o informacje o parametrach.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Wysyłany, gdy użytkownik znajduje się nad zmienną lub z kursorem na zmienną i wybiera **Quick Info** z **IntelliSense** w **Edytuj** menu. Zwracany typ zmiennej w oknie z poradami, wywołując <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateTipWindow%2A> metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>. Jeśli debugowanie jest aktywna, porady również powinny pokazywać wartość zmiennej.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Typowo wysyłana, gdy użytkownik wpisuje klawisze CTRL + SPACJA. To polecenie informuje usługa językowa do wywołania <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID><br /><br /> <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Wysyłane z menu, zwykle **Dodaj komentarz do zaznaczenia** lub **Usuń komentarz zaznaczenia** z **zaawansowane** w **Edytuj** menu. <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> Wskazuje, że użytkownik chce, aby przekształcić w komentarz zaznaczonego tekstu. <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> wskazuje, że użytkownik chce usuń znaczniki komentarza w zaznaczonym tekście. Te polecenia można zaimplementować tylko przez usługę języka.|  
  
## <a name="see-also"></a>Zobacz też  
 [Tworzenie starszej wersji usługi językowej](../../extensibility/internals/developing-a-legacy-language-service.md)

