---
title: Pliki elementu | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Files element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 37fc7bb582482f645fe5699196ca33d79304a5c3
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2018
ms.locfileid: "36327297"
---
# <a name="files-element"></a>Element Pliki
  Określa pliki do wdrożenia z elementu projektu SharePoint, takich jak funkcja elementu pliki i dane wyjściowe projektów zależnych programu SharePoint.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<Files>  
  <ProjectItemFile.../>  
  <ProjectOutputFile.../>  
</Files>  
```  
  
## <a name="type"></a>Typ  
 **FileCollectionType**  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne
  
|Element|Opis|  
|-------------|-----------------|  
|[Projectitemfile —](../sharepoint/projectitemfile-element.md)|Opcjonalne **ProjectItemFileType** elementu.<br /><br /> Reprezentuje plik programu SharePoint, takich jak plik element funkcji, aby dołączyć z elementem projektu po wdrożeniu programu SharePoint.|  
|[Projectoutputfile —](../sharepoint/projectoutputfile-element.md)|Opcjonalne **ProjectOutputFileType** elementu.<br /><br /> Reprezentuje dane wyjściowe projektu do dołączenia do elementu projektu po wdrożeniu programu SharePoint.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne
  
|Element|Opis|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Reprezentuje element projektu programu SharePoint. Ten element wymaganego głównego elementu z `.spdata` pliku.|  
  
## <a name="element-information"></a>Informacje o elementach
  
|||  
|-|-|  
|**Namespace**|http<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**Nazwa schematu**|Schemat elementu projektu SharePoint|  
|**Sprawdzanie poprawności pliku**|ProjectItemModelSchema.xsd|  
|**Może być pusta.**|Nie|  
  
## <a name="see-also"></a>Zobacz także
 [Odwołanie do schematu elementu projektu SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  
