---
title: "Wprowadzenie do zdarzeń"
description: "Więcej informacji na temat zdarzeń w .NET Core i cele firmy Microsoft projektu języka zdarzeń w tym omówieniu."
keywords: .NET, .NET core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 9b8d2a00-1584-4a5b-8994-5003d54d8e0c
ms.openlocfilehash: f81c2d9fc2ec69c295485fe06029b5de65335db0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-events"></a><span data-ttu-id="c0c82-104">Wprowadzenie do zdarzeń</span><span class="sxs-lookup"><span data-stu-id="c0c82-104">Introduction to Events</span></span>

[<span data-ttu-id="c0c82-105">Poprzednie</span><span class="sxs-lookup"><span data-stu-id="c0c82-105">Previous</span></span>](delegates-patterns.md)

<span data-ttu-id="c0c82-106">Zdarzenia są takie jak delegatów, *późne wiązanie* mechanizmu.</span><span class="sxs-lookup"><span data-stu-id="c0c82-106">Events are, like delegates, a *late binding* mechanism.</span></span> <span data-ttu-id="c0c82-107">W rzeczywistości zdarzenia są tworzone na obsługę języka delegatów.</span><span class="sxs-lookup"><span data-stu-id="c0c82-107">In fact, events are built on the language support for delegates.</span></span>

<span data-ttu-id="c0c82-108">Zdarzenia są sposób dla obiekt emisji (wszystkich zainteresowanych składników w systemie) szukają miało miejsce.</span><span class="sxs-lookup"><span data-stu-id="c0c82-108">Events are a way for an object to broadcast (to all interested components in the system) that something has happened.</span></span> <span data-ttu-id="c0c82-109">Drugim składnikiem mogą subskrybować zdarzenia i powiadomienia, gdy zdarzenie jest wywoływane.</span><span class="sxs-lookup"><span data-stu-id="c0c82-109">Any other component can subscribe to the event, and be notified when an event is raised.</span></span>

<span data-ttu-id="c0c82-110">W niektórych z programowania prawdopodobnie używano zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c0c82-110">You've probably used events in some of your programming.</span></span> <span data-ttu-id="c0c82-111">Wiele systemów graficznego ma modelu zdarzeń do interakcji z użytkownikiem raportu.</span><span class="sxs-lookup"><span data-stu-id="c0c82-111">Many graphical systems have an event model to report user interaction.</span></span> <span data-ttu-id="c0c82-112">Te zdarzenia rozpoczną przesyłanie raportów o ruchów myszy, naciśnięcie przycisku i podobne interakcji.</span><span class="sxs-lookup"><span data-stu-id="c0c82-112">These events would report mouse movement, button presses and similar interactions.</span></span> <span data-ttu-id="c0c82-113">Który jest jednym z najbardziej typowych, ale na pewno nie jedyny scenariusz, w którym zdarzenia są używane.</span><span class="sxs-lookup"><span data-stu-id="c0c82-113">That's one of the most common, but certainly not the only scenario where events are used.</span></span>

<span data-ttu-id="c0c82-114">Możesz definiować zdarzenia, które powinny być wywoływane dla klas.</span><span class="sxs-lookup"><span data-stu-id="c0c82-114">You can define events that should be raised for your classes.</span></span> <span data-ttu-id="c0c82-115">Ważnym zagadnieniem podczas pracy ze zdarzeniami jest to, że może być dowolny obiekt zarejestrowane dla określonego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c0c82-115">One important consideration when working with events is that there may not be any object registered for a particular event.</span></span> <span data-ttu-id="c0c82-116">Należy napisać kod, aby nie zgłaszał zdarzenia, gdy nie odbiorników są skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="c0c82-116">You must write your code so that it does not raise events when no listeners are configured.</span></span>

<span data-ttu-id="c0c82-117">Subskrybowanie zdarzeń tworzy sprzężenia między dwoma obiektami (źródło zdarzeń i obiekt sink zdarzenia).</span><span class="sxs-lookup"><span data-stu-id="c0c82-117">Subscribing to an event also creates a coupling between two objects (the event source, and the event sink).</span></span> <span data-ttu-id="c0c82-118">Należy się upewnić, że obiekt sink zdarzenia, cofnięć subskrypcji z źródło zdarzeń, gdy nie jest już zainteresowani zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c0c82-118">You need to ensure that the event sink unsubscribes from the event source when no longer interested in events.</span></span>

## <a name="design-goals-for-event-support"></a><span data-ttu-id="c0c82-119">Cele projektowania obsługi zdarzeń</span><span class="sxs-lookup"><span data-stu-id="c0c82-119">Design Goals for Event Support</span></span>

<span data-ttu-id="c0c82-120">Język projektu dla zdarzeń jest przeznaczony dla tych celów.</span><span class="sxs-lookup"><span data-stu-id="c0c82-120">The language design for events targets these goals.</span></span>

<span data-ttu-id="c0c82-121">Najpierw włączyć minimalne sprzężenia między źródłem zdarzenia i obiekt sink zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c0c82-121">First, enable very minimal coupling between an event source and an event sink.</span></span> <span data-ttu-id="c0c82-122">Te dwa składniki nie może zapisywać w tej samej organizacji, a nawet może zostać zaktualizowany w całkowicie różnych harmonogramów.</span><span class="sxs-lookup"><span data-stu-id="c0c82-122">These two components may not be written by the same organization, and may even be updated on totally different schedules.</span></span>

<span data-ttu-id="c0c82-123">Po drugie powinny być bardzo proste, aby subskrybować zdarzenia i można zrezygnować z tego samego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c0c82-123">Secondly, it should be very simple to subscribe to an event, and to unsubscribe from that same event.</span></span>

<span data-ttu-id="c0c82-124">A na koniec źródła zdarzeń powinny obsługiwać wielu subskrybentów zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="c0c82-124">And finally, event sources should support multiple event subscribers.</span></span> <span data-ttu-id="c0c82-125">Należy również obsługiwać, o subskrybentów zdarzeń dołączony.</span><span class="sxs-lookup"><span data-stu-id="c0c82-125">It should also support having no event subscribers attached.</span></span>

<span data-ttu-id="c0c82-126">Widać, że cele dotyczące zdarzenia są bardzo podobne do celów dla obiektów delegowanych.</span><span class="sxs-lookup"><span data-stu-id="c0c82-126">You can see that the goals for events are very similar to the goals for delegates.</span></span>
<span data-ttu-id="c0c82-127">Dlatego obsługa języków zdarzeń jest oparty na obsługę języka delegata.</span><span class="sxs-lookup"><span data-stu-id="c0c82-127">That's why the event language support is built on the delegate language support.</span></span>

## <a name="language-support-for-events"></a><span data-ttu-id="c0c82-128">Obsługa języka dla zdarzenia</span><span class="sxs-lookup"><span data-stu-id="c0c82-128">Language Support for Events</span></span>

<span data-ttu-id="c0c82-129">Składnia definiowanie zdarzeń, subskrypcja i anulowanie subskrypcji zdarzeń jest rozszerzeniem składni delegatów.</span><span class="sxs-lookup"><span data-stu-id="c0c82-129">The syntax for defining events, and subscribing or unsubscribing from events is an extension of the syntax for delegates.</span></span>

<span data-ttu-id="c0c82-130">Aby zdefiniować zdarzenia używane `event` — słowo kluczowe:</span><span class="sxs-lookup"><span data-stu-id="c0c82-130">To define an event you use the `event` keyword:</span></span>

```csharp
public event EventHandler<FileListArgs> Progress;
```

<span data-ttu-id="c0c82-131">Typ zdarzenia (`EventHandler<FileListArgs>` w tym przykładzie) musi być typem obiektu delegowanego.</span><span class="sxs-lookup"><span data-stu-id="c0c82-131">The type of the event (`EventHandler<FileListArgs>` in this example) must be a delegate type.</span></span> <span data-ttu-id="c0c82-132">Istnieje wiele Konwencji, które należy wykonać przy deklarowaniu zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c0c82-132">There are a number of conventions that you should follow when declaring an event.</span></span> <span data-ttu-id="c0c82-133">Zazwyczaj typ delegata zdarzenia ma typ zwracany typ void.</span><span class="sxs-lookup"><span data-stu-id="c0c82-133">Typically, the event delegate type has a void return.</span></span>
<span data-ttu-id="c0c82-134">Deklaracje zdarzeń powinny być zlecenie lub frazę zlecenia.</span><span class="sxs-lookup"><span data-stu-id="c0c82-134">Event declarations should be a verb, or a verb phrase.</span></span>
<span data-ttu-id="c0c82-135">Użyj przeszłego (w tym przykładzie), gdy zdarzenie zgłasza rzecz, która została wykonana.</span><span class="sxs-lookup"><span data-stu-id="c0c82-135">Use past tense (as in this example) when the event reports something that has happened.</span></span> <span data-ttu-id="c0c82-136">Użyj polecenia teraźniejszym (na przykład `Closing`) do zgłaszania coś, co się stanie.</span><span class="sxs-lookup"><span data-stu-id="c0c82-136">Use a present tense verb (for example, `Closing`) to report something that is about to happen.</span></span> <span data-ttu-id="c0c82-137">Często przy użyciu teraźniejszym wskazuje, że klasa obsługuje określonego rodzaju zachowanie dostosowania.</span><span class="sxs-lookup"><span data-stu-id="c0c82-137">Often, using present tense indicates that your class supports some kind of customization behavior.</span></span> <span data-ttu-id="c0c82-138">Jednym z najbardziej typowych scenariuszy jest obsługuje anulowania.</span><span class="sxs-lookup"><span data-stu-id="c0c82-138">One of the most common scenarios is to support cancellation.</span></span> <span data-ttu-id="c0c82-139">Na przykład `Closing` zdarzeń może zawierać argumentu, który wskazuje, czy operacja zamykania powinno być kontynuowane, czy nie.</span><span class="sxs-lookup"><span data-stu-id="c0c82-139">For example, a `Closing` event may include an argument that would indicate if the close operation should continue, or not.</span></span>  <span data-ttu-id="c0c82-140">Inne scenariusze mogą umożliwić wywołującym zmodyfikować zachowanie, aktualizując właściwości argumentów zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c0c82-140">Other scenarios may enable callers to modify behavior by updating properties of the event arguments.</span></span> <span data-ttu-id="c0c82-141">Mogą zgłaszać zdarzenia w celu poinformowania proponowanych następnej akcji zajmie algorytmu.</span><span class="sxs-lookup"><span data-stu-id="c0c82-141">You may raise an event to indicate a proposed next action an algorithm will take.</span></span> <span data-ttu-id="c0c82-142">Program obsługi zdarzeń może wprowadzić różne akcje przez modyfikowanie właściwości argumentu zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c0c82-142">The event handler may mandate a different action by modifying  properties of the event argument.</span></span>

<span data-ttu-id="c0c82-143">Jeśli chcesz zgłosić zdarzenie, należy wywołać przy użyciu składni wywołania obiektu delegowanego obsługi zdarzeń:</span><span class="sxs-lookup"><span data-stu-id="c0c82-143">When you want to raise the event, you call the event handlers using the delegate invocation syntax:</span></span>

```csharp
Progress?.Invoke(this, new FileListArgs(file));
```

<span data-ttu-id="c0c82-144">Zgodnie z opisem w sekcji na [delegatów](delegates-patterns.md),?.</span><span class="sxs-lookup"><span data-stu-id="c0c82-144">As discussed in the section on [delegates](delegates-patterns.md), the ?.</span></span>
<span data-ttu-id="c0c82-145">Operator ułatwia zapewnienie, że należy próbować zgłosić zdarzenie, gdy nie ma żadnych subskrybentów tego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c0c82-145">operator makes it easy to ensure that you do not attempt to raise the event when there are no subscribers to that event.</span></span>
 
<span data-ttu-id="c0c82-146">Subskrybowanie zdarzeń za pomocą `+=` operator:</span><span class="sxs-lookup"><span data-stu-id="c0c82-146">You subscribe to an event by using the `+=` operator:</span></span>

```csharp
EventHandler<FileListArgs> onProgress = (sender, eventArgs) => 
    Console.WriteLine(eventArgs.FoundFile);
lister.Progress += OnProgress;
```

<span data-ttu-id="c0c82-147">Metoda obsługi zwykle jest prefiksem "Na" następuje nazwa zdarzenia opisane powyżej.</span><span class="sxs-lookup"><span data-stu-id="c0c82-147">The handler method typically is the prefix 'On' followed by the event name, as shown above.</span></span>

<span data-ttu-id="c0c82-148">Anulowanie subskrypcji przy użyciu `-=` operator:</span><span class="sxs-lookup"><span data-stu-id="c0c82-148">You unsubscribe using the `-=` operator:</span></span>

```csharp
lister.Progress -= onProgress;
```

<span data-ttu-id="c0c82-149">Należy pamiętać, że zadeklarowany jako zmienna lokalna dla wyrażenia, który reprezentuje program obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="c0c82-149">It's important to note that I declared a local variable for the expression that represents the event handler.</span></span> <span data-ttu-id="c0c82-150">Dzięki temu usuwa anulowania subskrypcji programu obsługi.</span><span class="sxs-lookup"><span data-stu-id="c0c82-150">That ensures the unsubscribe removes the handler.</span></span>
<span data-ttu-id="c0c82-151">Jeśli zamiast tego użyto treści wyrażenia lambda, próbujesz usunąć program obsługi, który nigdy nie został dołączony, które nie działają.</span><span class="sxs-lookup"><span data-stu-id="c0c82-151">If, instead, you used the body of the lambda expression, you are attempting to remove a handler that has never been attached, which does nothing.</span></span>

<span data-ttu-id="c0c82-152">W kolejnym artykule dowiesz się więcej na temat wzorców typowych zdarzeń i różnych zmian w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c0c82-152">In the next article, you'll learn more about typical event patterns, and different variations on this example.</span></span>

[<span data-ttu-id="c0c82-153">Dalej</span><span class="sxs-lookup"><span data-stu-id="c0c82-153">Next</span></span>](event-pattern.md)