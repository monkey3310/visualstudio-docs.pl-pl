---
title: Korzystanie z programu MSBuild | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, compiling with MSBuild
- MSBuild, extensibility
- packages, compiling with MSBuild
ms.assetid: 9d38c388-1f64-430e-8f6c-e88bc99a4260
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f27d3c5c7465314a7e9005972dec1349c1b9d89f
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902234"
---
# <a name="using-msbuild"></a>Korzystanie z programu MSBuild
Program MSBuild, dostarcza dobrze zdefiniowanych, rozszerzalne formatu XML do tworzenia plików projektów, które w pełni opisuje elementy projektu do zbudowania zadania kompilacji i konfiguracje kompilacji.  
  
## <a name="general-msbuild-considerations"></a>Zagadnienia ogólne MSBuild  
 Pliki projektów programu MSBuild, na przykład [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] .csproj i [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] .vbproj pliki zawierają dane, które są używane w czasie kompilacji, ale może również zawierać dane, które są używane w czasie projektowania. Dane w czasie kompilacji jest przechowywany przy użyciu programu MSBuild w nim elementów podstawowych, w tym [Item — Element (MSBuild)](../../msbuild/item-element-msbuild.md) i [Property — Element (MSBuild)](../../msbuild/property-element-msbuild.md). Dane czasu projektowania, które są specyficzne dla typów projektów i wszelkie podtypy projektów powiązane dane, są przechowywane w dowolnej postaci XML zarezerwowano dla niej.  
  
 Program MSBuild nie zapewniają natywnej obsługi dla obiektów konfiguracji, ale zapewnia atrybuty warunkowe do określania danych specyficznych dla konfiguracji. Na przykład:  
  
```xml  
<OutputDir Condition="'$(Configuration)'=="release'">Bin\MyReleaseConfig</OutputDir>  
```  
  
 Aby uzyskać więcej informacji na temat atrybuty warunkowe, zobacz [konstrukcje warunkowe](../../msbuild/msbuild-conditional-constructs.md).  
  
### <a name="extending-msbuild-for-your-project-type"></a>Rozszerzanie programu MSBuild dla danego typu projektu  
 MSBuild interfejsów i interfejsy API mogą ulec zmianie w przyszłych wersjach programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. W związku z tym rozsądne jest używać klas framework (MPF) zarządzanego pakietu, ponieważ zapewniają one osłony przed zmianami.  
  
 Środowiska pakietu zarządzanego dla projektów (MPFProj) udostępnia klasy pomocy do tworzenia i zarządzania nowy system projektów. Instrukcje można znaleźć źródła kodu i kompilacji w [MPF projektów — Visual Studio 2013](https://github.com/tunnelvisionlabs/MPFProj10).  
  
 Klasy MPF specyficzne dla projektu są następujące:  
  
|Class|Implementacja|  
|-----------|--------------------|  
|`Microsoft.VisualStudio.Package.ProjectNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents>|  
|`Microsoft.VisualStudio.Package.ProjectFactory`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|  
|`Microsoft.VisualStudio.Package.HierarchyNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|  
|`Microsoft.VisualStudio.Package.ProjectConfig`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|  
|`Microsoft.VisualStudio.Package.SettingsPage`|<xref:Microsoft.VisualStudio.OLE.Interop.IPropertyPageSite>|  
  
 `Microsoft.VisualStudio.Package.ProjectElement` Klasa jest otoką elementy programu MSBuild.  
  
#### <a name="single-file-generators-vs-msbuild-tasks"></a>Vs generatory pojedynczego pliku. Zadania programu MSBuild  
 Pojedynczy plik generatory są dostępne — tylko w czasie projektowania, ale zadania programu MSBuild może być używany w czasie projektowania i w czasie kompilacji. Aby zapewnić maksymalną elastyczność dlatego należy użyć zadania programu MSBuild do przekształcania i generowanie kodu. Aby uzyskać więcej informacji, zobacz [narzędzia niestandardowe](../../extensibility/internals/custom-tools.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do narzędzia MSBuild](../../msbuild/msbuild-reference.md)   
 [Program MSBuild](../../msbuild/msbuild.md)   
 [Narzędzia niestandardowe](../../extensibility/internals/custom-tools.md)