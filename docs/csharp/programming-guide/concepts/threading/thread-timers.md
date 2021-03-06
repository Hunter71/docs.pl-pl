---
title: Czasomierze wątków (C#)
ms.date: 07/20/2015
ms.assetid: 52ed71e8-4fd9-43a4-ae40-04cce7cff23f
ms.openlocfilehash: c2be9fef0b3f6f3db7ae8c9a519ece0cb64b6f49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="thread-timers-c"></a>Czasomierze wątków (C#)
<xref:System.Threading.Timer?displayProperty=nameWithType> Klasy jest przydatne w przypadku okresowo uruchamianie zadania w oddzielnym wątku. Można na przykład użyć czasomierza wątku, sprawdź stan i integralności bazy danych lub utworzyć kopię zapasową plików krytycznych.  
  
## <a name="thread-timer-example"></a>Przykład czasomierza wątku  
 W poniższym przykładzie uruchamia zadanie, co dwie sekundy i używa flagę zainicjować <xref:System.IDisposable.Dispose%2A> metodę, która zatrzymuje czasomierza. W tym przykładzie wpisów stanu w oknie danych wyjściowych.  
  
```csharp  
private class StateObjClass  
{  
    // Used to hold parameters for calls to TimerTask.  
    public int SomeValue;  
    public System.Threading.Timer TimerReference;  
    public bool TimerCanceled;  
}  
  
public void RunTimer()  
{  
    StateObjClass StateObj = new StateObjClass();  
    StateObj.TimerCanceled = false;  
    StateObj.SomeValue = 1;  
    System.Threading.TimerCallback TimerDelegate =  
        new System.Threading.TimerCallback(TimerTask);  
  
    // Create a timer that calls a procedure every 2 seconds.  
    // Note: There is no Start method; the timer starts running as soon as   
    // the instance is created.  
    System.Threading.Timer TimerItem =  
        new System.Threading.Timer(TimerDelegate, StateObj, 2000, 2000);  
  
    // Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem;    
  
    // Run for ten loops.  
    while (StateObj.SomeValue < 10)   
    {  
        // Wait one second.  
        System.Threading.Thread.Sleep(1000);    
    }  
  
    // Request Dispose of the timer object.  
    StateObj.TimerCanceled = true;    
}  
  
private void TimerTask(object StateObj)  
{  
    StateObjClass State = (StateObjClass)StateObj;  
    // Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(ref State.SomeValue);  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " + DateTime.Now.ToString());  
    if (State.TimerCanceled)      
    // Dispose Requested.  
    {  
        State.TimerReference.Dispose();  
        System.Diagnostics.Debug.WriteLine("Done  " + DateTime.Now.ToString());  
    }  
}  
```  
  
 Czasomierze wątków są szczególnie przydatne, gdy <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> obiekt jest niedostępny, takie jak podczas tworzenia aplikacji konsoli.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Threading>  
 [Aplikacje wielowątkowe (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)
