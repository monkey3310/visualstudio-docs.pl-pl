---
title: Itemmetadata — Element (MSBuild) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemMetadata Element [MSBuild]
- <ItemMetadata> Element [MSBuild]
ms.assetid: e3db5122-202d-43a9-b2f4-3e0ec4ed3d08
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 78e9bfffc38ac54ec7aeb525665dc7e3a8927f74
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2018
ms.locfileid: "39080492"
---
# <a name="itemmetadata-element-msbuild"></a>Itemmetadata — element (MSBuild)
Zawiera klucz metadanych zdefiniowanych przez użytkownika elementu, który zawiera wartość metadanych elementu. Element może mieć dowolną liczbę par klucz wartość metadanych.  

 \<Project>  
 \<ItemGroup>  
 \<Element >  

## <a name="syntax"></a>Składnia  

```xml  
<ItemMetadataName> Item Metadata value</ItemMetadataName>  
```  

## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  

### <a name="attributes"></a>Atrybuty  

|Atrybut|Opis|  
|---------------|-----------------|  
|`Condition`|Atrybut opcjonalny.<br /><br /> Warunek, który ma zostać obliczone. Aby uzyskać więcej informacji, zobacz [warunki](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  

### <a name="parent-elements"></a>Elementy nadrzędne  

|Element|Opis|  
|-------------|-----------------|  
|[Element](../msbuild/item-element-msbuild.md)|Element zdefiniowany przez użytkownika, który definiuje dane wejściowe dla procesu kompilacji.|  

## <a name="text-value"></a>Wartość tekstowa  
 Wartość tekstowa jest opcjonalna.  

 Ten tekst Określa wartość elementu metadanych, które mogą być tekstem lub XML.  

## <a name="example"></a>Przykład  
 W poniższym przykładzie kodu przedstawiono sposób dodawania `Culture` metadanych z wartością `fr` do elementu `CSFile`.  

```xml  
<ItemGroup>  
    <CSFile Include="main.cs" >  
        <Culture>fr</Culture>  
    </CSFile>  
</ItemGroup>  
```  

## <a name="see-also"></a>Zobacz także  
 [Odwołanie do schematu pliku projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Elementy](../msbuild/msbuild-items.md)
