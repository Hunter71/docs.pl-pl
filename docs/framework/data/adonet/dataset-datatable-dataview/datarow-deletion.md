---
title: Usunięcie elementu DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 128c41e1906b17e7f42458e8a5f1b3d3ec9cc449
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
---
# <a name="datarow-deletion"></a>Usunięcie elementu DataRow
Istnieją dwie metody służy do usuwania <xref:System.Data.DataRow> obiekt z <xref:System.Data.DataTable> obiekt: **Usuń** metody <xref:System.Data.DataRowCollection> obiektu i <xref:System.Data.DataRow.Delete%2A> metody **DataRow**obiektu. Natomiast <xref:System.Data.DataRowCollection.Remove%2A> metoda usuwa **DataRow** z **kolekcji DataRowCollection**, <xref:System.Data.DataRow.Delete%2A> metoda oznacza tylko wierszy do usunięcia. Rzeczywiste usunięcie występuje, gdy aplikacja wywołuje **AcceptChanges** metody. Przy użyciu <xref:System.Data.DataRow.Delete%2A>, można programowo sprawdzić wiersze, które są oznaczone do usunięcia przed ich faktycznego usuwania. Jeśli wiersz jest oznaczona do usunięcia, jego <xref:System.Data.DataRow.RowState%2A> właściwość jest ustawiona na <xref:System.Data.DataRow.Delete%2A>.  
  
 Ani <xref:System.Data.DataRow.Delete%2A> ani <xref:System.Data.DataRowCollection.Remove%2A> powinna być wywoływana podczas iteracji w pętli foreach <xref:System.Data.DataRowCollection> obiektu. <xref:System.Data.DataRow.Delete%2A> ani <xref:System.Data.DataRowCollection.Remove%2A> zmodyfikuj stan kolekcji.  
  
 Korzystając z <xref:System.Data.DataSet> lub **DataTable** w połączeniu z **element DataAdapter** i relacyjnym źródłem danych, użyj **usunąć** metody  **Element DataRow** do usunięcia wiersza. **Usunąć** wierszu, co oznacza metodę **usunięte** w **DataSet** lub **DataTable** , ale nie powoduje usunięcia. Zamiast tego, kiedy **element DataAdapter** napotka oznaczonego jako **usunięte**, wykonywania jego **elementu DeleteCommand** do usunięcia wierszy w źródle danych. Wiersz może następnie należy trwale usunąć przy użyciu **AcceptChanges** metody. Jeśli używasz **Usuń** można usunąć wiersza, wiersz jest całkowicie usuwane z tabeli, ale **element DataAdapter** nie spowoduje usunięcia wierszy w źródle danych.  
  
 **Usuń** metody **kolekcji DataRowCollection** przyjmuje **DataRow** jako argument i usuwa go z kolekcji, jak pokazano w poniższym przykładzie.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Z kolei w poniższym przykładzie pokazano sposób wywoływania **usunąć** metoda **DataRow** można zmienić jego **RowState** do **usunięte** .  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Jeśli wiersz jest oznaczona do usunięcia i wywołania **AcceptChanges** metody **DataTable** obiekt wiersza jest usuwany z **DataTable**. Z drugiej strony, jeśli wywołujesz **RejectChanges**, **RowState** wiersza wraca do sprzed oznaczony jako **usunięte**.  
  
> [!NOTE]
>  Jeśli **RowState** z **DataRow** jest **Added**, czyli właśnie został dodany do tabeli, a następnie jest oznaczony jako **usunięte**, jest usunięte z tabeli.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [Operowanie danymi w elemencie DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów](http://go.microsoft.com/fwlink/?LinkId=217917)
