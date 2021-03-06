---
title: Strona usług, Projektant projektu | Dokumentacja firmy Microsoft
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
- vb.ProjectPropertiesServices
helpviewer_keywords:
- Services page in Project Designer
- Project Designer, Services page
ms.assetid: 6dd9e0fa-acba-4d7d-b081-705b0fc86ff5
caps.latest.revision: 30
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d08052f52a7a9130b9809d6ffaa5fe801a9c668d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629610"
---
# <a name="services-page-project-designer"></a>Strona usług, Projektant projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Strona usług, Projektant projektu](https://docs.microsoft.com/visualstudio/ide/reference/services-page-project-designer).  
  
  
Usługi aplikacji klienta zapewniają uproszczony dostęp do [!INCLUDE[ajax_current_short](../../includes/ajax-current-short-md.md)] logowania, ról i usług profilu z aplikacji Windows Forms i Windows Presentation Foundation (WPF). Możesz użyć **usług** strony **projektanta projektu** Włączanie i konfigurowanie usług aplikacji klienckich dla Twojego projektu.  
  
 Przy użyciu usług aplikacji klienta centralny serwer służy do uwierzytelniania użytkowników, określić każdy użytkownik przypisaną rolę lub role i przechowywać ustawienia aplikacji na użytkownika, które można udostępniać w sieci. Aby uzyskać więcej informacji, zobacz [usług aplikacji klienta](http://msdn.microsoft.com/library/1487d8df-089e-4f21-abfb-a791a652b58e).  
  
 Aby uzyskać dostęp do **usług** wybierz węzeł projektu w **Eksploratora rozwiązań**, a następnie kliknij przycisk **właściwości** na **projektu** menu. Podczas **projektanta projektu** zostanie wyświetlona, kliknij przycisk **usług** kartę.  
  
> [!NOTE]
>  Usługi aplikacji klienta wymaga pełnej wersji programu .NET Framework i nie są obsługiwane w programie .NET Framework Client Profile. Jeśli **włączyć usługi aplikacji klienckiej** pole wyboru jest wyłączone, upewnij się, że **platformę docelową** jest ustawiony do wersji programu .NET Framework 3.5 lub nowszej. Aby wyświetlić **platformę docelową** ustawienie w języku C#, otwórz projektanta projektu, a następnie kliknij przycisk **aplikacji** strony. Aby wyświetlić **platformę docelową** ustawienie w języku Visual Basic, otwórz projektanta projektu, kliknij przycisk **skompilować** strony, a następnie kliknij przycisk **zaawansowane opcje kompilacji**.  
  
## <a name="task-list"></a>Lista zadań  
 [Instrukcje: konfigurowanie usług aplikacji klienckich](http://msdn.microsoft.com/library/34a8688a-a32c-40d3-94be-c8e610c6a4e8)  
  
## <a name="uielement-list"></a>Lista elementów UI  
 **Konfiguracja**  
 Ta kontrolka nie jest edytowalny na tej stronie. Aby uzyskać opis tego formantu, zobacz [strona kompilowania, Projektant projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) lub [Stroka kompilacji, Projektant projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Platforma**  
 Ta kontrolka nie jest edytowalny na tej stronie. Aby uzyskać opis tego formantu, zobacz [strona kompilowania, Projektant projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) lub [Stroka kompilacji, Projektant projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Włączyć usługi aplikacji klienckiej**  
 Zaznacz, aby włączyć usługi aplikacji klienckiej. Należy określić lokalizacje usługi na **usług** strony do użycia usług aplikacji klienta.  
  
 **Uwierzytelnianie Windows**  
 Wskazuje, że dostawca uwierzytelniania będzie używać uwierzytelniania opartego na Windows, czyli tożsamości dostarczonych przez system operacyjny Windows.  
  
 **Korzystanie z uwierzytelniania formularzy**  
 Wskazuje, że dostawca uwierzytelniania będzie używać uwierzytelniania formularzy. Oznacza to, że aplikacji należy podać interfejsu użytkownika dla nazwy logowania. Aby uzyskać więcej informacji, zobacz [porady: Implementowanie logowania użytkownika przy użyciu usług aplikacji klienta](http://msdn.microsoft.com/library/5431a671-eb02-4e18-a651-24764fccec9a).  
  
 **Lokalizacja usługi uwierzytelniania**  
 Używany tylko z uwierzytelniania formularzy. Określa lokalizację usługi uwierzytelniania.  
  
 **Opcjonalne: Dostawca poświadczeń**  
 Używany tylko z uwierzytelniania formularzy. Wskazuje <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> implementacji, które będzie używane przez usługę uwierzytelniania, aby wyświetlić okno dialogowe logowania, gdy Twoja aplikacja wywołuje `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> metody i przekazuje puste ciągi lub `null` dla parametrów. Jeśli to pole pozostanie puste, należy podać prawidłową nazwę użytkownika i hasło, aby <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> metody. Dostawca poświadczeń należy określić nazwę typu kwalifikowanego zestawu. Aby uzyskać więcej informacji, zobacz <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName> i [nazw zestawów](http://msdn.microsoft.com/library/8f8c2c90-f15d-400e-87e7-a757e4f04d0e). W najprostszej postaci nazwę typu kwalifikowanego zestawu wyglądają podobnie do poniższego przykładu: `MyNamespace.MyLoginClass, MyAssembly`  
  
 **Lokalizacja usługi ról**  
 Określa lokalizację usługi ról.  
  
 **Ustawienia sieci Web usługi lokalizacji**  
 Określa lokalizację usługi profilu (ustawienia internetowe).  
  
 **Zaawansowane**  
 Otwiera [Zaawansowane ustawienia dla usług, okno dialogowe](../../ide/reference/advanced-settings-for-services-dialog-box.md), którego można użyć, aby zastąpić domyślne zachowanie. Na przykład służy to okno dialogowe, aby określić bazę danych magazynu offline, zamiast korzystać z lokalnego systemu plików. Aby uzyskać więcej informacji, zobacz [Zaawansowane ustawienia dla usług, okno dialogowe](../../ide/reference/advanced-settings-for-services-dialog-box.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Usługi aplikacji klienta](http://msdn.microsoft.com/library/1487d8df-089e-4f21-abfb-a791a652b58e)   
 [Zaawansowane ustawienia dla usług, okno dialogowe](../../ide/reference/advanced-settings-for-services-dialog-box.md)   
 [Porady: Konfigurowanie usług aplikacji klienta](http://msdn.microsoft.com/library/34a8688a-a32c-40d3-94be-c8e610c6a4e8)   
 [Strona kompilowania, Projektant projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Strona kompilacji, Projektant projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md)   
 [Wprowadzenie do projektanta projektu](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)



