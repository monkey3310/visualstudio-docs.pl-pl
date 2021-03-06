---
title: Defaultname — Element (szablony Visual Studio) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#DefaultName
helpviewer_keywords:
- DefaultName element [Visual Studio project templates]
ms.assetid: 0ff056c8-b9d2-4747-9308-92adf1811491
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 967bc0a21d9cf860baaff9fa9185c4f4bd81f463
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633522"
---
# <a name="defaultname-element-visual-studio-templates"></a>DefaultName — Element (szablony Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [defaultname — Element (szablony Visual Studio)](https://docs.microsoft.com/visualstudio/extensibility/defaultname-element-visual-studio-templates).  
  
Określa nazwę, który zostanie wygenerowany przez system projektu programu Visual Studio dla projektu lub elementu, podczas jego tworzenia.  
  
 \<VSTemplate>  
 \<TemplateData >  
 \<Defaultname — >  
  
## <a name="syntax"></a>Składnia  
  
```  
<DefaultName>  
    Default Project Name  
</DefaultName>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Element wymagany.<br /><br /> Klasyfikuje szablon i definiuje sposób wyświetlania albo **nowy projekt** lub **Dodaj nowy element** okno dialogowe.|  
  
## <a name="text-value"></a>Wartość tekstowa  
 Wartość tekstowa jest wymagana.  
  
 Ten tekst Określa domyślną nazwę projektu lub elementu.  
  
## <a name="remarks"></a>Uwagi  
 `DefaultName` element jest opcjonalny.  
  
 W przypadku projektów ten element Określa nazwę katalogu, który przechowuje projektu na dysku. Dla elementów Określa nazwę pliku w pliku źródłowym.  
  
 Podczas tworzenia projektu lub elementu, można modyfikować przy użyciu nazwy domyślnej **nazwa** opcja, która jest dostępna z poziomu **nowy projekt** okno dialogowe lub **Dodaj nowy element** okno dialogowe.  
  
 Jeśli użytkownik nie chce, aby system projektu ma generować domyślna nazwa projektu lub elementu, wartość [providedefaultname —](../extensibility/providedefaultname-element-visual-studio-templates.md) elementu `False`.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie pokazano metadanych dla szablonu elementu standardowego dla [!INCLUDE[csprcs](../includes/csprcs-md.md)] klasy.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <DefaultName>MyClass.cs</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem ReplaceParameters="true">MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do schematu szablonu Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Tworzenie szablonów projektu i elementu](../ide/creating-project-and-item-templates.md)

