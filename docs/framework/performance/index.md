---
title: "Wydajność środowiska .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance [.NET Framework]
- reliability [.NET Framework]
ms.assetid: c1676cca-3f1a-41ec-b469-9029566074fc
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1d1e1de5637dbb955dd72ed0291da1f4f537ce28
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="net-framework-performance"></a><span data-ttu-id="89685-102">Wydajność środowiska .NET Framework</span><span class="sxs-lookup"><span data-stu-id="89685-102">.NET Framework Performance</span></span>
<span data-ttu-id="89685-103">Jeśli chcesz utworzyć aplikacje o bardzo dużej wydajności, projektowanie i Planowanie wydajności tylko innych funkcji aplikacji czy projektu.</span><span class="sxs-lookup"><span data-stu-id="89685-103">If you want to create apps with great performance, you should design and plan for performance just as you would design any other feature of your app.</span></span> <span data-ttu-id="89685-104">Można używać narzędzi dostarczanych przez firmę Microsoft do mierzenia wydajności aplikacji i, w razie potrzeby poprawiają wykorzystanie pamięci, kod przepływności i czasu odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="89685-104">You can use the tools provided by Microsoft to measure your app's performance, and, if needed, make improvements to memory use, code throughput, and responsiveness.</span></span> <span data-ttu-id="89685-105">W tym temacie wymieniono narzędzia analizy wydajności firmy Microsoft zapewnia i łącza do innych tematów, które obejmują wydajność dla określonych obszarach tworzenia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="89685-105">This topic lists the performance analysis tools that Microsoft provides, and provides links to other topics that cover performance for specific areas of app development.</span></span>  
  
## <a name="designing-and-planning-for-performance"></a><span data-ttu-id="89685-106">Projektowanie i Planowanie wydajności</span><span class="sxs-lookup"><span data-stu-id="89685-106">Designing and planning for performance</span></span>  
 <span data-ttu-id="89685-107">Jeśli chcesz wspaniałej aplikacji zostanie wykonana, należy projektować wydajności w swojej aplikacji tak samo, jak będzie projektowania innych funkcji.</span><span class="sxs-lookup"><span data-stu-id="89685-107">If you want a great performing app, you must design performance into your app just as you would design any other feature.</span></span> <span data-ttu-id="89685-108">Wczesne i często należy określić scenariuszy o kluczowym znaczeniu wydajności w aplikacji, ustaw cele dotyczące wydajności i miar wydajności dotyczących następujących scenariuszy aplikacji.</span><span class="sxs-lookup"><span data-stu-id="89685-108">You should determine the performance-critical scenarios in your app, set performance goals, and measure performance for these app scenarios early and often.</span></span> <span data-ttu-id="89685-109">Ponieważ każdej aplikacji jest inna i ma inny wykonywania krytyczne wydajności ścieżki, wczesne określenie tych ścieżek i skupienie wysiłków umożliwiają zmaksymalizować wydajność pracy.</span><span class="sxs-lookup"><span data-stu-id="89685-109">Because each app is different and has different performance-critical execution paths, determining those paths early and focusing your efforts enable you to maximize your productivity.</span></span>  
  
 <span data-ttu-id="89685-110">Nie trzeba znać całkowicie docelowej platformy do utworzenia aplikacji wysokiej wydajności.</span><span class="sxs-lookup"><span data-stu-id="89685-110">You don’t have to be completely familiar with your target platform to create a high-performance app.</span></span> <span data-ttu-id="89685-111">Jednak należy opracować zrozumienia części docelowej platformy jest kosztowna pod względem wydajności.</span><span class="sxs-lookup"><span data-stu-id="89685-111">However, you should develop an understanding of which parts of your target platform are costly in terms of performance.</span></span> <span data-ttu-id="89685-112">Można to zrobić przez pomiaru wydajności wcześnie w procesie tworzenia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="89685-112">You can do this by measuring performance early in your development process.</span></span>  
  
 <span data-ttu-id="89685-113">Określenie obszarów, które są istotne wydajności i ustanowienie cele wydajności, zawsze należy wziąć pod uwagę środowisko użytkownika.</span><span class="sxs-lookup"><span data-stu-id="89685-113">To determine the areas that are crucial to performance and to establish your performance goals, always consider the user experience.</span></span> <span data-ttu-id="89685-114">Czas uruchamiania i czas odpowiedzi są dwóch podstawowych obszarach, które wpłyną na użytkownika z punktu widzenia użytkownika aplikacji.</span><span class="sxs-lookup"><span data-stu-id="89685-114">Startup time and responsiveness are two key areas that will affect the user’s perception of your app.</span></span> <span data-ttu-id="89685-115">Jeśli aplikacja korzysta z dużej ilości pamięci, może występować wolna dla użytkownika lub mieć wpływ na inne aplikacje uruchomione w systemie lub, w niektórych przypadkach można niepowodzenie procesu przesyłania Sklepu Windows lub Sklepu Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="89685-115">If your app uses a lot of memory, it may appear sluggish to the user or affect other apps running on the system, or, in some cases, it could fail the Windows Store or Windows Phone Store submission process.</span></span> <span data-ttu-id="89685-116">Ponadto jeśli okaże się, które części kodu wykonania częściej, można upewnij się, że te fragmenty kodu są również zoptymalizowane pod.</span><span class="sxs-lookup"><span data-stu-id="89685-116">Also, if you determine which parts of your code execute more frequently, you can make sure that these portions of your code are well optimized.</span></span>  
  
## <a name="analyzing-performance"></a><span data-ttu-id="89685-117">Analizowanie wydajności</span><span class="sxs-lookup"><span data-stu-id="89685-117">Analyzing performance</span></span>  
 <span data-ttu-id="89685-118">W ramach ogólnego planu rozwoju Ustaw punkty podczas programowania gdzie będą mierzyć wydajność aplikacji i porównywania wyników z wcześniej określonych celów.</span><span class="sxs-lookup"><span data-stu-id="89685-118">As part of your overall development plan, set points during development where you will measure the performance of your app and compare the results with the goals you set previously.</span></span> <span data-ttu-id="89685-119">Zmierz aplikacji w środowisku i sprzętu, na którym oczekujesz swoim użytkownikom.</span><span class="sxs-lookup"><span data-stu-id="89685-119">Measure your app in the environment and hardware that you expect your users to have.</span></span> <span data-ttu-id="89685-120">Za analizowanie wydajności aplikacji, wczesne i często można zmienić architektury decyzje, które mogą być kosztowne i kosztowne naprawa później w cyklu programowania.</span><span class="sxs-lookup"><span data-stu-id="89685-120">By analyzing your app’s performance early and often you can change architectural decisions that would be costly and expensive to fix later in the development cycle.</span></span> <span data-ttu-id="89685-121">W poniższych sekcjach opisano narzędzia wydajności, których można użyć do analizowania aplikacji i śledzenie zdarzeń, który jest używany przez te narzędzia omówiono w nim.</span><span class="sxs-lookup"><span data-stu-id="89685-121">The following sections describe performance tools you can use to analyze your apps and discuss event tracing, which is used by these tools.</span></span>  
  
### <a name="performance-tools"></a><span data-ttu-id="89685-122">Narzędzia wydajności</span><span class="sxs-lookup"><span data-stu-id="89685-122">Performance tools</span></span>  
 <span data-ttu-id="89685-123">Poniżej przedstawiono niektóre narzędzi wydajności, których można używać z aplikacji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="89685-123">Here are some of the performance tools you can use with your .NET Framework apps.</span></span>  
  
|<span data-ttu-id="89685-124">Narzędzie</span><span class="sxs-lookup"><span data-stu-id="89685-124">Tool</span></span>|<span data-ttu-id="89685-125">Opis</span><span class="sxs-lookup"><span data-stu-id="89685-125">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="89685-126">Analiza wydajności programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89685-126">Visual Studio Performance Analysis</span></span>|<span data-ttu-id="89685-127">Umożliwia analizowanie użycia procesora CPU aplikacji .NET Framework, które zostanie wdrożone na komputerach z systemem systemu operacyjnego Windows.</span><span class="sxs-lookup"><span data-stu-id="89685-127">Use to analyze the CPU usage of your .NET Framework apps that will be deployed to computers that are running the Windows operating system.</span></span><br /><br /> <span data-ttu-id="89685-128">To narzędzie jest dostępne z **debugowania** menu w programie Visual Studio po otwarciu projektu.</span><span class="sxs-lookup"><span data-stu-id="89685-128">This tool is available from the **Debug** menu in Visual Studio after you open a project.</span></span> <span data-ttu-id="89685-129">Aby uzyskać więcej informacji, zobacz [Eksplorator wydajności](/visualstudio/profiling/performance-explorer).</span><span class="sxs-lookup"><span data-stu-id="89685-129">For more information, see [Performance Explorer](/visualstudio/profiling/performance-explorer).</span></span> <span data-ttu-id="89685-130">**Uwaga:** analizy aplikacji Windows Phone Użyj (zobacz następnego wiersza) gdy Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="89685-130">**Note:**  Use Windows Phone Application Analysis (see next row) when targeting Windows Phone.</span></span>|  
|<span data-ttu-id="89685-131">Analiza aplikacji Windows Phone</span><span class="sxs-lookup"><span data-stu-id="89685-131">Windows Phone Application Analysis</span></span>|<span data-ttu-id="89685-132">Służy do analizowania procesora CPU i pamięci, szybkość transferu danych w sieci, czas odpowiedzi aplikacji i zużycie baterii w aplikacji Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="89685-132">Use to analyze the CPU and memory, network data transfer rate, app responsiveness, and battery consumption in your Windows Phone apps.</span></span><br /><br /> <span data-ttu-id="89685-133">To narzędzie jest dostępne z **debugowania** menu dla projektu Windows Phone w programie Visual Studio po zainstalowaniu [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=265773).</span><span class="sxs-lookup"><span data-stu-id="89685-133">This tool is available from the **Debug** menu for a Windows Phone project in Visual Studio after you install the [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=265773).</span></span> <span data-ttu-id="89685-134">Aby uzyskać więcej informacji, zobacz [profilowania aplikacji Windows Phone](http://msdn.microsoft.com/library/windowsphone/develop/jj215908\(v=vs.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="89685-134">For more information, see [App profiling for Windows Phone](http://msdn.microsoft.com/library/windowsphone/develop/jj215908\(v=vs.105\).aspx).</span></span>|  
|[<span data-ttu-id="89685-135">Narzędzia PerfView</span><span class="sxs-lookup"><span data-stu-id="89685-135">PerfView</span></span>](http://www.microsoft.com/download/details.aspx?id=28567)|<span data-ttu-id="89685-136">Służy do identyfikowania Procesora i problemy z wydajnością związane z pamięcią.</span><span class="sxs-lookup"><span data-stu-id="89685-136">Use to identify CPU and memory-related performance issues.</span></span> <span data-ttu-id="89685-137">To narzędzie używa śledzenie zdarzeń systemu Windows (ETW) i CLR profilowania interfejsów API, aby zapewnić zaawansowane pamięci i Procesora dochodzenia, a także informacje o czyszczeniu i kompilacji JIT.</span><span class="sxs-lookup"><span data-stu-id="89685-137">This tool uses event tracing for Windows (ETW)  and CLR profiling APIs to provide advanced memory and CPU investigations as well as information about garbage collection and JIT compilation.</span></span> <span data-ttu-id="89685-138">Aby uzyskać więcej informacji na temat używania narzędzia PerfView Zobacz pliki samouczka i pomocy, które są dołączone do aplikacji, [samouczki wideo z witryny Channel 9](http://channel9.msdn.com/Series/PerfView-Tutorial), i [blogach](http://blogs.msdn.com/b/vancem/archive/tags/perfview/).</span><span class="sxs-lookup"><span data-stu-id="89685-138">For more information about how to use PerfView, see the tutorial and help files that are included with the app, [Channel 9 video tutorials](http://channel9.msdn.com/Series/PerfView-Tutorial), and [blog posts](http://blogs.msdn.com/b/vancem/archive/tags/perfview/).</span></span><br /><br /> <span data-ttu-id="89685-139">Problemy dotyczące pamięci, zobacz [przy użyciu narzędzia PerfView dochodzeń pamięci](http://channel9.msdn.com/Series/PerfView-Tutorial/PerfView-Tutorial-9-NET-Memory-Investigation-Basics-of-GC-Heap-Snapshots).</span><span class="sxs-lookup"><span data-stu-id="89685-139">For memory-specific issues, see [Using PerfView for Memory Investigations](http://channel9.msdn.com/Series/PerfView-Tutorial/PerfView-Tutorial-9-NET-Memory-Investigation-Basics-of-GC-Heap-Snapshots).</span></span>|  
|[<span data-ttu-id="89685-140">Analizator wydajności systemu Windows</span><span class="sxs-lookup"><span data-stu-id="89685-140">Windows Performance Analyzer</span></span>](http://www.microsoft.com/download/details.aspx?id=30652)|<span data-ttu-id="89685-141">Służy do określania ogólnej wydajności systemu, takie jak pamięci oraz Magazyn aplikacji używać po wielu aplikacji uruchomionych na tym samym komputerze.</span><span class="sxs-lookup"><span data-stu-id="89685-141">Use to determine overall system performance such as your app's memory and storage use when multiple apps are running on the same computer.</span></span> <span data-ttu-id="89685-142">To narzędzie jest dostępny z Centrum pobierania jako część systemu Windows Assessment and Deployment Kit (ADK) dla [!INCLUDE[win8](../../../includes/win8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89685-142">This tool is available from the download center as part of the Windows Assessment and Deployment Kit (ADK) for [!INCLUDE[win8](../../../includes/win8-md.md)].</span></span> <span data-ttu-id="89685-143">Aby uzyskać więcej informacji, zobacz [Analizator wydajności systemu Windows](http://msdn.microsoft.com/library/windows/desktop/hh448170.aspx).</span><span class="sxs-lookup"><span data-stu-id="89685-143">For more information, see [Windows Performance Analyzer](http://msdn.microsoft.com/library/windows/desktop/hh448170.aspx).</span></span>|  
  
### <a name="event-tracing-for-windows-etw"></a><span data-ttu-id="89685-144">Śledzenie zdarzeń systemu Windows (ETW)</span><span class="sxs-lookup"><span data-stu-id="89685-144">Event tracing for Windows (ETW)</span></span>  
 <span data-ttu-id="89685-145">ETW to technika pozwala uzyskać informacje diagnostyczne o uruchamianiu kodu, który ma zasadnicze znaczenie dla wielu narzędzi wydajności wymienione wcześniej.</span><span class="sxs-lookup"><span data-stu-id="89685-145">ETW is a technique that lets you obtain diagnostic information about running code and is essential for many of the performance tools mentioned previously.</span></span> <span data-ttu-id="89685-146">ETW tworzy Dzienniki aplikacji programu .NET Framework i Windows są generowane określonego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="89685-146">ETW creates logs when particular events are raised by .NET Framework apps and Windows.</span></span> <span data-ttu-id="89685-147">Za pomocą funkcji ETW można włączyć i wyłączyć rejestrowanie dynamicznie, tak, aby można było wykonać szczegółowe śledzenie w środowisku produkcyjnym bez ponownego uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="89685-147">With ETW, you can enable and disable logging dynamically, so that you can perform detailed tracing in a production environment without restarting your app.</span></span> <span data-ttu-id="89685-148">.NET Framework zapewnia obsługę zdarzeń ETW i ETW jest używany przez wiele narzędzi do profilowania i wydajności do wygenerowania danych dotyczących wydajności.</span><span class="sxs-lookup"><span data-stu-id="89685-148">The .NET Framework offers support for ETW events, and ETW is used by many profiling and performance tools to generate performance data.</span></span> <span data-ttu-id="89685-149">Te narzędzia często Włączanie i wyłączanie zdarzenia ETW, więc ich znajomości jest przydatne.</span><span class="sxs-lookup"><span data-stu-id="89685-149">These tools often enable and disable ETW events, so familiarity with them is helpful.</span></span> <span data-ttu-id="89685-150">Określonych zdarzeń ETW służy do zbierania informacji o konkretnym składniki wydajności aplikacji.</span><span class="sxs-lookup"><span data-stu-id="89685-150">You can use specific ETW events to collect performance information about particular components of your app.</span></span> <span data-ttu-id="89685-151">Aby uzyskać więcej informacji na temat obsługi funkcji ETW w programie .NET Framework, zobacz [zdarzenia ETW w środowisku uruchomieniowym języka](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md) i [zdarzenia ETW w bibliotece równoległych zadań i PLINQ](../../../docs/framework/performance/etw-events-in-task-parallel-library-and-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="89685-151">For more information about ETW support in the .NET Framework, see [ETW Events in the Common Language Runtime](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md) and [ETW Events in Task Parallel Library and PLINQ](../../../docs/framework/performance/etw-events-in-task-parallel-library-and-plinq.md).</span></span>  
  
## <a name="performance-by-app-type"></a><span data-ttu-id="89685-152">Wydajność przez typ aplikacji</span><span class="sxs-lookup"><span data-stu-id="89685-152">Performance by app type</span></span>  
 <span data-ttu-id="89685-153">Każdy typ aplikacji .NET Framework ma własną najlepszych praktyk, zagadnienia i narzędzia do oceny wydajności.</span><span class="sxs-lookup"><span data-stu-id="89685-153">Each type of .NET Framework app has its own best practices, considerations, and tools for evaluating performance.</span></span> <span data-ttu-id="89685-154">Poniższe łącza tabeli do tematów wydajność dla określonych typów aplikacji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="89685-154">The following table links to performance topics for specific .NET Framework app types.</span></span>  
  
|<span data-ttu-id="89685-155">Typ aplikacji</span><span class="sxs-lookup"><span data-stu-id="89685-155">App type</span></span>|<span data-ttu-id="89685-156">Zobacz</span><span class="sxs-lookup"><span data-stu-id="89685-156">See</span></span>|  
|--------------|---------|  
|<span data-ttu-id="89685-157">Aplikacje środowiska .NET framework dla wszystkich platform</span><span class="sxs-lookup"><span data-stu-id="89685-157">.NET Framework apps for all platforms</span></span>|[<span data-ttu-id="89685-158">Wyrzucanie elementów bezużytecznych i wydajność</span><span class="sxs-lookup"><span data-stu-id="89685-158">Garbage Collection and Performance</span></span>](../../../docs/standard/garbage-collection/performance.md)<br /><br /> [<span data-ttu-id="89685-159">Porady dotyczące wydajności</span><span class="sxs-lookup"><span data-stu-id="89685-159">Performance Tips</span></span>](../../../docs/framework/performance/performance-tips.md)|  
|[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]<span data-ttu-id="89685-160">aplikacji napisanych w języku C++, C# i Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89685-160"> apps written in C++, C#, and Visual Basic</span></span>|[<span data-ttu-id="89685-161">Najlepsze praktyki wydajności dla aplikacji ze Sklepu Windows przy użyciu języka C++, C# i Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89685-161">Performance best practices for Windows Store apps using C++, C#, and Visual Basic</span></span>](http://msdn.microsoft.com/library/windows/apps/hh750313.aspx)|  
|<span data-ttu-id="89685-162">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="89685-162">Windows Phone</span></span>|<span data-ttu-id="89685-163">[Zagadnienia dotyczące wydajności aplikacji Windows Phone](http://msdn.microsoft.com/library/windowsphone/develop/ff967560\(v=vs.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="89685-163">[App performance considerations for Windows Phone](http://msdn.microsoft.com/library/windowsphone/develop/ff967560\(v=vs.105\).aspx)</span></span><br /><br /> <span data-ttu-id="89685-164">[Analiza aplikacji Windows Phone](http://msdn.microsoft.com/library/windowsphone/develop/hh202934\(v=vs.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="89685-164">[Windows Phone Application Analysis](http://msdn.microsoft.com/library/windowsphone/develop/hh202934\(v=vs.105\).aspx)</span></span><br /><br /> [<span data-ttu-id="89685-165">Pobierz aplikacje Windows Phone w witrynie Marketplace szybsze</span><span class="sxs-lookup"><span data-stu-id="89685-165">Get Your Windows Phone Applications in the Marketplace Faster</span></span>](http://msdn.microsoft.com/magazine/hh781024.aspx)|  
|<span data-ttu-id="89685-166">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="89685-166">Windows Presentation Foundation (WPF)</span></span>|[<span data-ttu-id="89685-167">Pakiet wydajności WPF</span><span class="sxs-lookup"><span data-stu-id="89685-167">WPF Performance Suite</span></span>](http://msdn.microsoft.com/library/67cafaad-57ad-4ecb-9c08-57fac144393e)|  
|<span data-ttu-id="89685-168">Silverlight</span><span class="sxs-lookup"><span data-stu-id="89685-168">Silverlight</span></span>|<span data-ttu-id="89685-169">[Porady dotyczące wydajności](http://msdn.microsoft.com/library/cc189071\(v=vs.95\).aspx)</span><span class="sxs-lookup"><span data-stu-id="89685-169">[Performance tips](http://msdn.microsoft.com/library/cc189071\(v=vs.95\).aspx)</span></span>|  
|<span data-ttu-id="89685-170">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="89685-170">ASP.NET</span></span>|[<span data-ttu-id="89685-171">Omówienie wydajności programu ASP.NET</span><span class="sxs-lookup"><span data-stu-id="89685-171">ASP.NET Performance Overview</span></span>](http://msdn.microsoft.com/library/f882bf1b-a009-4312-ac06-74370ffabc0b)|  
|<span data-ttu-id="89685-172">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89685-172">Windows Forms</span></span>|[<span data-ttu-id="89685-173">Praktyczne wskazówki dotyczące zwiększania wydajności aplikacji formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="89685-173">Practical Tips for Boosting the Performance of Windows Forms Apps</span></span>](http://msdn.microsoft.com/magazine/cc163630.aspx)|  
  
## <a name="related-topics"></a><span data-ttu-id="89685-174">Tematy pokrewne</span><span class="sxs-lookup"><span data-stu-id="89685-174">Related Topics</span></span>  
  
|<span data-ttu-id="89685-175">Tytuł</span><span class="sxs-lookup"><span data-stu-id="89685-175">Title</span></span>|<span data-ttu-id="89685-176">Opis</span><span class="sxs-lookup"><span data-stu-id="89685-176">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="89685-177">Buforowanie w aplikacjach .NET Framework</span><span class="sxs-lookup"><span data-stu-id="89685-177">Caching in .NET Framework Applications</span></span>](../../../docs/framework/performance/caching-in-net-framework-applications.md)|<span data-ttu-id="89685-178">Opisuje metody do buforowania danych w celu zwiększenia wydajności w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="89685-178">Describes techniques for caching data to improve performance in your app.</span></span>|  
|[<span data-ttu-id="89685-179">Inicjalizacja z opóźnieniem</span><span class="sxs-lookup"><span data-stu-id="89685-179">Lazy Initialization</span></span>](../../../docs/framework/performance/lazy-initialization.md)|<span data-ttu-id="89685-180">Zawiera opis sposobu zainicjowania obiekty wymagane do zwiększenia wydajności, szczególnie podczas uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="89685-180">Describes how to initialize objects as-needed to improve performance, particularly at app startup.</span></span>|  
|[<span data-ttu-id="89685-181">Niezawodność</span><span class="sxs-lookup"><span data-stu-id="89685-181">Reliability</span></span>](../../../docs/framework/performance/reliability.md)|<span data-ttu-id="89685-182">Zawiera informacje dotyczące zapobiegania asynchroniczne wyjątki w środowisku serwera.</span><span class="sxs-lookup"><span data-stu-id="89685-182">Provides information about preventing asynchronous exceptions in a server environment.</span></span>|  
|[<span data-ttu-id="89685-183">Pisanie dużych i sprawnie działających .NET Framework aplikacje</span><span class="sxs-lookup"><span data-stu-id="89685-183">Writing Large, Responsive .NET Framework Apps</span></span>](../../../docs/framework/performance/writing-large-responsive-apps.md)|<span data-ttu-id="89685-184">Zawiera wskazówki dotyczące wydajności zebrane z ponowne zapisywanie C# i Visual Basic kompilatory w kodzie zarządzanym i zawiera kilka przykładów rzeczywistych kompilatora C#.</span><span class="sxs-lookup"><span data-stu-id="89685-184">Provides performance tips gathered from rewriting the C# and Visual Basic compilers in managed code, and includes several real examples from the C# compiler.</span></span>|