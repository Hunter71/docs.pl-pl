---
title: '|| (LUB) (Jednostka SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 09ae742f648f95819a8c6fc64d402c4f11c7748a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
---
# <a name="-or-entity-sql"></a>|| (LUB) (Jednostka SQL)
Łączy dwa `Boolean` wyrażenia.  
  
## <a name="syntax"></a>Składnia  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Argumenty  
 `boolean_expression`  
 Prawidłowe wyrażenie, które zwraca `Boolean`.  
  
## <a name="return-value"></a>Wartość zwracana  
 `true` Jeśli jeden z warunków jest `true`; w przeciwnym razie `false`.  
  
## <a name="remarks"></a>Uwagi  
 LUB [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatora logicznego. Służy do łączenia dwóch warunków. W przypadku więcej niż jeden operator w instrukcji lub operatory są oceniane po operatorach i. Można jednak zmienić kolejność obliczania za pomocą nawiasów.  
  
 Podwójne pionowych słupków (&#124;&#124;) mają te same funkcje co operatora OR.  
  
 W poniższej tabeli przedstawiono możliwe wartości wejściowych i zwracanych typów.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|WARTOŚĆ TRUE|WARTOŚĆ TRUE|WARTOŚĆ TRUE|  
|`FALSE`|WARTOŚĆ TRUE|FAŁSZ|NULL|  
|`NULL`|WARTOŚĆ TRUE|NULL|NULL|  
  
## <a name="example"></a>Przykład  
 Następujące zapytanie SQL jednostki używa operatora OR do łączenia dwóch `Boolean` wyrażenia. Kwerenda jest oparta na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1.  Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
