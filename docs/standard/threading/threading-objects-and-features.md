---
title: "Wątkowość obiektów i funkcji"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a73e5c60a661c171e9e46e6307484cf5e0e6b80
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="threading-objects-and-features"></a>Wątkowość obiektów i funkcji
.NET Framework udostępnia wiele obiektów, które ułatwiają tworzenie i zarządzanie nimi w aplikacjach wielowątkowych. Zarządzane wątki są reprezentowane przez <xref:System.Threading.Thread> klasy. <xref:System.Threading.ThreadPool> Klasa umożliwia łatwe tworzenie i zarządzanie zadaniami w tle wielowątkowych. <xref:System.ComponentModel.BackgroundWorker> Klasy jest taka sama dla zadania, które współdziałają z interfejsu użytkownika. <xref:System.Threading.Timer> Klasa wykonuje zadania w tle w określonych interwałach.  
  
 Ponadto istnieje wiele klas, które synchronizują działania wątków, w tym <xref:System.Threading.Semaphore> i <xref:System.Threading.EventWaitHandle> klas wprowadzonych w programie .NET Framework w wersji 2.0. Funkcje te klasy są porównywane w [podstawowych Omówienie synchronizacji](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Zarządzana Pula wątków](../../../docs/standard/threading/the-managed-thread-pool.md)  
 Wyjaśniono **puli wątków** klasy, która pozwala na żądanie wątku do wykonania zadania bez konieczności zarządzania dowolnego wątku samodzielnie.  
  
 [Czasomierze](../../../docs/standard/threading/timers.md)  
 Wyjaśniono, jak używać **czasomierza** do określenia delegata do wywołania w określonym czasie.  
  
 [Monitory](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 Wyjaśniono, jak używać **Monitor** klasy synchronizujący dostęp do elementu członkowskiego lub do tworzenia własnych wątku typu zarządzania.  
  
 [Uchwyty oczekiwania](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 W tym artykule opisano <xref:System.Threading.WaitHandle> klasy, abstrakcyjna klasa podstawowa dla zdarzenia oczekiwania dojść, muteksy i semaforów, dzięki czemu oczekiwanie na wiele zdarzeń synchronizacji.  
  
 [EventWaitHandle, autoresetevent —, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 W tym artykule opisano zarządzanych uchwyty oczekiwania na zdarzenie, które są używane do synchronizowania działania wątku sygnalizacji i Oczekiwanie na sygnały.  
  
 [Muteksy](../../../docs/standard/threading/mutexes.md)  
 Wyjaśniono, jak używać <xref:System.Threading.Mutex> synchronizujący dostęp do obiektu lub utworzyć własne mechanizmy synchronizacji.  
  
 [Operacje blokowane](../../../docs/standard/threading/interlocked-operations.md)  
 Wyjaśniono, jak używać <xref:System.Threading.Interlocked> klasę, aby zwiększyć lub zmniejszyć wartość i przechowywania wartości w jednej operacji atomic.  
  
 [Reader_writer_lock](../../../docs/standard/threading/reader-writer-locks.md)  
 Definiuje blokady, która implementuje semantykę pojedynczego — moduł zapisujący/wielu czytników.  
  
 [Semafor i klasa SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 W tym artykule opisano <xref:System.Threading.Semaphore> obiekty i objaśnienie sposobu ich użyć do kontroli dostępu do zasobów ograniczone.  
  
 [Przegląd elementów podstawowych synchronizacji](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Porównanie funkcji blokowania i synchronizacja wątków zarządzanych klas .NET Framework.  
  
 [Bariery](../../../docs/standard/threading/barrier.md)  
 W tym artykule opisano <xref:System.Threading.Barrier> obiekty, które implementują wzorzec bariery koordynacji wątków w operacjach etapowe.  
  
 [Struktury SpinLock](../../../docs/standard/threading/spinlock.md)  
 W tym artykule opisano <xref:System.Threading.SpinLock>, lekkie sposobem klasa monitora w niektórych scenariuszach niskiego poziomu.  
  
 [Metody SpinWait](../../../docs/standard/threading/spinwait.md)  
 W tym artykule opisano <xref:System.Threading.SpinWait>, pierwotnych niskiego poziomu synchronizacji, który wykonuje zajęty Obracająca przed zainicjowaniem oczekiwania na podstawie jądra.  
  
## <a name="reference"></a>Tematy pomocy  
 <xref:System.Threading.Thread>  
 Zawiera dokumentacja referencyjna dla **wątku** klasy, która reprezentuje zarządzanego wątku, czy pochodzi kodu niezarządzanego, lub został utworzony w zarządzanej aplikacji.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Umożliwia zadania w tle, które współdziałają z interfejsem użytkownika, komunikację za pomocą zdarzenia wywoływane w wątku interfejsu użytkownika.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Asynchroniczne We/Wy pliku](../../../docs/standard/io/asynchronous-file-i-o.md)  
 W tym artykule opisano, jak asynchroniczne We/Wy portów za pomocą puli wątków wymagają przetwarzania tylko po zakończeniu operacji wejścia/wyjścia.  
  
 [Biblioteka zadań równoległych (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 W tym artykule opisano zalecane podejście do programowania wielowątkowe w [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] i nowszych.