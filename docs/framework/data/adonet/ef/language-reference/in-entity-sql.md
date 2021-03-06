---
title: W (jednostka SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 1f3be5717c27a691e073cee46df757d0166fe78a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
---
# <a name="in-entity-sql"></a>W (jednostka SQL)
Określa, czy wartość odpowiada wartości w kolekcji.  
  
## <a name="syntax"></a>Składnia  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>Argumenty  
 `value`  
 Dowolne prawidłowe wyrażenie zwracające wartość do dopasowania.  
  
 [NOT]  
 Określa, że `Boolean` wynik w można zanegowane.  
  
 `expression`  
 Dowolne prawidłowe wyrażenie zwracające kolekcji do testowania pod kątem dopasowania. Wszystkie wyrażenia musi być tego samego typu lub wspólny podstawowej lub pochodny typ jako `value`.  
  
## <a name="return-value"></a>Wartość zwracana  
 `true` Jeśli wartość zostanie znaleziony w kolekcji; wartość null, jeśli ma wartość null lub kolekcja ma wartość null; w przeciwnym razie `false`. Przy użyciu NOT IN Negacja wyniki cali  
  
## <a name="example"></a>Przykład  
 Następujące zapytanie SQL jednostki używa operatora IN ustalenie, czy wartość odpowiada wartości w kolekcji. Kwerenda jest oparta na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1.  Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
