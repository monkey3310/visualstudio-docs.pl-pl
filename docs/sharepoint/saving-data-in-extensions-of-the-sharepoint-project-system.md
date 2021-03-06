---
title: Zapisywanie danych w rozszerzeniach systemu projektu SharePoint | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
helpviewer_keywords:
- SharePoint project items, saving string data
- project items [SharePoint development in Visual Studio], saving string data
- projects [SharePoint development in Visual Studio], saving string data
- SharePoint projects, saving string data
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 74228b5259b733c91397eb1b40a2485daea8b79e
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120327"
---
# <a name="save-data-in-extensions-of-the-sharepoint-project-system"></a>Zapisywanie danych w rozszerzeniach systemu projektu SharePoint
  Podczas rozszerzania systemu projektu SharePoint można zapisać danych ciąg będzie nadal występować po zamknięciu projektu programu SharePoint. Dane są zwykle skojarzone z elementem określonego projektu lub z samym projekcie.  
  
 Jeśli masz dane, które nie jest konieczne będą się powtarzać, można dodać danych do każdego obiektu w modelu obiektów programu SharePoint narzędzia, która implementuje <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject> interfejsu. Aby uzyskać więcej informacji, zobacz [rozszerzeń narzędzi kojarzenie danych niestandardowych z programem SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
## <a name="save-data-that-is-associated-with-a-project-item"></a>Zapisz dane skojarzone z elementem projektu
 Jeśli masz dane skojarzone z określonego elementu projektu SharePoint, takiego jak wartość właściwości, które można dodać do elementu projektu można zapisać danych do *.spdata —* pliku dla elementu projektu. Aby to zrobić, użyj <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> właściwość <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> obiektu. Danymi dodawanymi do tej właściwości jest zapisywany w **extensiondata —** element *.spdata —* pliku dla elementu projektu. Aby uzyskać więcej informacji, zobacz [extensiondata — Element](../sharepoint/extensiondata-element.md).  
  
 Poniższy przykład kodu pokazuje sposób użycia <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> właściwości można zapisać wartości właściwości ciągu, który jest zdefiniowany w niestandardowego typu elementu projektu SharePoint. Aby wyświetlić ten przykład w kontekście większego przykładu, zobacz [porady: Dodawanie właściwości do niestandardowego typu elementu projektu SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md).  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#14)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#14)]  
  
## <a name="save-data-that-is-associated-with-a-project"></a>Zapisz dane skojarzone z projektem
 Jeśli masz dane na poziomie projektu, takie jak wartości właściwości, które dodajesz do projektów SharePoint można zapisać danych do pliku projektu ( *.csproj* pliku lub *vbproj* pliku) lub opcji użytkownika projektu plik ( *. csproj.user* pliku lub *. vbproj.user* pliku). Plik, który chcesz zapisać dane w zależy od sposobu danych do użycia:  
  
-   Jeśli dane mają być dostępne dla wszystkich deweloperów, którzy Otwórz projekt programu SharePoint, należy zapisać danych do pliku projektu. Ten plik jest zawsze ewidencjonowane bazy danych kontroli źródła, więc dane w tym pliku są dostępne dla innych deweloperów, którzy wyewidencjonować projektu.  
  
-   Jeśli dane mają być dostępne tylko dla bieżącego projektanta, który ma projekt SharePoint jest otwarty w programie Visual Studio, należy zapisać danych do pliku opcji użytkownika projektu. Ten plik nie jest zazwyczaj sprawdzana do bazy danych kontroli źródła, więc dane w tym pliku nie jest dostępne dla innych deweloperów, którzy wyewidencjonować projektu.  
  
### <a name="save-data-to-the-project-file"></a>Zapisywanie danych w pliku projektu
 Można zapisać danych w pliku projektu, należy przekonwertować <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> do obiektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> obiekt, a następnie użyj <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> metody. Poniższy przykład kodu pokazuje, jak użyć tej metody można zapisać wartości właściwości projektu w pliku projektu. Aby wyświetlić ten przykład w kontekście większego przykładu, zobacz [porady: Dodawanie właściwości do projektów SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md).  
  
 [!code-vb[SpExt_SPCustomPrjProperty#3](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#3)]
 [!code-csharp[SpExt_SPCustomPrjProperty#3](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#3)]  
  
 Aby uzyskać więcej informacji na temat konwertowania <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> obiektów do innych typów w modelu obiektu automatyzacji programu Visual Studio lub model obiektów integracji, zobacz [konwersji między typami systemu projektu SharePoint a innymi typami projektu Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).  
  
### <a name="save-data-to-the-project-user-option-file"></a>Zapisywanie danych w pliku opcji użytkownika projektu
 Aby zapisać danych do pliku projektu użytkownika opcji, należy użyć <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectUserFileData%2A> właściwość <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> obiektu. Poniższy przykład kodu pokazuje, jak użyć tej właściwości można zapisać wartości właściwości projektu w pliku opcji użytkownika projektu. Aby wyświetlić ten przykład w kontekście większego przykładu, zobacz [porady: Dodawanie właściwości do projektów SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md).  
  
 [!code-vb[SpExt_SPCustomPrjProperty#2](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#2)]
 [!code-csharp[SpExt_SPCustomPrjProperty#2](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#2)]  
  
## <a name="see-also"></a>Zobacz także
 [Rozszerzanie systemu projektu SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Kojarzenie danych niestandardowych z rozszerzeniami narzędzi SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)   
 [Konwertowanie pomiędzy typami systemu projektu SharePoint a innymi typami projektu Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)  
  
