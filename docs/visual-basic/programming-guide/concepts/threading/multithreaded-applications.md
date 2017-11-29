---
title: "Aplikacje wielowątkowe (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 19a4fe40e27a9edf8515e2734914aaf02d5e48b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="multithreaded-applications-visual-basic"></a><span data-ttu-id="1279f-102">Aplikacje wielowątkowe (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1279f-102">Multithreaded Applications (Visual Basic)</span></span>
<span data-ttu-id="1279f-103">Za pomocą Visual Basic mogą pisać aplikacje, służących do wykonywania wielu zadań jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="1279f-103">With Visual Basic, you can write applications that perform multiple tasks at the same time.</span></span> <span data-ttu-id="1279f-104">Zadania związane z możliwości maksymalnie innych zadań można wykonywać w oddzielnych wątkach proces znany jako *wielowątkowość* lub *wolne wątkowość*.</span><span class="sxs-lookup"><span data-stu-id="1279f-104">Tasks with the potential of holding up other tasks can execute on separate threads, a process known as *multithreading* or *free threading*.</span></span>  
  
 <span data-ttu-id="1279f-105">Aplikacje korzystające z wielowątkowość są bardziej odpowiednie do wprowadzenia danych przez użytkownika, ponieważ interfejsu użytkownika pozostaje aktywne, jak wykonać zadania obciążenie procesora na poszczególne wątki.</span><span class="sxs-lookup"><span data-stu-id="1279f-105">Applications that use multithreading are more responsive to user input because the user interface stays active as processor-intensive tasks execute on separate threads.</span></span> <span data-ttu-id="1279f-106">Wielowątkowość jest również przydatne podczas tworzenia skalowalnych aplikacji, ponieważ użytkownik może dodać wątków w miarę wzrostu obciążenia.</span><span class="sxs-lookup"><span data-stu-id="1279f-106">Multithreading is also useful when you create scalable applications, because you can add threads as the workload increases.</span></span>  
  
## <a name="creating-and-using-threads"></a><span data-ttu-id="1279f-107">Tworzenie i używanie wątków</span><span class="sxs-lookup"><span data-stu-id="1279f-107">Creating and Using Threads</span></span>  
 <span data-ttu-id="1279f-108">Aby uzyskać większą kontrolę nad zachowanie wątków aplikacji, można zarządzać wątki samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="1279f-108">If you need more control over the behavior of your application's threads, you can manage the threads yourself.</span></span> <span data-ttu-id="1279f-109">Jednak należy pamiętać, że zapisywania poprawne wielowątkowe aplikacje mogą być trudne: aplikacja może przestać odpowiadać lub środowisko przejściowe błędy spowodowane wyścigu.</span><span class="sxs-lookup"><span data-stu-id="1279f-109">However, realize that writing correct multithreaded applications can be difficult: Your application may stop responding or experience transient errors caused by race conditions.</span></span> <span data-ttu-id="1279f-110">Aby uzyskać więcej informacji, zobacz [składniki obsługujące wielowątkowość](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span><span class="sxs-lookup"><span data-stu-id="1279f-110">For more information, see [Thread-Safe Components](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span></span>  
  
 <span data-ttu-id="1279f-111">Tworzenie nowego wątku przez deklarowanie zmiennej typu <xref:System.Threading.Thread> i wywołanie konstruktora, podając nazwę procedury lub metodę, która ma być wykonane w nowym wątku.</span><span class="sxs-lookup"><span data-stu-id="1279f-111">You create a new thread by declaring a variable of type <xref:System.Threading.Thread> and calling the constructor, providing the name of the procedure or method that you want to execute on the new thread.</span></span> <span data-ttu-id="1279f-112">Poniższy kod stanowi przykład.</span><span class="sxs-lookup"><span data-stu-id="1279f-112">The following code provides an example.</span></span>  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a><span data-ttu-id="1279f-113">Uruchamianie i zatrzymywanie wątków</span><span class="sxs-lookup"><span data-stu-id="1279f-113">Starting and Stopping Threads</span></span>  
 <span data-ttu-id="1279f-114">Aby rozpocząć wykonywanie nowego wątku, należy użyć <xref:System.Threading.Thread.Start%2A> metody, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="1279f-114">To start the execution of a new thread, use the <xref:System.Threading.Thread.Start%2A> method, as shown in the following code.</span></span>  
  
```vb  
newThread.Start()  
```  
  
 <span data-ttu-id="1279f-115">Aby zatrzymać wykonanie wątku, użyj <xref:System.Threading.Thread.Abort%2A> metody, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="1279f-115">To stop the execution of a thread, use the <xref:System.Threading.Thread.Abort%2A> method, as shown in the following code.</span></span>  
  
```vb  
newThread.Abort()  
```  
  
 <span data-ttu-id="1279f-116">Oprócz uruchamianie i zatrzymywanie wątków, można również wstrzymać wątków przez wywołanie metody <xref:System.Threading.Thread.Sleep%2A> lub <xref:System.Threading.Thread.Suspend%2A> metody wznowić wątku zawieszonym przy użyciu <xref:System.Threading.Thread.Resume%2A> metody i zniszcz wątku przy użyciu <xref:System.Threading.Thread.Abort%2A> — metoda</span><span class="sxs-lookup"><span data-stu-id="1279f-116">Besides starting and stopping threads, you can also pause threads by calling the <xref:System.Threading.Thread.Sleep%2A> or <xref:System.Threading.Thread.Suspend%2A> method, resume a suspended thread by using the <xref:System.Threading.Thread.Resume%2A> method, and destroy a thread by using the <xref:System.Threading.Thread.Abort%2A> method</span></span>  
  
### <a name="thread-methods"></a><span data-ttu-id="1279f-117">Metody wątku</span><span class="sxs-lookup"><span data-stu-id="1279f-117">Thread Methods</span></span>  
 <span data-ttu-id="1279f-118">W poniższej tabeli przedstawiono niektóre metody, których można użyć do kontrolowania poszczególnych wątków.</span><span class="sxs-lookup"><span data-stu-id="1279f-118">The following table shows some of the methods that you can use to control individual threads.</span></span>  
  
|<span data-ttu-id="1279f-119">Metoda</span><span class="sxs-lookup"><span data-stu-id="1279f-119">Method</span></span>|<span data-ttu-id="1279f-120">Akcja</span><span class="sxs-lookup"><span data-stu-id="1279f-120">Action</span></span>|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A>|<span data-ttu-id="1279f-121">Powoduje, że wątku w celu rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="1279f-121">Causes a thread to start to run.</span></span>|  
|<xref:System.Threading.Thread.Sleep%2A>|<span data-ttu-id="1279f-122">Wstrzymuje wątku przez określony czas.</span><span class="sxs-lookup"><span data-stu-id="1279f-122">Pauses a thread for a specified time.</span></span>|  
|<xref:System.Threading.Thread.Suspend%2A>|<span data-ttu-id="1279f-123">Wstrzymuje wątku po osiągnięciu bezpiecznym.</span><span class="sxs-lookup"><span data-stu-id="1279f-123">Pauses a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Abort%2A>|<span data-ttu-id="1279f-124">Zatrzymuje wątek bezpiecznym.</span><span class="sxs-lookup"><span data-stu-id="1279f-124">Stops a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Resume%2A>|<span data-ttu-id="1279f-125">Ponowne uruchomienie wątku zawieszonym</span><span class="sxs-lookup"><span data-stu-id="1279f-125">Restarts a suspended thread</span></span>|  
|<xref:System.Threading.Thread.Join%2A>|<span data-ttu-id="1279f-126">Powoduje, że bieżący wątek oczekiwania na zakończenie innego wątku.</span><span class="sxs-lookup"><span data-stu-id="1279f-126">Causes the current thread to wait for another thread to finish.</span></span> <span data-ttu-id="1279f-127">Jeśli jest używany z wartości limitu czasu, ta metoda zwraca `True` Jeśli wątek zakończy działanie w przydzielonym czasie.</span><span class="sxs-lookup"><span data-stu-id="1279f-127">If used with a time-out value, this method returns `True` if the thread finishes in the allocated time.</span></span>|  
  
### <a name="safe-points"></a><span data-ttu-id="1279f-128">Punkty bezpieczeństwa</span><span class="sxs-lookup"><span data-stu-id="1279f-128">Safe Points</span></span>  
 <span data-ttu-id="1279f-129">Większość tych metod nie wymaga wyjaśnień, ale pojęcie *punkty bezpieczeństwa* mogą być nowe dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="1279f-129">Most of these methods are self-explanatory, but the concept of *safe points* may be new to you.</span></span> <span data-ttu-id="1279f-130">Punkty bezpieczeństwa, są lokalizacje w kodzie, gdzie jest bezpieczne dla środowiska CLR na wykonywanie automatycznego *wyrzucanie elementów bezużytecznych*, proces zwalniania zmienne i odzyskiwanie pamięci.</span><span class="sxs-lookup"><span data-stu-id="1279f-130">Safe points are locations in code where it is safe for the common language runtime to perform automatic *garbage collection*, the process of releasing unused variables and reclaiming memory.</span></span> <span data-ttu-id="1279f-131">Podczas wywoływania <xref:System.Threading.Thread.Abort%2A> lub <xref:System.Threading.Thread.Suspend%2A> metoda wątku, środowisko uruchomieniowe języka wspólnego analizuje kod i określa lokalizację odpowiednią lokalizację dla wątku przestanie działać.</span><span class="sxs-lookup"><span data-stu-id="1279f-131">When you call the <xref:System.Threading.Thread.Abort%2A> or <xref:System.Threading.Thread.Suspend%2A> method of a thread, the common language runtime analyzes the code and determines the location of an appropriate location for the thread to stop running.</span></span>  
  
### <a name="thread-properties"></a><span data-ttu-id="1279f-132">Właściwości wątku</span><span class="sxs-lookup"><span data-stu-id="1279f-132">Thread Properties</span></span>  
 <span data-ttu-id="1279f-133">Wątki również zawierać kilka właściwości przydatne, jak pokazano w poniższej tabeli:</span><span class="sxs-lookup"><span data-stu-id="1279f-133">Threads also contain several useful properties, as shown in the following table:</span></span>  
  
|<span data-ttu-id="1279f-134">Właściwość</span><span class="sxs-lookup"><span data-stu-id="1279f-134">Property</span></span>|<span data-ttu-id="1279f-135">Wartość</span><span class="sxs-lookup"><span data-stu-id="1279f-135">Value</span></span>|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|<span data-ttu-id="1279f-136">Zawiera wartość `True` czy wątku jest aktywna.</span><span class="sxs-lookup"><span data-stu-id="1279f-136">Contains the value `True` if a thread is active.</span></span>|  
|<xref:System.Threading.Thread.IsBackground%2A>|<span data-ttu-id="1279f-137">Pobiera lub ustawia wartość Boolean wskazującą, czy wątek ma lub powinny być wątku w tle.</span><span class="sxs-lookup"><span data-stu-id="1279f-137">Gets or sets a Boolean that indicates if a thread is or should be a background thread.</span></span> <span data-ttu-id="1279f-138">Wątki w tle są podobne do wątki pierwszoplanowe, ale wątku w tle nie zapobiega proces zatrzymywania.</span><span class="sxs-lookup"><span data-stu-id="1279f-138">Background threads are like foreground threads, but a background thread does not prevent a process from stopping.</span></span> <span data-ttu-id="1279f-139">Po zatrzymaniu wszystkie wątki pierwszego planu, które należą do procesów, środowisko uruchomieniowe języka wspólnego kończy proces po wywołaniu <xref:System.Threading.Thread.Abort%2A> metoda wątki w tle, które są nadal aktywne.</span><span class="sxs-lookup"><span data-stu-id="1279f-139">Once all foreground threads that belong to a process have stopped, the common language runtime ends the process by calling the <xref:System.Threading.Thread.Abort%2A> method on background threads that are still alive.</span></span>|  
|<xref:System.Threading.Thread.Name%2A>|<span data-ttu-id="1279f-140">Pobiera lub ustawia nazwę wątku.</span><span class="sxs-lookup"><span data-stu-id="1279f-140">Gets or sets the name of a thread.</span></span> <span data-ttu-id="1279f-141">Najczęściej używane do odnajdywania poszczególnych wątków podczas debugowania.</span><span class="sxs-lookup"><span data-stu-id="1279f-141">Most frequently used to discover individual threads when you debug.</span></span>|  
|<xref:System.Threading.Thread.Priority%2A>|<span data-ttu-id="1279f-142">Pobiera lub ustawia wartość, która jest używana przez system operacyjny priorytety planowania wątków.</span><span class="sxs-lookup"><span data-stu-id="1279f-142">Gets or sets a value that is used by the operating system to prioritize thread scheduling.</span></span>|  
|<xref:System.Threading.Thread.ThreadState%2A>|<span data-ttu-id="1279f-143">Zawiera wartość, która opisuje stanu lub stany wątku.</span><span class="sxs-lookup"><span data-stu-id="1279f-143">Contains a value that describes a thread's state or states.</span></span>|  
  
## <a name="thread-priorities"></a><span data-ttu-id="1279f-144">Priorytety wątku</span><span class="sxs-lookup"><span data-stu-id="1279f-144">Thread Priorities</span></span>  
 <span data-ttu-id="1279f-145">Każdy wątek ma właściwość priorytet, która określa, jak duże lub małe wycinka czasu procesora, które ma wykonać.</span><span class="sxs-lookup"><span data-stu-id="1279f-145">Every thread has a priority property that determines how big or small a slice of processor time it has to execute.</span></span> <span data-ttu-id="1279f-146">System operacyjny przydziela dłużej przedziały czasu, aby wątki o wysokim priorytecie i krótszy przedziały czasu, aby wątki o niskim priorytecie.</span><span class="sxs-lookup"><span data-stu-id="1279f-146">The operating system allocates longer time slices to high-priority threads and shorter time slices to low-priority threads.</span></span> <span data-ttu-id="1279f-147">Nowe wątki są tworzone z wartością `Normal`, można jednak zmienić <xref:System.Threading.Thread.Priority%2A> wszelkie wartości dla właściwości <xref:System.Threading.ThreadPriority> wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="1279f-147">New threads are created with the value of `Normal`, but you can change the <xref:System.Threading.Thread.Priority%2A> property to any value in the <xref:System.Threading.ThreadPriority> enumeration.</span></span>  
  
 <span data-ttu-id="1279f-148">Zobacz <xref:System.Threading.ThreadPriority> szczegółowy opis różnych priorytetów wątku.</span><span class="sxs-lookup"><span data-stu-id="1279f-148">See <xref:System.Threading.ThreadPriority> for a detailed description of the various thread priorities.</span></span>  
  
## <a name="foreground-and-background-threads"></a><span data-ttu-id="1279f-149">Wątki pierwszego planu i tła</span><span class="sxs-lookup"><span data-stu-id="1279f-149">Foreground and Background Threads</span></span>  
 <span data-ttu-id="1279f-150">A *wątku na pierwszym planie* działa przez czas nieokreślony, podczas gdy *wątku w tle* zatrzymuje się, jak ostatni wątek pierwszego planu została zatrzymana.</span><span class="sxs-lookup"><span data-stu-id="1279f-150">A *foreground thread* runs indefinitely, whereas a *background thread* stops as soon as the last foreground thread has stopped.</span></span> <span data-ttu-id="1279f-151">Można użyć <xref:System.Threading.Thread.IsBackground%2A> właściwości do określania, lub zmienić stan wątku w tle.</span><span class="sxs-lookup"><span data-stu-id="1279f-151">You can use the <xref:System.Threading.Thread.IsBackground%2A> property to determine or change the background status of a thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1279f-152">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1279f-152">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="1279f-153">Synchronizacja wątku (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1279f-153">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="1279f-154">Parametry i wartości zwracane dla procedur wielowątkowości (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1279f-154">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)  
 [<span data-ttu-id="1279f-155">Wątkowość (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1279f-155">Threading (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/index.md)