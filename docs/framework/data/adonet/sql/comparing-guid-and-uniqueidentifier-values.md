---
title: "Porównanie identyfikator GUID i uniqueidentifier wartości"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7bdd8108261e1e1bc18dd636ba654f7fb6bed981
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="comparing-guid-and-uniqueidentifier-values"></a>Porównanie identyfikator GUID i uniqueidentifier wartości
Typ danych Unikatowy identyfikator globalny (GUID) w programie SQL Server jest reprezentowana przez `uniqueidentifier` typ danych, który przechowuje 16-bajtowych wartości binarnej. Identyfikator GUID jest liczbą binarną i jest głównie jako identyfikator, który musi być unikatowa w sieci z wielu komputerów w wielu lokacjach. Identyfikatory GUID mogą być generowane przez wywołanie funkcji NEWID języka Transact-SQL i jest musi być unikatowy w całym świecie. Aby uzyskać więcej informacji zobacz "Using uniqueidentifier danych" w dokumentacji SQL Server — książki Online.  
  
## <a name="working-with-sqlguid-values"></a>Praca z wartościami SqlGuid  
 Identyfikatory GUID są długich i zasłoniętej, dlatego nie są one przydatne dla użytkowników. Jeśli identyfikatory GUID losowo generowane są używane do wartości kluczy i wstawić wiele wierszy, możesz uzyskać losowych operacji We/Wy do Twojej indeksy, które może niekorzystnie wpłynąć na wydajność. Identyfikatory GUID są również stosunkowo dużej w porównaniu do innych typów danych. Ogólnie zaleca się tylko w przypadku scenariuszy bardzo małym nie innych danych jest odpowiedni typ przy użyciu identyfikatorów GUID.  
  
### <a name="comparing-guid-values"></a>Porównanie wartości identyfikatora GUID  
 Operatory porównania mogą być używane z `uniqueidentifier` wartości. Jednak kolejność nie jest zaimplementowana przez porównanie wzorce bit dwóch wartości. Tylko operacje, które są dozwolone przed `uniqueidentifier` wartości są porównania (= <>, \<, >, \<=, > =) i sprawdzanie wartości NULL (IS NULL i IS NOT NULL). Inne operatory arytmetyczne są dozwolone.  
  
 Zarówno <xref:System.Guid> i <xref:System.Data.SqlTypes.SqlGuid> ma `CompareTo` metodę porównywania różnych wartości identyfikatora GUID. Jednak `System.Guid.CompareTo` i `SqlTypes.SqlGuid.CompareTo` są implementowane w inny sposób. <xref:System.Data.SqlTypes.SqlGuid>implementuje `CompareTo` przy użyciu zachowanie programu SQL Server w ostatnich sześciu bajtów wartości są najbardziej znaczący. <xref:System.Guid>oblicza wszystkie 16 bajtów. W poniższym przykładzie pokazano różnicę zachowania. Pierwsza sekcja wyświetla kod nieposortowane <xref:System.Guid> wartości, a druga sekcja kod pokazuje sortowanych <xref:System.Guid> wartości. Trzeci sekcji przedstawiono sortowanych <xref:System.Data.SqlTypes.SqlGuid> wartości. Dane wyjściowe jest wyświetlana poniżej przykładowy kod.  
  
 [!code-csharp[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/VB/source.vb#1)]  
  
 Ten przykład generuje następujące wyniki.  
  
```  
Unsorted Guids:  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
  
Sorted Guids:  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
  
Sorted SqlGuids:  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Danych programu SQL Server typy i ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów](http://go.microsoft.com/fwlink/?LinkId=217917)