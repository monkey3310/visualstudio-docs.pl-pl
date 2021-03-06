---
title: 'Porady: włączenie ustawień zabezpieczeń technologii ClickOnce | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- security [Visual Studio], ClickOnce applications
- ClickOnce deployment, security settings
- security settings, ClickOnce deployment
ms.assetid: 73cd3e9d-cd72-4ad2-8cae-94d6bb6b01e0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f21b58a0ec9e8fe26cb02f72912fd23424cdfc7a
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39150940"
---
# <a name="how-to-enable-clickonce-security-settings"></a>Porady: włączenie ustawień zabezpieczeń technologii ClickOnce
Zabezpieczenia dostępu kodu dla aplikacji ClickOnce musi być włączony, aby można było opublikować aplikację. Odbywa się to automatycznie podczas publikowania aplikacji za pomocą Kreatora publikacji.  
  
 W niektórych przypadkach włączenie zabezpieczeń dostępu kodu może wpłynąć na wydajność podczas kompilowania lub debugowania aplikacji; w takich przypadkach mogą chcieć tymczasowo wyłączyć ustawienia zabezpieczeń.  
  
 Ustawień zabezpieczeń technologii ClickOnce można włączać lub wyłączać na **zabezpieczeń** strony **projektanta projektu**.  
  
### <a name="to-enable-clickonce-security-settings"></a>Aby włączyć ustawień zabezpieczeń technologii ClickOnce  
  
1.  Za pomocą projektu wybranego w **Eksploratora rozwiązań**na **projektu** menu, kliknij przycisk **właściwości**.  
  
2.  Kliknij przycisk **zabezpieczeń** kartę.  
  
3.  Wybierz **włączenia ustawień zabezpieczeń technologii ClickOnce** pole wyboru.  
  
     Możesz teraz dostosować ustawienia zabezpieczeń dla aplikacji na stronie zabezpieczenia.  
  
    > [!NOTE]
    >  To pole wyboru jest wybierana z każdym opublikowaniu aplikacji za pomocą **Publikuj** kreatora.  
  
### <a name="to-disable-clickonce-security-settings"></a>Aby wyłączyć ustawień zabezpieczeń technologii ClickOnce  
  
1.  Za pomocą projektu wybranego w **Eksploratora rozwiązań**na **projektu** menu, kliknij przycisk **właściwości**.  
  
2.  Kliknij przycisk **zabezpieczeń** kartę.  
  
3.  Wyczyść **włączenia ustawień zabezpieczeń technologii ClickOnce** pole wyboru.  
  
     Twoja aplikacja będzie uruchamiana za pomocą ustawień zabezpieczeń w trybie pełnego zaufania; wszystkie ustawienia na **zabezpieczeń** strony zostaną zignorowane.  
  
    > [!NOTE]
    >  Każdorazowo, gdy aplikacja została opublikowana przy użyciu Kreatora publikowania tego pola wyboru zostanie wybrany; należy usunąć je ponownie po każdej publikacji pomyślnie.  
  
## <a name="see-also"></a>Zobacz także  
 [Zabezpieczanie aplikacji ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpieczenia dostępu kodu dla aplikacji ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 
