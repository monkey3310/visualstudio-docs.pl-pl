---
title: Tworzenie prostej aplikacji danych z WPF i Entity Framework 6
ms.date: 08/22/2017
ms.topic: conceptual
dev_langs:
- CSharp
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c39546d48cd8b8bf71594685f944751c1f023750
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117813"
---
# <a name="create-a-simple-data-application-with-wpf-and-entity-framework-6"></a>Tworzenie prostej aplikacji danych z WPF i Entity Framework 6

W tym przewodniku przedstawiono sposób tworzenia aplikacji podstawowe "formularzy nad danymi" w programie Visual Studio. Aplikacja korzysta z bazy danych LocalDB programu SQL Server, bazy danych Northwind, Entity Framework 6 i Windows Presentation Foundation. Widoczny jest sposób czy podstawowe wiązanie danych z widoku główny szczegółowy i ma również niestandardowe Nawigator powiązania z przycisków dla **Przenieś następny**, **Przenieś poprzedniej**, **Przenieś na początek**, **Przenieś na koniec**, **aktualizacji** i **usunąć**.

Ten artykuł koncentruje się na temat używania narzędzia danych w programie Visual Studio i nie jest podejmowana próba wyjaśniono podstawowe technologie w dowolnym poziomie. Przyjęto założenie, że podstawowa znajomość języka XAML, Entity Framework i SQL. W tym przykładzie nie potwierdzają również architektury Model-View-ViewModel (MVVM), który jest standardem aplikacji WPF. Można jednak skopiować ten kod do własnych aplikacji MVVM z kilku zmian.

## <a name="install-and-connect-to-northwind"></a>Zainstaluj i połącz się Northwind

W tym przykładzie używa programu SQL Server Express LocalDB i przykładowej bazy danych Northwind. Jeśli dostawca danych ADO.NET dla tego produktu obsługuje programu Entity Framework, powinien działać z innymi produktami bazy danych SQL równie dobrze.

1.  Jeśli nie masz programu SQL Server Express LocalDB, zainstaluj go z [strony pobierania programu SQL Server Express](https://www.microsoft.com/sql-server/sql-server-editions-express), lub za pomocą **Instalator programu Visual Studio**. W **Instalator programu Visual Studio**, można zainstalować programu SQL Server Express LocalDB w ramach **tworzenia klasycznych aplikacji .NET** obciążenia lub jako poszczególnych składników.

2.  Instalowanie przykładowej bazy danych Northwind, wykonaj następujące czynności:

    1. W programie Visual Studio Otwórz **Eksplorator obiektów SQL Server** okna. (**Eksplorator obiektów SQL Server** jest instalowany jako część **magazynu danych i przetwarzania** obciążeń w **Instalator programu Visual Studio**.) Rozwiń węzeł **programu SQL Server** węzła. Kliknij prawym przyciskiem myszy w wystąpieniu bazy danych LocalDB, a następnie wybierz **nowe zapytanie**.

       Zostanie otwarte okno edytora zapytań.

    2. Kopiuj [skryptu języka Transact-SQL Northwind](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do Schowka. Ten skrypt T-SQL utworzy bazę danych Northwind od początku i wypełnia danych.

    3. Wkleić skryptu T-SQL w edytorze zapytań, a następnie wybierz pozycję **Execute** przycisku.

       Po pewnym czasie zakończeniu zapytania i utworzeniu bazy danych Northwind.

3.  [Dodaj nowe połączenia](../data-tools/add-new-connections.md) dla Northwind.

## <a name="configure-the-project"></a>Konfigurowanie projektu

1.  W programie Visual Studio, wybierz **pliku** > **nowy** > **projektu** , a następnie utwórz nową aplikację WPF C#.

2.  Następnie dodaj pakiet NuGet dla programu Entity Framework 6. W **Eksploratora rozwiązań**, wybierz węzeł projektu. W menu głównym wybierz **projektu** > **Zarządzaj pakietami NuGet**.

     ![Zarządzanie pakietami NuGet elementu menu](../data-tools/media/raddata_vs2015_manage_nuget_packages.png)

3.  W **Menedżera pakietów NuGet**, kliknij **Przeglądaj** łącza. Entity Framework jest prawdopodobnie pakiet na liście. Kliknij przycisk **zainstalować** w okienku po prawej stronie i postępuj zgodnie z monitami. W oknie danych wyjściowych informuje, po zakończeniu instalacji.

     ![Pakiet NuGet programu Entity Framework](../data-tools/media/raddata_vs2015_nuget_ef.png)

4.  Teraz można używać programu Visual Studio do utworzenia modelu na podstawie bazy danych Northwind.

## <a name="create-the-model"></a>Tworzenie modelu

1.  Kliknij prawym przyciskiem myszy węzeł projektu w Eksploratorze rozwiązań i wybierz polecenie **Dodaj** > **nowy element**. W okienku po lewej stronie w węźle C#, wybierz **danych** i w środkowym okienku wybierz **modelu danych jednostki ADO.NET**.

     ![Entity Framework modelu nowego elementu projektu](../data-tools/media/raddata-ef-new-project-item.png)

  2.  Wywołanie modelu `Northwind_model` i wybierz polecenie **OK**. **Kreatora modelu danych jednostki** otwiera. Wybierz **EF Designer z bazy danych** , a następnie kliknij przycisk **dalej**.

     ![Model EF z bazy danych](../data-tools/media/raddata-ef-model-from-database.png)

3.  Na następnym ekranie, wybierz użytkownika LocalDB Northwind połączeń i kliknij przycisk **dalej**.

4.  Na następnej stronie kreatora wybierz tabele, procedury składowane i inne obiekty bazy danych do uwzględnienia w modelu Entity Framework. Rozwiń węzeł dbo w widoku drzewa, a następnie wybierz **klientów**, **zamówień**, i **szczegółów zamówienia**. Pozostaw zaznaczone domyślne i kliknij przycisk **Zakończ**.

     ![Wybierz obiekty bazy danych dla modelu](../data-tools/media/raddata-choose-ef-objects.png)

5.  Kreator generuje klas C#, które reprezentują modelu programu Entity Framework. Klasy są zwykły starego klasy C# i jakie firma Microsoft są databind WPF interfejsu użytkownika. *Edmx* plik zawiera opis relacji i innych metadanych, które kojarzy klas obiektów w bazie danych. *.TT —* pliki są szablony T4, które generują kod, który działa w modelu, a następnie zapisz zmiany w bazie danych. Te pliki w można wyświetlić **Eksploratora rozwiązań** w węźle Northwind_model:

       ![Pliki modelu EF w Eksploratorze rozwiązania](../data-tools/media/raddata-solution-explorer-ef-model-files.png)

     Powierzchnię projektanta dla *edmx* pliku umożliwia modyfikowanie niektórych właściwości i relacje w modelu. Firma Microsoft nie będą w tym przewodniku za pomocą projektanta.

6.  *.TT —* pliki są ogólnego przeznaczenia, należy dostosować jeden z nich do pracy z WPF wiązania z danymi, które wymaga ObservableCollections. W **Eksploratora rozwiązań**, rozwiń węzeł Northwind_model do momentu znalezienia *Northwind_model.tt*. (Upewnij się, że nie jesteś w *. Context.TT* pliku, który jest bezpośrednio poniżej *edmx* pliku.)

    -   Zastąp dwa wystąpienia <xref:System.Collections.ICollection> z <xref:System.Collections.ObjectModel.ObservableCollection%601>.

    -   Zamień na pierwsze wystąpienie <xref:System.Collections.Generic.HashSet%601> z <xref:System.Collections.ObjectModel.ObservableCollection%601> wokół wiersza 51. Nie zastępuj drugie wystąpienie zestaw HashSet.

    -   Zastąpić tylko wystąpienie <xref:System.Collections.Generic> (około wiersza 431) z <xref:System.Collections.ObjectModel>.

7.  Naciśnij klawisz **Ctrl**+**Shift**+**B** Aby skompilować projekt. Po zakończeniu kompilacji klasy modelu są widoczne w Kreatorze źródła danych.

Teraz można przystąpić do Podłączanie tego modelu do strony XAML, dzięki czemu można wyświetlać, przejdź i modyfikować dane.

## <a name="databind-the-model-to-the-xaml-page"></a>DataBind modelu do strony XAML

Można napisać własny kod wiązania danych, ale jest znacznie łatwiejsze umożliwić programowi Visual Studio zrobił dla Ciebie.

1.  W menu głównym wybierz **projektu** > **Dodaj nowe źródło danych** można wyświetlić **Kreator konfiguracji źródła danych**. Wybierz **obiektu** ponieważ dokonywane jest wiązanie dla klasy modelu nie do bazy danych:

     ![Kreator konfiguracji źródła danych z obiektu źródłowego](../data-tools/media/raddata-data-source-configuration-wizard-with-object-source.png)

2.  Wybierz **klienta**. (Źródeł dla zleceń są automatycznie generowane z właściwości nawigacji zamówień klientów).

     ![Dodawanie klas jednostek jako źródła danych](../data-tools/media/raddata-add-entity-classes-as-data-sources.png)

3.  Kliknij przycisk **Zakończ**.

4.  Przejdź do *MainWindow.xaml* w widoku kodu. Firma Microsoft jest zachowywana XAML prostego na potrzeby tego przykładu. Zmień tytuł okna głównego na coś bardziej opisowe i zwiększyć jej wysokości i szerokości do 600 x 800 teraz. Zawsze można zmienić go później. Teraz Dodaj te definicje trzech wierszy do głównego siatki, jeden wiersz przycisków nawigacji, dla szczegóły klienta, a drugi w siatce, pokazujący ich zleceń:

    ```xaml
    <Grid.RowDefinitions>
            <RowDefinition Height="auto"/>
            <RowDefinition Height="auto"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
    ```

5.  Teraz otworzyć *MainWindow.xaml* tak, aby wyświetlanych w projektancie. Powoduje to **źródeł danych** okna są wyświetlane jako opcja na marginesie okno programu Visual Studio **przybornika**. Kliknij kartę, aby otworzyć okno lub #else naciśnij **Shift**+**Alt**+**D** lub wybierz **widoku**  >  **Innych okien** > **źródeł danych**. Zamierzamy do wyświetlania każdej właściwości w klasie klientów w jego własnej poszczególnych tekst. Po pierwsze, kliknij strzałkę w **klientów** kombi polu i wybierz polecenie **szczegóły**. Następnie przeciągnij węzeł środkowej części powierzchni projektu, aby projektanta wie, czy chcesz, aby przejść w środkowej wiersza. Jeśli użytkownik misplace go, można określić wiersz ręcznie później w kodzie XAML. Domyślnie przez formanty są umieszczane w pionie w elemencie siatki, ale w tym momencie można rozmieścić je jednak na formularzu, takich jak. Na przykład może być uzasadnione, aby umieścić **nazwa** pole tekstowe u góry powyżej adres. Przykładowa aplikacja dla tego artykułu zmienia kolejność pól i rozmieszcza je na dwie kolumny.

     ![Powiązanie źródła danych klientów do pojedynczych formantów](../data-tools/media/raddata-customers-data-source-binding-to-individual-controls.png)

     W widoku kodu można przeglądać nowy `Grid` elementu w wierszu 1 (środkową wiersz) nadrzędnego elementu siatki. Element nadrzędny ma siatki `DataContext` atrybut, który odwołuje się do CollectionViewSource, dodawanej do `Windows.Resources` elementu. Podane tego kontekstu danych po pierwszym polu wiąże **adres**, ta nazwa jest mapowany na `Address` właściwość w bieżącej `Customer` obiektu w CollectionViewSource.

    ```xaml
    <Grid DataContext="{StaticResource customerViewSource}">
    ```

6.  Gdy klient jest widoczna w górnej połowie okna, chcesz zobaczyć jego zamówienia w dolnej połowie. Możesz wyświetlić zamówienia w kontrolce siatki pojedynczego widoku. Wzorzec szczegół wiązania z danymi będzie działać zgodnie z oczekiwaniami ważne jest powiązać właściwość zamówień w klasie klienci nie do osobny węzeł zleceń. Przeciągnij właściwość zamówień klasy klientów do dolnej części formularza tak, aby projektanta umieszcza je w wierszu 2:

     ![Przeciągnij zamówień klas jako siatkę](../data-tools/media/raddata-drag-orders-classes-as-grid.png)

7.  Visual Studio wygenerował żadnego kodu powiązania, który łączy kontrolek interfejsu użytkownika do zdarzeń w modelu. Wszystko, co należy zrobić, aby zobaczyć niektóre dane, jest napisanie kodu, aby wypełnić modelu. Po pierwsze, przejdź do *MainWindow.xaml.cs* i dodać element członkowski danych klasy okna głównego dla kontekstu danych. Ten obiekt, który został wygenerowany dla Ciebie, działa podobnie formant, który śledzi zmiany i zdarzeń w modelu. Zostanie również dodać logikę inicjującą konstruktora. Na początku klasy powinien wyglądać następująco:

     [!code-csharp[MainWindow#1](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#1)]

     Dodaj `using` dyrektywy dla System.Data.Entity wprowadzenia — metoda rozszerzenia obciążenia w zakresie:

     ```csharp
     using System.Data.Entity;
     ```

     Teraz przewiń w dół i Znajdź `Window_Loaded` obsługi zdarzeń. Zwróć uwagę, że program Visual Studio dodał obiektu CollectionViewSource. Reprezentuje obiekt NorthwindEntities wybranej podczas tworzenia modelu. Teraz Dodaj kod, aby `Window_Loaded` tak, aby cały metody teraz wygląda następująco:

     [!code-csharp[Window_Loaded#2](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#2)]

8.  Naciśnij klawisz **F5**. Szczegóły powinny być widoczne dla pierwszego klienta, który został pobrany do CollectionViewSource. Należy również sprawdzić ich zamówień w siatce danych. Formatowanie nie jest duża, dlatego ta funkcja pozwala rozwiązać ten problem. Można również utworzyć sposób wyświetlania innych rekordów oraz wykonywać podstawowe operacje CRUD.

## <a name="adjust-the-page-design-and-add-grids-for-new-customers-and-orders"></a>Dostosuj projekt strony i dodać siatki dla nowych klientów i zlecenia

Układ domyślny utworzony przez program Visual Studio nie jest odpowiedni dla twojej aplikacji, więc należy ręcznie podjąć pewne zmiany w kodzie XAML. Należy również niektórych "Form", (które są rzeczywiście siatki), aby zezwolić użytkownikowi na dodawanie nowych klientów lub kolejności. Aby można było dodać nowego klienta i kolejność, potrzebujesz osobny zestaw pól tekstowych, które nie są powiązane z danymi do `CollectionViewSource`. Będzie kontrolować siatki, które użytkownik zobaczy w danym momencie przez ustawienie właściwości Visible metod obsługi. Na koniec należy dodać przycisk Usuń do każdego wiersza w siatce zleceń umożliwia użytkownikowi na usuwanie pojedynczego zamówienia.

Najpierw dodaj te style `Windows.Resources` element *MainWindow.xaml*:

```xaml
<Style x:Key="Label" TargetType="{x:Type Label}" BasedOn="{x:Null}">
    <Setter Property="HorizontalAlignment" Value="Left"/>
    <Setter Property="VerticalAlignment" Value="Center"/>
    <Setter Property="Margin" Value="3"/>
    <Setter Property="Height" Value="23"/>
</Style>
<Style x:Key="CustTextBox" TargetType="{x:Type TextBox}" BasedOn="{x:Null}">
    <Setter Property="HorizontalAlignment" Value="Right"/>
    <Setter Property="VerticalAlignment" Value="Center"/>
    <Setter Property="Margin" Value="3"/>
    <Setter Property="Height" Value="26"/>
    <Setter Property="Width" Value="120"/>
</Style>
```

Następnie zastąp całą siatki zewnętrzne tego znacznika:

```xaml
<Grid>
     <Grid.RowDefinitions>
         <RowDefinition Height="auto"/>
         <RowDefinition Height="auto"/>
         <RowDefinition Height="*"/>
     </Grid.RowDefinitions>
     <Grid x:Name="existingCustomerGrid" Grid.Row="1" HorizontalAlignment="Left" Margin="5" Visibility="Visible" VerticalAlignment="Top" Background="AntiqueWhite" DataContext="{StaticResource customerViewSource}">
         <Grid.ColumnDefinitions>
             <ColumnDefinition Width="Auto" MinWidth="233"/>
             <ColumnDefinition Width="Auto" MinWidth="397"/>
         </Grid.ColumnDefinitions>
         <Grid.RowDefinitions>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
         </Grid.RowDefinitions>
         <Label Content="Customer ID:" Grid.Row="0" Style="{StaticResource Label}"/>
         <TextBox x:Name="customerIDTextBox" Grid.Row="0" Style="{StaticResource CustTextBox}"
                  Text="{Binding CustomerID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Company Name:" Grid.Row="1" Style="{StaticResource Label}"/>
         <TextBox x:Name="companyNameTextBox" Grid.Row="1" Style="{StaticResource CustTextBox}"
                  Text="{Binding CompanyName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Contact Name:" Grid.Row="2" Style="{StaticResource Label}"/>
         <TextBox x:Name="contactNameTextBox" Grid.Row="2" Style="{StaticResource CustTextBox}"
                  Text="{Binding ContactName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Contact Title:" Grid.Row="3" Style="{StaticResource Label}"/>
         <TextBox x:Name="contactTitleTextBox" Grid.Row="3" Style="{StaticResource CustTextBox}"
                  Text="{Binding ContactTitle, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Address:" Grid.Row="4" Style="{StaticResource Label}"/>
         <TextBox x:Name="addressTextBox" Grid.Row="4" Style="{StaticResource CustTextBox}"
                  Text="{Binding Address, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="City:" Grid.Column="1" Grid.Row="0" Style="{StaticResource Label}"/>
         <TextBox x:Name="cityTextBox" Grid.Column="1" Grid.Row="0" Style="{StaticResource CustTextBox}"
                  Text="{Binding City, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Country:" Grid.Column="1" Grid.Row="1" Style="{StaticResource Label}"/>
         <TextBox x:Name="countryTextBox" Grid.Column="1" Grid.Row="1" Style="{StaticResource CustTextBox}"
                  Text="{Binding Country, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Fax:" Grid.Column="1" Grid.Row="2" Style="{StaticResource Label}"/>
         <TextBox x:Name="faxTextBox" Grid.Column="1" Grid.Row="2" Style="{StaticResource CustTextBox}"
                  Text="{Binding Fax, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Phone:" Grid.Column="1" Grid.Row="3" Style="{StaticResource Label}"/>
         <TextBox x:Name="phoneTextBox" Grid.Column="1" Grid.Row="3" Style="{StaticResource CustTextBox}"
                  Text="{Binding Phone, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Postal Code:" Grid.Column="1" Grid.Row="4" VerticalAlignment="Center" Style="{StaticResource Label}"/>
         <TextBox x:Name="postalCodeTextBox" Grid.Column="1" Grid.Row="4" Style="{StaticResource CustTextBox}"
                  Text="{Binding PostalCode, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Region:" Grid.Column="1" Grid.Row="5" Style="{StaticResource Label}"/>
         <TextBox x:Name="regionTextBox" Grid.Column="1" Grid.Row="5" Style="{StaticResource CustTextBox}"
                  Text="{Binding Region, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
     </Grid>
     <Grid x:Name="newCustomerGrid" Grid.Row="1" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="5" DataContext="{Binding RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type Window}}, Path=newCustomer, UpdateSourceTrigger=Explicit}" Visibility="Collapsed" Background="CornflowerBlue">
         <Grid.ColumnDefinitions>
             <ColumnDefinition Width="Auto" MinWidth="233"/>
             <ColumnDefinition Width="Auto" MinWidth="397"/>
         </Grid.ColumnDefinitions>
         <Grid.RowDefinitions>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
         </Grid.RowDefinitions>
         <Label Content="Customer ID:" Grid.Row="0" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_customerIDTextBox" Grid.Row="0" Style="{StaticResource CustTextBox}"
                  Text="{Binding CustomerID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Company Name:" Grid.Row="1" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_companyNameTextBox" Grid.Row="1" Style="{StaticResource CustTextBox}"
                  Text="{Binding CompanyName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true }"/>
         <Label Content="Contact Name:" Grid.Row="2" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_contactNameTextBox" Grid.Row="2" Style="{StaticResource CustTextBox}"
                  Text="{Binding ContactName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Contact Title:" Grid.Row="3" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_contactTitleTextBox" Grid.Row="3" Style="{StaticResource CustTextBox}"
                  Text="{Binding ContactTitle, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Address:" Grid.Row="4" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_addressTextBox" Grid.Row="4" Style="{StaticResource CustTextBox}"
                  Text="{Binding Address, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="City:" Grid.Column="1" Grid.Row="0" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_cityTextBox" Grid.Column="1" Grid.Row="0" Style="{StaticResource CustTextBox}"
                  Text="{Binding City, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Country:" Grid.Column="1" Grid.Row="1" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_countryTextBox" Grid.Column="1" Grid.Row="1" Style="{StaticResource CustTextBox}"
                  Text="{Binding Country, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Fax:" Grid.Column="1" Grid.Row="2" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_faxTextBox" Grid.Column="1" Grid.Row="2" Style="{StaticResource CustTextBox}"
                  Text="{Binding Fax, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Phone:" Grid.Column="1" Grid.Row="3" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_phoneTextBox" Grid.Column="1" Grid.Row="3" Style="{StaticResource CustTextBox}"
                  Text="{Binding Phone, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Postal Code:" Grid.Column="1" Grid.Row="4" VerticalAlignment="Center" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_postalCodeTextBox" Grid.Column="1" Grid.Row="4" Style="{StaticResource CustTextBox}"
                  Text="{Binding PostalCode, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Region:" Grid.Column="1" Grid.Row="5" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_regionTextBox" Grid.Column="1" Grid.Row="5" Style="{StaticResource CustTextBox}"
                  Text="{Binding Region, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
     </Grid>
     <Grid x:Name="newOrderGrid" Grid.Row="1" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="5" DataContext="{Binding Path=newOrder, Mode=TwoWay}" Visibility="Collapsed" Background="LightGreen">
         <Grid.ColumnDefinitions>
             <ColumnDefinition Width="Auto" MinWidth="233"/>
             <ColumnDefinition Width="Auto" MinWidth="397"/>
         </Grid.ColumnDefinitions>
         <Grid.RowDefinitions>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
             <RowDefinition Height="Auto"/>
         </Grid.RowDefinitions>
         <Label Content="New Order Form" FontWeight="Bold"/>
         <Label Content="Employee ID:"  Grid.Row="1" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_employeeIDTextBox" Grid.Row="1" Style="{StaticResource CustTextBox}"
                  Text="{Binding EmployeeID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Order Date:"  Grid.Row="2" Style="{StaticResource Label}"/>
         <DatePicker x:Name="add_orderDatePicker" Grid.Row="2"  HorizontalAlignment="Right" Width="120"
                 SelectedDate="{Binding OrderDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>
         <Label Content="Required Date:" Grid.Row="3" Style="{StaticResource Label}"/>
         <DatePicker x:Name="add_requiredDatePicker" Grid.Row="3" HorizontalAlignment="Right" Width="120"
                  SelectedDate="{Binding RequiredDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>
         <Label Content="Shipped Date:"  Grid.Row="4"  Style="{StaticResource Label}"/>
         <DatePicker x:Name="add_shippedDatePicker"  Grid.Row="4"  HorizontalAlignment="Right" Width="120"
                 SelectedDate="{Binding ShippedDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>
         <Label Content="Ship Via:"  Grid.Row="5" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_ShipViaTextBox"  Grid.Row="5" Style="{StaticResource CustTextBox}"
                  Text="{Binding ShipVia, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Freight"  Grid.Row="6" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_freightTextBox" Grid.Row="6" Style="{StaticResource CustTextBox}"
                  Text="{Binding Freight, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
     </Grid>
     <DataGrid x:Name="ordersDataGrid" SelectionUnit="Cell" SelectionMode="Single" AutoGenerateColumns="False" CanUserAddRows="false" IsEnabled="True" EnableRowVirtualization="True" Width="auto" ItemsSource="{Binding Source={StaticResource customerOrdersViewSource}}" Margin="10,10,10,10" Grid.Row="2" RowDetailsVisibilityMode="VisibleWhenSelected">
         <DataGrid.Columns>
             <DataGridTemplateColumn>
                 <DataGridTemplateColumn.CellTemplate>
                     <DataTemplate>
                         <Button Content="Delete" Command="{StaticResource DeleteOrderCommand}" CommandParameter="{Binding}"/>
                     </DataTemplate>
                 </DataGridTemplateColumn.CellTemplate>
             </DataGridTemplateColumn>
             <DataGridTextColumn x:Name="customerIDColumn" Binding="{Binding CustomerID}" Header="Customer ID" Width="SizeToHeader"/>
             <DataGridTextColumn x:Name="employeeIDColumn" Binding="{Binding EmployeeID}" Header="Employee ID" Width="SizeToHeader"/>
             <DataGridTextColumn x:Name="freightColumn" Binding="{Binding Freight}" Header="Freight" Width="SizeToHeader"/>
             <DataGridTemplateColumn x:Name="orderDateColumn" Header="Order Date" Width="SizeToHeader">
                 <DataGridTemplateColumn.CellTemplate>
                     <DataTemplate>
                         <DatePicker SelectedDate="{Binding OrderDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>
                     </DataTemplate>
                 </DataGridTemplateColumn.CellTemplate>
             </DataGridTemplateColumn>
             <DataGridTextColumn x:Name="orderIDColumn" Binding="{Binding OrderID}" Header="Order ID" Width="SizeToHeader"/>
             <DataGridTemplateColumn x:Name="requiredDateColumn" Header="Required Date" Width="SizeToHeader">
                 <DataGridTemplateColumn.CellTemplate>
                     <DataTemplate>
                         <DatePicker SelectedDate="{Binding RequiredDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>
                     </DataTemplate>
                 </DataGridTemplateColumn.CellTemplate>
             </DataGridTemplateColumn>
             <DataGridTextColumn x:Name="shipAddressColumn" Binding="{Binding ShipAddress}" Header="Ship Address" Width="SizeToHeader"/>
             <DataGridTextColumn x:Name="shipCityColumn" Binding="{Binding ShipCity}" Header="Ship City" Width="SizeToHeader"/>
             <DataGridTextColumn x:Name="shipCountryColumn" Binding="{Binding ShipCountry}" Header="Ship Country" Width="SizeToHeader"/>
             <DataGridTextColumn x:Name="shipNameColumn" Binding="{Binding ShipName}" Header="Ship Name" Width="SizeToHeader"/>
             <DataGridTemplateColumn x:Name="shippedDateColumn" Header="Shipped Date" Width="SizeToHeader">
                 <DataGridTemplateColumn.CellTemplate>
                     <DataTemplate>
                         <DatePicker SelectedDate="{Binding ShippedDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>
                     </DataTemplate>
                 </DataGridTemplateColumn.CellTemplate>
             </DataGridTemplateColumn>
             <DataGridTextColumn x:Name="shipPostalCodeColumn" Binding="{Binding ShipPostalCode}" Header="Ship Postal Code" Width="SizeToHeader"/>
             <DataGridTextColumn x:Name="shipRegionColumn" Binding="{Binding ShipRegion}" Header="Ship Region" Width="SizeToHeader"/>
             <DataGridTextColumn x:Name="shipViaColumn" Binding="{Binding ShipVia}" Header="Ship Via" Width="SizeToHeader"/>
         </DataGrid.Columns>
     </DataGrid>
 </Grid>
```

## <a name="add-buttons-to-navigate-add-update-and-delete"></a>Dodawanie przycisków do Przejdź, dodawanie, aktualizowanie i usuwanie

W aplikacjach formularzy systemu Windows możesz uzyskać obiekt BindingNavigator z przycisków nawigacji wierszy w bazie danych i wykonywania podstawowych operacji CRUD. WPF nie zapewnia BindingNavigator, ale jest dość proste go utworzyć. Tym przycisków w poziomie Panel stosu i skojarzyć przycisków z poleceniami, które są powiązane z metody w kodzie.

Brak części fours logiki polecenia: (1) poleceń, powiązania (2, (3) przycisków i (4 programy obsługi poleceń w CodeBehind.

### <a name="add-commands-bindings-and-buttons-in-xaml"></a>Dodawanie poleceń, powiązania i przycisków w języku XAML

1.  Najpierw dodaj poleceń w *MainWindow.xaml* pliku wewnątrz `Windows.Resources` elementu:

    ```xaml
    <RoutedUICommand x:Key="FirstCommand" Text="First"/>
    <RoutedUICommand x:Key="LastCommand" Text="Last"/>
    <RoutedUICommand x:Key="NextCommand" Text="Next"/>
    <RoutedUICommand x:Key="PreviousCommand" Text="Previous"/>
    <RoutedUICommand x:Key="DeleteCustomerCommand" Text="Delete Customer"/>
    <RoutedUICommand x:Key="DeleteOrderCommand" Text="Delete Order"/>
    <RoutedUICommand x:Key="UpdateCommand" Text="Update"/>
    <RoutedUICommand x:Key="AddCommand" Text="Add"/>
    <RoutedUICommand x:Key="CancelCommand" Text="Cancel"/>
    ```

2.  Mapuje elementem CommandBinding `RoutedUICommand` zdarzeń do metody w kodzie. Dodaj tę `CommandBindings` elementu po `Windows.Resources` tagu zamykającego:

    ```xaml
    <Window.CommandBindings>
        <CommandBinding Command="{StaticResource FirstCommand}" Executed="FirstCommandHandler"/>
        <CommandBinding Command="{StaticResource LastCommand}" Executed="LastCommandHandler"/>
        <CommandBinding Command="{StaticResource NextCommand}" Executed="NextCommandHandler"/>
        <CommandBinding Command="{StaticResource PreviousCommand}" Executed="PreviousCommandHandler"/>
        <CommandBinding Command="{StaticResource DeleteCustomerCommand}" Executed="DeleteCustomerCommandHandler"/>
        <CommandBinding Command="{StaticResource DeleteOrderCommand}" Executed="DeleteOrderCommandHandler"/>
        <CommandBinding Command="{StaticResource UpdateCommand}" Executed="UpdateCommandHandler"/>
        <CommandBinding Command="{StaticResource AddCommand}" Executed="AddCommandHandler"/>
        <CommandBinding Command="{StaticResource CancelCommand}" Executed="CancelCommandHandler"/>
    </Window.CommandBindings>
    ```

3.  Teraz Dodaj `StackPanel` z nawigacji, dodawanie, usuwanie i aktualizowanie przycisków. Najpierw dodaj ten styl `Windows.Resources`:

    ```xaml
    <Style x:Key="NavButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="FontSize" Value="24"/>
        <Setter Property="FontFamily" Value="Segoe UI Symbol"/>
        <Setter Property="Margin" Value="2,2,2,0"/>
        <Setter Property="Width" Value="40"/>
        <Setter Property="Height" Value="auto"/>
    </Style>
    ```

     Po drugie, wklej ten kod tuż po `RowDefinitions` dla zewnętrznego `Grid` elemencie w kierunku do góry strony XAML:

    ```xaml
    <StackPanel Orientation="Horizontal" Margin="2,2,2,0" Height="36" VerticalAlignment="Top" Background="Gainsboro" DataContext="{StaticResource customerViewSource}" d:LayoutOverrides="LeftMargin, RightMargin, TopMargin, BottomMargin">
        <Button Name="btnFirst" Content="|◄" Command="{StaticResource FirstCommand}" Style="{StaticResource NavButton}"/>
        <Button Name="btnPrev" Content="◄" Command="{StaticResource PreviousCommand}" Style="{StaticResource NavButton}"/>
        <Button Name="btnNext" Content="►" Command="{StaticResource NextCommand}" Style="{StaticResource NavButton}"/>
        <Button Name="btnLast" Content="►|" Command="{StaticResource LastCommand}" Style="{StaticResource NavButton}"/>
        <Button Name="btnDelete" Content="Delete Customer" Command="{StaticResource DeleteCustomerCommand}" FontSize="11" Width="120" Style="{StaticResource NavButton}"/>
        <Button Name="btnAdd" Content="New Customer" Command="{StaticResource AddCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>
        <Button Content="New Order" Name="btnNewOrder" FontSize="11" Width="80" Style="{StaticResource NavButton}" Click="NewOrder_click"/>
        <Button Name="btnUpdate" Content="Commit" Command="{StaticResource UpdateCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>
        <Button Content="Cancel" Name="btnCancel" Command="{StaticResource CancelCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>
    </StackPanel>
    ```

### <a name="add-command-handlers-to-the-mainwindow-class"></a>Dodaj programy obsługi poleceń do klasy okna głównego

CodeBehind jest minimalny, z wyjątkiem metod dodawania i usuwania. Nawigacji jest wykonywane przez wywołanie metody na właściwość View elementu CollectionViewSource. `DeleteOrderCommandHandler` Pokazano, jak wykonać usuwanie kaskadowe zamówienia. Mamy najpierw usunąć szczegóły zamówienia, które są skojarzone z nim. `UpdateCommandHandler` Dodaje nowego klienta lub kolejności do kolekcji, w przeciwnym razie po prostu aktualizuje istniejący klient lub kolejności zmiany wprowadzone przez użytkownika w polach tekstowych.

Dodaj do klasy okna głównego w tych metod obsługi *MainWindow.xaml.cs*. Jeśli Twoje CollectionViewSource dla tabeli klientów ma inną nazwę, należy dostosować nazwę w każdej z tych metod:

[!code-csharp[CommandHandlers#3](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#3)]

## <a name="run-the-application"></a>Uruchamianie aplikacji

Aby rozpocząć debugowanie, naciśnij klawisz **F5**. Powinna zostać wyświetlona klienta i kolejność danych w siatce, a przycisków nawigacji powinny działać zgodnie z oczekiwaniami. Polecenie **zatwierdzić** można dodać nowego klienta lub kolejności do modelu po wprowadzeniu danych. Polecenie **anulować** kopii poza nowego klienta lub nowy formularz kolejności bez zapisywania danych. Możesz wprowadzić zmian do istniejących klientów i zamówienia bezpośrednio w polach tekstowych, a te zmiany są automatycznie zapisywane w modelu.

## <a name="see-also"></a>Zobacz także

- [Narzędzia do obsługi danych programu Visual Studio dla platformy .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)
- [Dokumentację programu Entity Framework](/ef/)