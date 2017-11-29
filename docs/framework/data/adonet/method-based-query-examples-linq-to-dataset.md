---
title: "Przykłady zapytań — metoda (LINQ do DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d340775c-7f39-4087-a290-5cbec6cfa68e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 995ac8b4fc91517573dbf9cc02dd1133074ade54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="method-based-query-examples-linq-to-dataset"></a>Przykłady zapytań — metoda (LINQ do DataSet)
Ta sekcja zawiera [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] programowania, przykłady w składni zapytania oparte na metodzie, które używają standardowych operatorów zapytań. <xref:System.Data.DataSet> Używane w tym przykładzie jest wypełniany przy użyciu `FillDataSet` metodę, która została określona w [podczas ładowania danych do zestawu danych](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md). Aby uzyskać więcej informacji, zobacz [standardowe operatory zapytań — omówienie](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Projekcji](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
 Przykłady w tym temacie przedstawiają sposób użycia <xref:System.Linq.Enumerable.Select%2A> i <xref:System.Linq.Enumerable.SelectMany%2A> metod do badania <xref:System.Data.DataSet>.  
  
 [Podział na partycje](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
 Przykłady w tym temacie przedstawiają sposób użycia <xref:System.Linq.Enumerable.Skip%2A> i <xref:System.Linq.Enumerable.Take%2A> metod do badania <xref:System.Data.DataSet> i partycji wyniki.  
  
 [Kolejność](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
 Przykłady w tym temacie przedstawiają sposób użycia <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, i <xref:System.Linq.Enumerable.ThenByDescending%2A> metod do badania <xref:System.Data.DataSet> i kolejność wyników.  
  
 [Operatory zestawów](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
 Przykłady w tym temacie przedstawiają sposób użycia <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, i <xref:System.Linq.Enumerable.Union%2A> operatory do wykonywania operacji na podstawie wartości porównania zestawów wierszy danych.  
  
 [Operatory konwersji](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
 Przykłady w tym temacie przedstawiają sposób użycia <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, i <xref:System.Linq.Enumerable.ToList%2A> metod, aby natychmiast wykonać wyrażenia zapytania.  
  
 [Operatory — element](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
 Przykłady w tym temacie przedstawiają sposób użycia <xref:System.Linq.Enumerable.First%2A> i <xref:System.Linq.Enumerable.ElementAt%2A> metody w celu uzyskania <xref:System.Data.DataRow> elementy z <xref:System.Data.DataSet>.  
  
 [Operatory agregacji](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
 Przykłady w tym temacie przedstawiają sposób użycia <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, i <xref:System.Linq.Enumerable.Sum%2A> metod do badania <xref:System.Data.DataSet> i agregowanie danych.  
  
 [Dołącz](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
 Przykłady w tym temacie przedstawiają sposób użycia <xref:System.Linq.Enumerable.GroupJoin%2A> i <xref:System.Linq.Enumerable.Join%2A> metod do badania <xref:System.Data.DataSet>.  
  
## <a name="see-also"></a>Zobacz też  
 [Przykłady wyrażeń zapytania](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)  
 [Przykłady Operator specyficzne dla zestawu danych](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 [LINQ do DataSet przykłady](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)