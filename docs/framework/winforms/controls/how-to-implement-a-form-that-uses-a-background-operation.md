---
title: "Porady: implementowanie formularza korzystającego z operacji w tle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a519f1611e419ec439a70ec86f457049582c4ceb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="0d553-102">Porady: implementowanie formularza korzystającego z operacji w tle</span><span class="sxs-lookup"><span data-stu-id="0d553-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="0d553-103">Następujący przykład program tworzy formularz, który oblicza Fibonacci cyfry.</span><span class="sxs-lookup"><span data-stu-id="0d553-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="0d553-104">Obliczenie jest uruchamiane w wątku, który jest oddzielony od wątku interfejsu użytkownika, więc interfejsu użytkownika w dalszym ciągu działać bez opóźnień w trakcie wykonywania obliczeń.</span><span class="sxs-lookup"><span data-stu-id="0d553-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="0d553-105">Brak kompleksową obsługę tego zadania w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0d553-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="0d553-106">Zobacz też [wskazówki: Wdrażanie formularza korzystającego z operacji w tle](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="0d553-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d553-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="0d553-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0d553-108">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="0d553-108">Compiling the Code</span></span>  
 <span data-ttu-id="0d553-109">Ten przykład wymaga:</span><span class="sxs-lookup"><span data-stu-id="0d553-109">This example requires:</span></span>  
  
-   <span data-ttu-id="0d553-110">Odwołania do zestawów systemu, System.Drawing i System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="0d553-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="0d553-111">Informacji dotyczących tworzenia tego przykładu z wiersza polecenia dla [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] lub [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], zobacz [tworzenie z wiersza polecenia](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) lub [kompilowania z wiersza polecenia csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0d553-111">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0d553-112">Można także utworzyć tym przykładzie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] przez wklejenie kodu do nowego projektu.</span><span class="sxs-lookup"><span data-stu-id="0d553-112">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="0d553-113">Zobacz też [porady: kompilowanie i uruchamianie pełną Windows formularze kodu przykład za pomocą programu Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="0d553-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0d553-114">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="0d553-114">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="0d553-115">Korzystając z wielowątkowość jakiegokolwiek, możesz narażając samodzielnie do usterki bardzo poważne i złożone.</span><span class="sxs-lookup"><span data-stu-id="0d553-115">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="0d553-116">Zapoznaj się [zarządzanych wątków najlepsze rozwiązania w zakresie](../../../../docs/standard/threading/managed-threading-best-practices.md) przed zaimplementowaniem rozwiązania, w którym używane wielowątkowości.</span><span class="sxs-lookup"><span data-stu-id="0d553-116">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d553-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0d553-117">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="0d553-118">Omówienie wzorca asynchronicznego opartego na zdarzeniach</span><span class="sxs-lookup"><span data-stu-id="0d553-118">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="0d553-119">Zarządzana wątkowość — najlepsze praktyki</span><span class="sxs-lookup"><span data-stu-id="0d553-119">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)