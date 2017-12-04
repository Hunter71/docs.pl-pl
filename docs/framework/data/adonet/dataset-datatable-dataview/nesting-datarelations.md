---
title: "DataRelations zagnieżdżenia"
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
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db7df753bf6066d3a89c46a82b66e47281076f95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="nesting-datarelations"></a>DataRelations zagnieżdżenia
Poszczególnych tabel relacyjnych reprezentację danych, zawierać wierszy, które są powiązane ze sobą przy użyciu kolumny lub zestaw kolumn. W ADO.NET <xref:System.Data.DataSet>, relacji między tabelami jest implementowane za pomocą <xref:System.Data.DataRelation>. Po utworzeniu **DataRelation**, relacje nadrzędny podrzędny kolumn są zarządzane za pośrednictwem tylko relacja. Tabele i kolumny są osobne jednostki. W hierarchiczną reprezentację danych XML zawiera relacje nadrzędny podrzędny są reprezentowane przez elementy nadrzędne, zawierające elementy zagnieżdżonych elementów podrzędnych.  
  
 Ułatwia to zagnieżdżania obiektów podrzędnych podczas **DataSet** jest zsynchronizowany z <xref:System.Xml.XmlDataDocument> lub zapisywane jako danych XML przy użyciu **WriteXml**, **DataRelation** przedstawia **zagnieżdżone** właściwości. Ustawienie **zagnieżdżone** właściwość **DataRelation** do **true** powoduje, że obiekt podrzędny wierszy relacji do być zagnieżdżony w kolumnie nadrzędnej, gdy zapisywane jako dane XML lub synchronizowane z **dokumentu XmlDataDocument**. **Zagnieżdżone** właściwość **DataRelation** jest **false**, domyślnie.  
  
 Na przykład, należy wziąć pod uwagę następujące **zestawu danych**.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection)  
  
connection.Open()  
  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
customerAdapter.Fill(dataSet, "Customers")  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
Dim customerOrders As DataRelation = dataSet.Relations.Add( _  
  "CustOrders", dataSet.Tables("Customers").Columns("CustomerID"), _  
  dataSet.Tables("Orders").Columns("CustomerID"))  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection);  
  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
customerAdapter.Fill(dataSet, "Customers");  
orderAdapter.Fill(dataSet, "Orders");  
  
connection.Close();  
  
DataRelation customerOrders = dataSet.Relations.Add(  
  "CustOrders", dataSet.Tables["Customers"].Columns["CustomerID"],  
  dataSet.Tables["Orders"].Columns["CustomerID"]);  
```  
  
 Ponieważ **zagnieżdżone** właściwość **DataRelation** obiektu nie jest ustawiony na **true** tego **zestawu danych**, obiekty podrzędne nie są zagnieżdżone w ramach elementy nadrzędne podczas to **DataSet** jest reprezentowany jako dane XML. Przekształcanie XML reprezentację **zestawu danych** zawiera powiązane **zestawu danych**s z relacjami-nested danych może spowodować spadek wydajności. Firma Microsoft zaleca, aby zagnieździć relacji danych. Aby to zrobić, ustaw **zagnieżdżone** właściwości **true**. Następnie należy napisać kod w arkusz stylów XSLT, który używa wyrażenia zapytania XPath góra dół hierarchiczne do lokalizowania i przekształcania danych.  
  
 Poniższy przykładowy kod przedstawia wynik wywołania **WriteXml** na **zestawu danych**.  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
  <Orders>  
    <OrderID>10643</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-08-25T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10692</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-10-03T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10308</OrderID>  
    <CustomerID>ANATR</CustomerID>  
    <OrderDate>1996-09-18T00:00:00</OrderDate>  
  </Orders>  
</CustomerOrders>  
```  
  
 Należy pamiętać, że **klientów** elementu i **zamówień** elementy są wyświetlane jako elementów równorzędnych. Jeśli potrzebujesz **zamówień** elementy wyświetlane jako elementy podrzędne ich elementów nadrzędnych odpowiednich, **zagnieżdżone** właściwość **DataRelation** musi mieć ustawioną **true** i należy dodać następujące:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 Poniższy kod przedstawia, jak dane wyjściowe będą wyglądać, z **zamówień** elementy zagnieżdżone w obrębie ich elementów nadrzędnych odpowiednich.  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <Orders>  
      <OrderID>10643</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-08-25T00:00:00</OrderDate>  
    </Orders>  
    <Orders>  
      <OrderID>10692</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-10-03T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <Orders>  
      <OrderID>10308</OrderID>  
      <CustomerID>ANATR</CustomerID>  
      <OrderDate>1996-09-18T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
</CustomerOrders>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Za pomocą języka XML w zestawie danych](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Dodawanie DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 [Zbiory danych, DataTables i DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów](http://go.microsoft.com/fwlink/?LinkId=217917)