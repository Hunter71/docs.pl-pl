---
title: 'Porady: Użyj funkcji skalarnej zdefiniowanej przez użytkownika'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: 3748f7b865de22353c8c0a91aaf52e672455ed38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>Porady: Użyj funkcji skalarnej zdefiniowanej przez użytkownika
Zdefiniowany w klasie w funkcji zdefiniowanej przez użytkownika przy użyciu metody klienta można mapować <xref:System.Data.Linq.Mapping.FunctionAttribute> atrybutu. Należy pamiętać, że treść metody tworzy wyrażenie, które znajdują się próba wywołania metody i przekazuje tego wyrażenia do <xref:System.Data.Linq.DataContext> tłumaczenia i wykonywania.  
  
> [!NOTE]
>  Bezpośrednie wykonywanie występuje tylko wtedy, gdy funkcja jest wywoływana poza zapytaniem. Aby uzyskać więcej informacji, zobacz [porady: wbudowane funkcje Call User-Defined](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).  
  
## <a name="example"></a>Przykład  
 Następujący kod SQL stanowi funkcji skalarnej zdefiniowanej przez użytkownika `ReverseCustName()`.  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 Czy mapy metodę klienta, takich jak dla tego kodu:  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a>Zobacz też  
 [Funkcje zdefiniowane przez użytkownika](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
