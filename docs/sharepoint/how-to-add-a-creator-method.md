---
title: 'Porady: Dodawanie metody Creator | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], Creator
- BDC [SharePoint development in Visual Studio], adding entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entity instances
- BDC [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Creator
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 353d834ccd32376b53c875be356865711a4f89fd
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757243"
---
# <a name="how-to-add-a-creator-method"></a>Porady: Dodawanie metody Creator
  Metody Creator dodaje nowe dane do źródła danych jednostki. Usługa łączności danych biznesowych (BDC) wywołuje tę metodę, gdy użytkownicy wybiorą **nowy element** znajdującego się na **wstążki** listy, która jest oparta na modelu. Aby uzyskać więcej informacji, zobacz [projektowanie modelu łączności danych biznesowych](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-add-a-creator-method"></a>Aby dodać metody Creator  
  
1.  Na **projektanta BDC**, wybierz jednostki.  
  
2.  Na pasku menu wybierz **widoku** > **inne okna** >**szczegóły metody usługi łączności danych biznesowych**.  
  
     **Szczegóły metody usługi łączności danych biznesowych** zostanie otwarte okno. Aby uzyskać więcej informacji dotyczących tego okna, zobacz [omówienie narzędzi projektowania modelu BDC](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  W **Dodaj metodę** wybierz **Utwórz metody Creator**.  
  
     Visual Studio dodaje następujące elementy do modelu, a te elementy są wyświetlane w **szczegóły metody usługi łączności danych biznesowych** okna.  
  
    -   Metodę o nazwie **Utwórz**.  
  
    -   Parametr wejściowy dla metody.  
  
    -   Parametr zwrotnego dla metody.  
  
    -   Wpisz deskryptory parametrów.  
  
    -   Wystąpienia metody dla metody.  
  
     Aby uzyskać więcej informacji, zobacz [projektowanie modelu łączności danych biznesowych](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
4.  W **Eksploratora rozwiązań**, otwórz menu skrótów w pliku kodu usługi, który został wygenerowany dla obiektu, a następnie wybierz **kod widoku**.  
  
     Plik kodu usługi jednostki zostanie otwarty w edytorze kodu. Aby uzyskać więcej informacji o pliku kodu usługi jednostki, zobacz [Tworzenie modelu łączności danych biznesowych](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
5.  Dodaj kod do metody Creator, która dodaje dane do źródła danych. W następującym przykładzie dodano skontaktuj się z przykładową bazą danych AdventureWorks programu SQL Server.  
  
    > [!NOTE]  
    >  Zastąp wartość `ServerName` nazwę serwera.  
  
     [!code-csharp[SP_BDC#4](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#4)]
     [!code-vb[SP_BDC#4](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#4)]  
  
## <a name="see-also"></a>Zobacz także
 [Projektowanie modelu łączności danych biznesowych](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Porady: Dodawanie metody wyszukiwania](../sharepoint/how-to-add-a-finder-method.md)   
 [Porady: Dodawanie określonej metody wyszukiwania](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Porady: Dodawanie metody Deleter](../sharepoint/how-to-add-a-deleter-method.md)   
 [Porady: Dodawanie metody Updater](../sharepoint/how-to-add-an-updater-method.md)   
 [Omówienie narzędzi projektowania modelu BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Porady: Dodawanie parametru do metody](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Porady: Definiowanie wystąpienia metody](../sharepoint/how-to-define-a-method-instance.md)  
  
  
