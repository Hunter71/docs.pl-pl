### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="74a26-101">Połączenie nie może nawiązać 1997 serwera SQL lub bazy danych za pomocą karty VIA</span><span class="sxs-lookup"><span data-stu-id="74a26-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="74a26-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="74a26-102">Details</span></span>|<span data-ttu-id="74a26-103">Połączenia z bazami danych programu SQL Server przy użyciu [wirtualne karty interfejsu (VIA) protokołu](https://technet.microsoft.com/library/ms191229%28v=sql.105%29.aspx) nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="74a26-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](https://technet.microsoft.com/library/ms191229%28v=sql.105%29.aspx) are no longer supported.</span></span> <span data-ttu-id="74a26-104">Protokół używany do łączenia z bazą danych programu SQL Server jest widoczna w parametrach połączenia.</span><span class="sxs-lookup"><span data-stu-id="74a26-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="74a26-105">Połączenie VIA będzie zawierać za pośrednictwem:&lt;servername&gt;.</span><span class="sxs-lookup"><span data-stu-id="74a26-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="74a26-106">Jeśli ta aplikacja łączy się z serwerem SQL za pomocą protokołu innego niż VIA (tcp: lub np: na przykład), a następnie nie istotne zmiany będą napotkał. Ponadto połączenia SQL Server 7 (1997) nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="74a26-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>|
|<span data-ttu-id="74a26-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="74a26-107">Suggestion</span></span>|<span data-ttu-id="74a26-108">Protokół VIA jest przestarzały, więc alternatywnych protokołu używanego do nawiązania połączenia bazy danych SQL.</span><span class="sxs-lookup"><span data-stu-id="74a26-108">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="74a26-109">Protokół najczęściej używany jest protokół TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="74a26-109">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="74a26-110">Instrukcje dotyczące włączania protokołu TCP/IP można znaleźć [tutaj](https://msdn.microsoft.com/library/bb909712.aspx).</span><span class="sxs-lookup"><span data-stu-id="74a26-110">Instructions for enabling the TCP/IP protocol can be found [here](https://msdn.microsoft.com/library/bb909712.aspx).</span></span> <span data-ttu-id="74a26-111">Jeśli bazy danych jest dostępne tylko z w intranecie, protokołu potoków udostępnionego może zapewnić lepszą wydajność, jeśli sieć jest powolne.</span><span class="sxs-lookup"><span data-stu-id="74a26-111">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>|
|<span data-ttu-id="74a26-112">Zakres</span><span class="sxs-lookup"><span data-stu-id="74a26-112">Scope</span></span>|<span data-ttu-id="74a26-113">Krawędź</span><span class="sxs-lookup"><span data-stu-id="74a26-113">Edge</span></span>|
|<span data-ttu-id="74a26-114">Wersja</span><span class="sxs-lookup"><span data-stu-id="74a26-114">Version</span></span>|<span data-ttu-id="74a26-115">4.5</span><span class="sxs-lookup"><span data-stu-id="74a26-115">4.5</span></span>|
|<span data-ttu-id="74a26-116">Typ</span><span class="sxs-lookup"><span data-stu-id="74a26-116">Type</span></span>|<span data-ttu-id="74a26-117">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="74a26-117">Runtime</span></span>|
|<span data-ttu-id="74a26-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="74a26-118">Affected APIs</span></span>|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|
