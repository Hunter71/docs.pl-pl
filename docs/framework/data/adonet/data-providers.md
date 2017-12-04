---
title: Dostawcy danych .NET framework
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
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
caps.latest.revision: "13"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4c11b826a51cc4f1563729728626fb8041e31ee1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="net-framework-data-providers"></a>Dostawcy danych .NET framework
A [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawca danych służy do nawiązywania połączenia z bazą danych, wykonywania poleceń i pobierania wyników. Wyniki są albo przetwarzane bezpośrednio, umieszczone w <xref:System.Data.DataSet> aby widoczne dla użytkownika, zgodnie z potrzebami, połączony z danymi z wielu źródeł lub węzłach między warstwami. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]dostawcy danych to lekkie, tworzenie minimalnego warstwy między źródłem danych i kod, zwiększenie wydajności bez ograniczania funkcjonalności.  
  
 W poniższej tabeli wymieniono dostawcy danych, które są objęte [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych|Opis|  
|-------------------------------------------------------------------------------|-----------------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych dla[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]|Zapewnia dostęp do danych firmy Microsoft [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]. Używa <xref:System.Data.SqlClient> przestrzeni nazw.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych OLE DB dla|Dla źródeł danych udostępniany przy użyciu OLE DB. Używa <xref:System.Data.OleDb> przestrzeni nazw.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych dla ODBC|Dla źródeł danych udostępnianych przez za pośrednictwem sterownika ODBC. Używa <xref:System.Data.Odbc> przestrzeni nazw.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych dla programu Oracle|Dla źródła danych programu Oracle. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych programu Oracle obsługuje Oracle oprogramowania klienta w wersji version 8.1.7 lub nowszej i używa <xref:System.Data.OracleClient> przestrzeni nazw.|  
|Dostawca EntityClient|Zapewnia dostęp do danych dla modelu danych jednostki (EDM) aplikacji. Używa <xref:System.Data.EntityClient> przestrzeni nazw.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] Compact 4.0.|Zapewnia dostęp do danych firmy Microsoft [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] Compact 4.0. Używa [System.Data.SqlServerCe](http://msdn.microsoft.com/library/system.data.sqlserverce.aspx) przestrzeni nazw.|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Podstawowych obiektów dostawcy danych .NET Framework  
 W poniższej tabeli przedstawiono cztery podstawowych obiektów, które tworzą [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych.  
  
|Obiekt|Opis|  
|------------|-----------------|  
|`Connection`|Ustanawia połączenie z określonego źródła danych. Klasa podstawowa dla wszystkich `Connection` obiektów jest <xref:System.Data.Common.DbConnection> klasy.|  
|`Command`|Wykonuje polecenie względem źródła danych. Przedstawia `Parameters` i może zostać uruchomiony w zakresie `Transaction` z `Connection`. Klasa podstawowa dla wszystkich `Command` obiektów jest <xref:System.Data.Common.DbCommand> klasy.|  
|`DataReader`|Odczytuje tylko do przodu, tylko do odczytu strumienia danych ze źródła danych. Klasa podstawowa dla wszystkich `DataReader` obiektów jest <xref:System.Data.Common.DbDataReader> klasy.|  
|`DataAdapter`|Wypełnia `DataSet` i rozpoznawany jako aktualizacje ze źródłem danych. Klasa podstawowa dla wszystkich `DataAdapter` obiektów jest <xref:System.Data.Common.DbDataAdapter> klasy.|  
  
 Oprócz podstawowe klasy wymienione w tabeli wcześniej w tym dokumencie [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych zawiera także klas wymienionych w poniższej tabeli.  
  
|Obiekt|Opis|  
|------------|-----------------|  
|`Transaction`|Rejestruje poleceń w transakcji w źródle danych. Klasa podstawowa dla wszystkich `Transaction` obiektów jest <xref:System.Data.Common.DbTransaction> klasy. ADO.NET także zapewnia obsługę transakcji za pomocą klasy w <xref:System.Transactions> przestrzeni nazw.|  
|`CommandBuilder`|Obiekt pomocnika, które automatycznie generuje właściwości polecenia `DataAdapter` lub uzyskuje informacje o parametrach procedury składowanej i wypełnia `Parameters` Kolekcja `Command` obiektu. Klasa podstawowa dla wszystkich `CommandBuilder` obiektów jest <xref:System.Data.Common.DbCommandBuilder> klasy.|  
|`ConnectionStringBuilder`|Obiekt pomocnika, która zapewnia prosty sposób tworzenia i zarządzania zawartością parametrów połączeń używanych przez `Connection` obiektów. Klasa podstawowa dla wszystkich `ConnectionStringBuilder` obiektów jest <xref:System.Data.Common.DbConnectionStringBuilder> klasy.|  
|`Parameter`|Definiuje danych wejściowych, wyjściowych i parametrów wartości zwracanej dla poleceń i procedur składowanych. Klasa podstawowa dla wszystkich `Parameter` obiektów jest <xref:System.Data.Common.DbParameter> klasy.|  
|`Exception`|Zwracany, gdy wystąpi błąd w źródle danych. Wystąpił błąd wystąpił na kliencie [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] throw dostawców danych [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] wyjątku. Klasa podstawowa dla wszystkich `Exception` obiektów jest <xref:System.Data.Common.DbException> klasy.|  
|`Error`|Udostępnia informacje, ostrzeżenie lub błąd zwrócony przez źródło danych.|  
|`ClientPermission`|Podany dla [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] atrybutów zabezpieczeń dostępu kodu dostawcy danych. Klasa podstawowa dla wszystkich `ClientPermission` obiektów jest <xref:System.Data.Common.DBDataPermission> klasy.|  
  
## <a name="net-framework-data-provider-for-includessnoversionincludesssnoversion-mdmd-sqlclient"></a>Dostawca danych programu .NET framework dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] (SqlClient)  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] (SqlClient) używa własnego protokołu do komunikowania się z [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]. Jest lekki i wykonuje dobrze, ponieważ jest zoptymalizowany do dostępu [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] bezpośrednio, bez dodawania warstwy OLE DB lub Otwórz połączenie bazy danych (ODBC). Poniższej ilustracji zestawiono ze sobą [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] z [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych OLE DB. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych OLE DB komunikuje się ze źródłem danych OLE DB za pomocą obu usługi OLE DB składnika, który zapewnia puli połączeń i transakcji usługi i dostawcy OLE DB dla źródła danych.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych ODBC ma podobną architekturę do [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych OLE DB; na przykład wywołuje do składnika usługi ODBC.  
  
 ![Dostawcy danych](../../../../docs/framework/data/adonet/media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Porównanie dostawcy danych programu .NET Framework dla programu SQL Server i .NET Framework Data Provider for OLE DB  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] klasy znajdują się w <xref:System.Data.SqlClient> przestrzeni nazw.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] obsługuje zarówno lokalnych, jak i rozproszonych transakcje. W przypadku transakcji rozproszonych [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], domyślnie automatycznie rejestruje w transakcji i uzyskuje dostęp do szczegółów transakcji z usługi składników systemu Windows lub <xref:System.Transactions>. Aby uzyskać więcej informacji, zobacz [transakcji i współbieżność](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Poniższy przykładowy kod przedstawia sposób obejmują `System.Data.SqlClient` przestrzeni nazw w aplikacji.  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>Dostawca danych programu .NET framework dla OLE DB  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych OLE DB (OleDb) używa natywnego OLE DB za pomocą modelu COM interop, aby umożliwić dostęp do danych. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych OLE DB obsługuje zarówno lokalnych, jak i rozproszonych transakcje. W przypadku transakcji rozproszonych [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych OLE DB, domyślnie rejestruje w transakcji i automatycznie uzyskuje szczegóły transakcji z usługi składników systemu Windows. Aby uzyskać więcej informacji, zobacz [transakcji i współbieżność](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 W poniższej tabeli przedstawiono dostawców, które zostały przetestowane z [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
|Sterownik|Dostawcy|  
|------------|--------------|  
|SQLOLEDB|Dostawca Microsoft OLE DB dla[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]|  
|MSDAORA|Dostawca Microsoft OLE DB dla Oracle|  
|Microsoft.Jet.OLEDB.4.0|Dostawca OLE DB dla programu Microsoft Jet|  
  
> [!NOTE]
>  Przy użyciu bazy danych programu Access (Jet) jako źródła danych dla aplikacji wielowątkowych, takich jak [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplikacji, nie jest zalecane. Jeśli jako źródło danych musi używać Jet [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplikacji, należy pamiętać, że [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplikacji nawiązywania połączenia z bazą danych programu Access mogą wystąpić problemy z połączeniem.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych OLE DB nie obsługuje interfejsów wersji 2.5 OLE DB. Dostawców OLE DB wymagających pomocy technicznej dla OLE DB 2.5 interfejsy będzie działać poprawnie z [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych OLE DB. Dotyczy to również dostawcy Microsoft OLE DB dla programu Exchange i dostawcy Microsoft OLE DB dla publikacji Internet.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych OLE DB nie działa z dostawcy OLE DB dla ODBC (MSDASQL). Aby dostęp do ODBC źródła danych przy użyciu [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], użyj [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych dla ODBC.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych OLE DB klas znajdują się w <xref:System.Data.OleDb> przestrzeni nazw. Poniższy przykładowy kod przedstawia sposób obejmują `System.Data.OleDb` przestrzeni nazw w aplikacji.  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>.NET framework Data Provider for ODBC  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych ODBC (Odbc) używa natywnego Menedżera sterowników ODBC (DM), aby umożliwić dostęp do danych. Dostawca danych ODBC obsługuje zarówno lokalnych, jak i rozproszonych transakcji. Transakcji rozproszonych dostawcę danych ODBC, domyślnie rejestruje w transakcji i automatycznie uzyskuje szczegóły transakcji z usługi składników systemu Windows. Aby uzyskać więcej informacji, zobacz [transakcji i współbieżność](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 W poniższej tabeli przedstawiono sterowników ODBC przetestowana [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
|Sterownik|  
|------------|  
|[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]|  
|Microsoft ODBC dla Oracle|  
|Sterownik programu Microsoft Access (*.mdb)|  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych dla klasy ODBC znajdują się w <xref:System.Data.Odbc> przestrzeni nazw.  
  
 Poniższy przykładowy kod przedstawia sposób obejmują `System.Data.Odbc` przestrzeni nazw w aplikacji.  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych ODBC wymaga składników MDAC w wersji 2.6 lub nowszej wersji, a MDAC 2.8 SP1 jest zalecane. Możesz pobrać MDAC 2.8 z dodatkiem SP1 z [dostęp do danych i magazynu w Centrum deweloperów](http://go.microsoft.com/fwlink/?linkid=4173).  
  
## <a name="net-framework-data-provider-for-oracle"></a>.NET framework Data Provider for Oracle  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych programu Oracle (OracleClient) umożliwia dostęp do danych ze źródłami danych Oracle za pośrednictwem połączenia klienta Oracle. Dostawca danych obsługuje oprogramowania klienta Oracle w wersji version 8.1.7 lub nowszej wersji. Dostawca danych obsługuje zarówno lokalnych, jak i rozproszonych transakcji. Aby uzyskać więcej informacji, zobacz [transakcji i współbieżność](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Dostawcy danych programu Oracle wymaga oprogramowania klienta Oracle (wersji version 8.1.7 lub nowszej wersji) w systemie, zanim będzie można połączyć ze źródłem danych programu Oracle.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych programu Oracle klas znajdują się w <xref:System.Data.OracleClient> przestrzeni nazw i są zawarte w `System.Data.OracleClient.dll` zestawu. Odwołanie do obu `System.Data.dll` i `System.Data.OracleClient.dll` podczas kompilowania aplikacji, która używa dostawcy danych.  
  
 Poniższy przykładowy kod przedstawia sposób obejmują `System.Data.OracleClient` przestrzeni nazw w aplikacji.  
  
```vb  
Imports System.Data  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data;  
using System.Data.OracleClient;  
```  
  
## <a name="choosing-a-net-framework-data-provider"></a>Wybieranie dostawcy danych .NET Framework  
 W zależności od projektu i źródła danych dla aplikacji, wybór [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych może poprawić wydajność, możliwości i integralności aplikacji. Poniższa tabela zawiera omówienie korzyści i ograniczenia dotyczące każdego [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych.  
  
|Dostawcy|Uwagi|  
|--------------|-----------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych dla[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]|Zalecanym dla aplikacji warstwy środkowej, które używają programu Microsoft [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].<br /><br /> Zalecanym dla aplikacji jednowarstwową, które używają aparatu bazy danych programu Microsoft (MSDE) lub [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].<br /><br /> Zalecane przez użycie dostawcy OLE DB dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] (SQLOLEDB) z [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych OLE DB.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Dostawca danych OLE DB dla|Aby uzyskać [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dostawcy danych dla [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] zaleca się zamiast tego dostawcy.<br /><br /> Zalecane w przypadku jednowarstwową aplikacji, które używają bazy danych programu Microsoft Access. Nie zaleca się korzystanie z bazy danych programu Access dla aplikacji warstwy środkowej.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]"Dostawca danych dla ODBC|Zalecane dla Środkowej i warstwy pojedynczej aplikacji, które używają źródła danych ODBC.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]' Data Provider for Oracle|Zalecane dla Środkowej i warstwy pojedynczej aplikacji, które używają źródła danych Oracle.|  
  
## <a name="entityclient-provider"></a>Dostawca EntityClient  
 Dostawca EntityClient jest używany do uzyskiwania dostępu do danych oparte na modelu danych jednostki (EDM). W przeciwieństwie do innych .NET Framework dostawców danych nie współdziała bezpośrednio ze źródłem danych. Zamiast tego używa SQL jednostki do komunikowania się z podstawowym dostawcą danych. Aby uzyskać więcej informacji, zobacz [EntityClient i SQL jednostki](http://msdn.microsoft.com/en-us/49202ab9-ac98-4b4b-a05c-140e422bf527).  
  
## <a name="see-also"></a>Zobacz też  
 [ADO.NET — omówienie](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [Trwa pobieranie i modyfikowanie danych ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów](http://go.microsoft.com/fwlink/?LinkId=217917)