---
title: Korzystanie z usług i dostarczanie | Dokumentacja firmy Microsoft
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
- examples [Visual Studio SDK], services
- Visual Studio, services
- services
ms.assetid: c0b415ba-b825-4da0-9faf-8a60a663e302
caps.latest.revision: 42
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: facf0bb9968e3ffbc9a68eb8eee906f300eb1859
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692445"
---
# <a name="using-and-providing-services"></a>Korzystanie z usług i dostarczanie ich
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Using i dostarczanie usług](https://docs.microsoft.com/visualstudio/extensibility/using-and-providing-services).  
  
Usługa jest Umowa między dwoma pakietami VSPackage. Jednego pakietu VSPackage oferuje zestaw określonych interfejsów dla innego pakietu VSPackage korzystać. Na przykład [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] oferuje <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> do dowolnego pakietu VSPackage go obsłużyć obciążenia. Ta usługa zapewnia <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> interfejs, który może służyć do zapisu w dzienniku aktywności. Aby uzyskać więcej informacji, zobacz [porady: Korzystanie z dziennika aktywności](../extensibility/how-to-use-the-activity-log.md).  
  
 Pakietów VSPackage może oferować swoje własne przy użyciu usług <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> interfejs...  
  
 Program Visual Studio udostępnia ważne usługi, takie jak następujące:  
  
|Usługa środowiska IDE|Opis|  
|-----------------|-----------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>|Zapewnia dostęp do środowiska IDE usług radzenia sobie z podstawowych funkcji, pakietów VSPackage i rejestru.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|Udostępnia podstawowe obsługi okien i związane z interfejsem użytkownika w środowisku IDE, takie jak możliwość tworzenia, narzędzi i oknami dokumentu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|Zapewnia podstawowe funkcje związane z rozwiązania, takimi jak wyliczyć projektów, Utwórz nowe projekty i monitorowanie zmian projektu.|  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Podstawowe informacje o usłudze](../extensibility/internals/service-essentials.md)  
 Przedstawia informacje o ważnych elementów usługi Visual Studio.  
  
 [Instrukcje: uzyskiwanie usługi](../extensibility/how-to-get-a-service.md)  
 W tym artykule omówiono sposób żądania (Używanie) usługi.  
  
 [Instrukcje: dostarczanie usługi](../extensibility/how-to-provide-a-service.md)  
 W tym artykule omówiono sposób zapewniania usług.  
  
 [Instrukcje: dostarczanie asynchronicznej usługi programu Visual Studio](../extensibility/how-to-provide-an-asynchronous-visual-studio-service.md)  
 W tym artykule omówiono sposób obsługi asynchronicznego.  
  
 [Instrukcje: rozwiązywanie problemów z usługami](../extensibility/how-to-troubleshoot-services.md)  
 W tym artykule omówiono typowe problemy i przedstawia informacje o rozwiązaniach do nich.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)

