### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="da9a1-101">Nazwy zdarzeń funkcji ETW nie może się różnić tylko sufiksem "Start" lub "Stop"</span><span class="sxs-lookup"><span data-stu-id="da9a1-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

|   |   |
|---|---|
|<span data-ttu-id="da9a1-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="da9a1-102">Details</span></span>|<span data-ttu-id="da9a1-103">.NET Framework 4.6 i 4.6.1 zgłasza wyjątek środowiska uruchomieniowego <xref:System.ArgumentException> gdy dwie nazwy zdarzenia funkcji Śledzenie zdarzeń systemu Windows () różnią się tylko w programie &quot;Start&quot; lub &quot;zatrzymać&quot; sufiks (jako po nazwie jedno zdarzenie <code>LogUser</code>i o innej nazwie <code>LogUserStart</code>).</span><span class="sxs-lookup"><span data-stu-id="da9a1-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix (as when one event is named <code>LogUser</code> and another is named <code>LogUserStart</code>).</span></span> <span data-ttu-id="da9a1-104">W takim przypadku środowisko uruchomieniowe nie można utworzyć źródła zdarzeń, którego nie można wyemitować żadnych rejestrowania.</span><span class="sxs-lookup"><span data-stu-id="da9a1-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>|
|<span data-ttu-id="da9a1-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="da9a1-105">Suggestion</span></span>|<span data-ttu-id="da9a1-106">Aby zapobiec wyjątek, upewnij się, że żadne nazwy dwóch zdarzeń różnią się tylko w programie &quot;Start&quot; lub &quot;zatrzymać&quot; sufiks. To wymaganie nie obowiązuje w programie .NET Framework 4.6.2; środowisko uruchomieniowe można odróżniania nazw zdarzeń, które różnią się tylko przez &quot;Start&quot; i &quot;zatrzymać&quot; sufiks.</span><span class="sxs-lookup"><span data-stu-id="da9a1-106">To prevent the exception, ensure that no two event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the &quot;Start&quot; and &quot;Stop&quot; suffix.</span></span>|
|<span data-ttu-id="da9a1-107">Zakres</span><span class="sxs-lookup"><span data-stu-id="da9a1-107">Scope</span></span>|<span data-ttu-id="da9a1-108">Krawędź</span><span class="sxs-lookup"><span data-stu-id="da9a1-108">Edge</span></span>|
|<span data-ttu-id="da9a1-109">Wersja</span><span class="sxs-lookup"><span data-stu-id="da9a1-109">Version</span></span>|<span data-ttu-id="da9a1-110">4.6</span><span class="sxs-lookup"><span data-stu-id="da9a1-110">4.6</span></span>|
|<span data-ttu-id="da9a1-111">Typ</span><span class="sxs-lookup"><span data-stu-id="da9a1-111">Type</span></span>|<span data-ttu-id="da9a1-112">Przekierowania</span><span class="sxs-lookup"><span data-stu-id="da9a1-112">Retargeting</span></span>|
