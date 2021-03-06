---
title: Rejestrowanie rozszerzeń środowiska .NET Framework | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 0017255b67042a7e42b54325b24512a295ebeaf5
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/20/2018
ms.locfileid: "39180155"
---
# <a name="register-extensions-of-the-net-framework"></a>Rejestrowanie rozszerzeń środowiska .NET Framework
Można opracować zestaw, który rozszerza określonej wersji programu .NET Framework. Aby włączyć zestawu są wyświetlane w programie Visual Studio **Add References** okno dialogowe, należy dodać folder, który zawiera go do rejestru systemowego.  
  
 Na przykład załóżmy, że firma Trey Research przygotowała bibliotekę, która rozszerza programu .NET Framework 4 i chce zestawy bibliotek, które pojawią się w **Add References** okno dialogowe, jeśli projekt jest przeznaczony dla .NET Framework 4. Również założono, że zestawów 32-bitowych uruchomiony na komputerze 32-bitowy lub 64-bitowych zestawów uruchomionego na komputerze 64-bitowe są zestawy i że zostaną zainstalowane w *C:\TreyResearch\Extensions4\\*  folderu.  
  
 Zarejestruj ten folder przy użyciu tego klucza: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\**. Nadaj klucza to wartość domyślna: **C:\TreyResearch\Extensions4**.  
  
> [!NOTE]
>  Numer kompilacji programu .NET Framework w wersji może się różnić.  
  
 Aby zarejestrować zestaw 32-bitowego na komputerze 64-bitowym, za pomocą Wow6432 węzła, na przykład: **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\**.  
  
### <a name="see-also"></a>Zobacz także  
 [Integracja z programem Visual Studio](../msbuild/visual-studio-integration-msbuild.md)