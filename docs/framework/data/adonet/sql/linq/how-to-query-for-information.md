---
title: 'Porady: Kwerenda dotycząca informacji'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: ae369cb6aaabfdf116f43629a0acb4ad9f7af8c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-query-for-information"></a>Porady: Kwerenda dotycząca informacji
Zapytania w programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] używać tej samej składni jak zapytania w [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. Jedyną różnicą jest to, że obiekty przywoływane w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zapytania są mapowane do elementów w bazie danych. Aby uzyskać więcej informacji, zobacz [wprowadzenie do kwerend LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tłumaczy zapytania zostanie zapisany na równoważne zapytania SQL, a następnie wysyła je do serwera w celu przetworzenia.  
  
 Niektóre funkcje [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] zapytań może być konieczne szczególną uwagę w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aplikacji. Aby uzyskać więcej informacji, zobacz [pojęcia zapytania](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).  
  
## <a name="example"></a>Przykład  
 Następujące zapytanie zapyta, aby uzyskać listę klientów w Londynie. W tym przykładzie `Customers` jest tabela w bazie danych Northwind.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też  
 [Tworzenie modelu obiektu](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [Pobieranie przykładowych baz danych](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Wykonywanie zapytania w bazie danych](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
