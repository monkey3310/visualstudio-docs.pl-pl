---
title: Priorytet projektu | Dokumentacja firmy Microsoft
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
- projects [Visual Studio SDK], opening items
ms.assetid: 9f707592-2fb6-4f75-9269-f6d4700a998e
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 57698e78c9228177e7f078cd725c1d4571e36d76
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691654"
---
# <a name="project-priority"></a>Priorytet projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [priorytet projektu](https://docs.microsoft.com/visualstudio/extensibility/internals/project-priority).  
  
Element projektu jest zazwyczaj członkiem tylko jednego projektu w rozwiązaniu. W związku z tym IDE może łatwo ustalić, który projekt jest używany do otwierania elementu. Jednak jeśli element jest członkiem więcej niż jeden projekt, IDE używa schematu priorytetu do określenia najlepsze projektu do otwierania elementu.  
  
 Na poniższej liście przedstawiono schemat priorytet projektu:  
  
-   Wywołania środowiska IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2.IsDocumentInProject%2A> metody dla każdego projektu w rozwiązaniu, aby ustalić, czy dokument jest członkiem tego projektu.  
  
-   Jeśli dokument jest członkiem projektu, projektu odpowiada za pomocą priorytet czy projektu przypisuje się zgodnie z jego obsługa tego dokumentu. Na przykład projekt języka odpowiada za pomocą wysoki priorytet dla jego plików źródłowych języka, ale odpowiada o niższym priorytecie typu nierozpoznanego pliku, który nie jest używany jako część procesu kompilacji.  
  
-   Projekty, które zapewniają projektantów lub edytorach niestandardowych, specyficzne dla projektu dla dokumentu otrzymają wysoki priorytet.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> Wyliczenia zawiera dokument wartości priorytetu.  
  
-   Projekt, który określa najwyższy priorytet otrzymuje kontekstu do otwierania tego dokumentu. Jeśli dwa projekty zwracają wartości w taki sam priorytet, aktywnego projektu jest preferowana. Jeśli brak projektu w rozwiązaniu odpowiada otworzyć dokument, IDE umieszcza dokument w projekcie różne pliki. Aby uzyskać więcej informacji, zobacz [projekt różne pliki](../../extensibility/internals/miscellaneous-files-project.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Projekt różne pliki](../../extensibility/internals/miscellaneous-files-project.md)   
 [Porady: otwieranie edytorów dla otwartych dokumentów](../../extensibility/how-to-open-editors-for-open-documents.md)   
 [Dodawanie projektu i szablonów elementów projektu](../../extensibility/internals/adding-project-and-project-item-templates.md)

