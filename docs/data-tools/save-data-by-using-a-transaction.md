---
title: "Porady: zapisywanie danych przy użyciu transakcji | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- saving data, using transactions
- System.Transactions namespace
- transactions, saving data
- data [Visual Studio], saving
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 23cf5ee9ef7369d8c0f52adde639adad4abe3ae6
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2017
---
# <a name="how-to-save-data-by-using-a-transaction"></a>Porady: zapisywanie danych przy użyciu transakcji
Zapisywanie danych w transakcji przy użyciu <xref:System.Transactions> przestrzeni nazw. Użyj <xref:System.Transactions.TransactionScope> obiekt, aby uczestniczyć w transakcji, która jest automatycznie zarządzane dla Ciebie.  
  
Projekty nie są tworzone z odwołaniem do zestawu System.Transactions, więc musisz ręcznie Dodaj odwołanie do projektów, które używają transakcji.  
  
Najłatwiejszym sposobem realizowania transakcji jest można utworzyć wystąpienia <xref:System.Transactions.TransactionScope> obiektu w `using` instrukcji. (Aby uzyskać więcej informacji, zobacz [instrukcji Using](/dotnet/visual-basic/language-reference/statements/using-statement), i [za pomocą instrukcji](/dotnet/csharp/language-reference/keywords/using-statement).) Kod, który jest uruchamiany w ramach `using` instrukcji uczestniczy w transakcji.  
  
Aby zatwierdzić transakcji, należy wywołać <xref:System.Transactions.TransactionScope.Complete%2A> następujący ostatnim za pomocą zablokować.  
  
Aby wycofać transakcji, Zgłoś wyjątek przed wywołaniem <xref:System.Transactions.TransactionScope.Complete%2A> metody.  
  
## <a name="to-add-a-reference-to-the-systemtransactionsdll"></a>Aby dodać odwołanie do Biblioteka System.Transactions.dll  
  
1.  Na **projektu** menu, wybierz opcję **Dodaj odwołanie**.  
  
2.  Na **.NET** kartę (**programu SQL Server** kartę dla projektów programu SQL Server), wybierz pozycję **System.Transactions**, a następnie wybierz **OK**.  
  
     Odwołanie do Biblioteka System.Transactions.dll zostanie dodany do projektu.  
  
## <a name="to-save-data-in-a-transaction"></a>Można zapisać danych w transakcji  
  
-   Dodaj kod, aby zapisać danych w ramach przy użyciu instrukcji, która zawiera transakcję. Poniższy kod przedstawia sposób tworzenia i wystąpienia <xref:System.Transactions.TransactionScope> obiektu za pomocą instrukcji:  
  
     [!code-vb[VbRaddataSaving#11](../data-tools/codesnippet/VisualBasic/save-data-by-using-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#11](../data-tools/codesnippet/CSharp/save-data-by-using-a-transaction_1.cs)]  
  
## <a name="see-also"></a>Zobacz także
[Zapisywanie danych w bazie danych](../data-tools/save-data-back-to-the-database.md)  
[Wskazówki: Zapisywanie danych w transakcji](../data-tools/save-data-in-a-transaction.md)  