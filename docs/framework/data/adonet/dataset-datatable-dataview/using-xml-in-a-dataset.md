---
title: Za pomocą języka XML w zestawie danych
ms.date: 03/30/2017
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
ms.openlocfilehash: c5a4df5f2c77853864f51ee9b226f412f382dd09
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
---
# <a name="using-xml-in-a-dataset"></a>Za pomocą języka XML w zestawie danych
Z ADO.NET możesz wpisać <xref:System.Data.DataSet> ze strumienia XML lub dokumentu. Strumień XML lub dokument można użyć do dostarczenia <xref:System.Data.DataSet> danych, informacje o schemacie lub obu. Informacje podane w strumieniu XML lub dokument można połączyć z istniejących danych i informacji o schemacie znajduje się już w <xref:System.Data.DataSet>.  
  
 ADO.NET umożliwia również tworzenie reprezentację XML <xref:System.Data.DataSet>, z lub bez jego schemat, aby przetransportować <xref:System.Data.DataSet> przez HTTP do użycia przez inną platformie włączone XML lub aplikacji. W reprezentacji XML <xref:System.Data.DataSet>, dane są zapisywane w pliku XML i schemat, jeśli jest dołączony wbudowany w reprezentacji, jest zapisywany przy użyciu języka definicji schematu XML (XSD). XML i schematu XML zapewniają wygodną format przesyłania zawartości <xref:System.Data.DataSet> do i z klientów zdalnych.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Elementy DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 Zawiera szczegółowe informacje na format XML używany do odczytu i zapisu zawartości w formacie DiffGram <xref:System.Data.DataSet>.  
  
 [Ładowanie elementu DataSet z pliku XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 W tym artykule omówiono różne opcje, które należy uwzględnić podczas ładowania zawartości <xref:System.Data.DataSet> z dokumentu XML.  
  
 [Zapisywanie zawartości elementu DataSet jako danych XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 W tym artykule omówiono sposób generowania zawartości <xref:System.Data.DataSet> jako dane XML i można użyć różnych opcji formatu XML.  
  
 [Ładowanie informacji o schemacie elementu DataSet z pliku XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 W tym artykule omówiono <xref:System.Data.DataSet> metody używane do ładowania schematu <xref:System.Data.DataSet> z pliku XML.  
  
 [Zapisywanie informacji o schemacie elementu DataSet jako pliku XSD](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)  
 W tym artykule omówiono zastosowania schematu XML i sposób generowania z <xref:System.Data.DataSet>.  
  
 [Synchronizacja elementów DataSet i XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 Zawiera omówienie możliwości dostępnych w programie .NET Framework synchronicznego dostępu do widoków relacyjnych i hierarchicznych jednego zestawu danych, a pokazano, jak utworzyć synchroniczne relacji między <xref:System.Data.DataSet> i <xref:System.Xml.XmlDataDocument>.  
  
 [Zagnieżdżanie elementów DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 W tym artykule omówiono znaczenie zagnieżdżonych <xref:System.Data.DataRelation> obiektów po reprezentujący zawartość <xref:System.Data.DataSet> danych XML oraz sposób ich tworzenia.  
  
 [Pobieranie relacyjnej struktury elementu DataSet ze schematu XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Opisuje relacyjne struktury lub schematu z <xref:System.Data.DataSet> która jest tworzona na podstawie schematu XML.  
  
 [Wnioskowanie relacyjnej struktury elementu DataSet z pliku XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 Opisuje wynikowy relacyjne struktury lub schematu z <xref:System.Data.DataSet> utworzonego podczas wywnioskować na podstawie elementów XML.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Omówienie ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 W tym artykule opisano ADO.NET architektury i składników i sposobu ich używania dostęp do istniejących źródeł danych oraz do zarządzania danymi w aplikacji.  
  
## <a name="see-also"></a>Zobacz też  
 [Elementy DataSet, DataTable i DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów](http://go.microsoft.com/fwlink/?LinkId=217917)
