---
title: Aplikacja konsoli
description: Ten samouczek zawiera szereg funkcji .NET Core i języka C#.
ms.date: 03/06/2017
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: bae03c9ae02f2888b1b70617ca712ef7927e9dce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="console-application"></a>Aplikacja konsoli

Ten samouczek zawiera szereg funkcji .NET Core i języka C#. Dowiesz się:

- Podstawowe informacje o .NET Core interfejsu wiersza polecenia (CLI)
- Struktura aplikacji Konsolowej C#
- Konsola operacje We/Wy
- Podstawy interfejsów API we/wy pliku w .NET
- Podstawy opartego na zadaniach asynchronicznej Programowanie w .NET

Będzie utworzyć aplikację, która odczytuje plik tekstowy i zwraca zawartość tego pliku tekstowego do konsoli. Dane wyjściowe do konsoli jest użytkownika, aby dopasować go czytać na głos. Można przyspieszyć lub spowolnić tempo przez naciśnięcie przycisku "<" lub ">" kluczy.

Istnieje wiele funkcji, w tym samouczku. Utworzymy je jeden po drugim.

## <a name="prerequisites"></a>Wymagania wstępne

Należy skonfigurować komputer, aby uruchomić oprogramowanie .NET Core. Instrukcje instalacji można znaleźć na [.NET Core](https://www.microsoft.com/net/core) strony. Można uruchomić tej aplikacji, w systemie Windows, Linux, macOS lub w kontenerze Docker.
Należy zainstalować w edytorze kodu dotyczącego elementów ulubionych.

## <a name="create-the-application"></a>Tworzenie aplikacji

Pierwszym krokiem jest utworzenie nowej aplikacji. Otwórz wiersz polecenia i Utwórz nowy katalog aplikacji. Upewnij się, że sposób bieżącego katalogu. Wpisz polecenie `dotnet new console` w wierszu polecenia. Spowoduje to utworzenie plików starter podstawowe aplikacji "Hello World".

Przed wprowadzeniem modyfikacji przejdźmy do czynności, aby uruchomić prostej aplikacji Hello World. Po utworzeniu aplikacji, wpisz `dotnet restore` w wierszu polecenia. To polecenie uruchamia proces przywracania pakietów NuGet. NuGet jest Menedżera pakietów platformy .NET. To polecenie pobiera wszelkie brakujące zależności projektu. Jak jest to nowy projekt, Brak zależności są na miejscu, więc przy pierwszym uruchomieniu pobierze framework .NET Core. Po wykonaniu tego kroku początkowego, wystarczy uruchomić `dotnet restore` podczas dodawania nowych pakietów zależnych lub zaktualizować wersje zależności.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Po przywróceniu pakietów, możesz uruchomić `dotnet build`. Wykonuje aparat kompilacji i tworzy aplikację pliku wykonywalnego. Na koniec wykonaj `dotnet run` do uruchamiania aplikacji.

Jest prosty kod aplikacji Hello World w pliku Program.cs. Otwórz ten plik z w ulubionym edytorze tekstów. Jesteśmy wprowadzi naszym pierwszym zmiany.
W górnej części pliku, zobacz using instrukcji:

```csharp
using System;
```

Ta instrukcja informuje kompilator, że dowolne typy z `System` znajdują się w zakresie przestrzeni nazw. Jak który użyto innych języków obiektowo C# używa przestrzeni nazw do organizowania typów. Nie różni się ten program Hello World. Widać, że program jest ujęta w przestrzeni nazw o nazwie na podstawie nazwy bieżącego katalogu. W tym samouczku Zmieńmy nazwę przestrzeni nazw do `TeleprompterConsole`:

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a>Odczytywanie i wyświetlania pliku

Pierwszy funkcję tak, aby dodać jest możliwość odczytywanie pliku tekstowego i Wyświetl ten tekst do konsoli. Po pierwsze możemy dodać plik tekstowy. Kopiuj [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) plik z repozytorium GitHub dla tego [próbki](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) w katalogu projektu. To będzie służyć jako skryptów dla aplikacji. Jeśli chcesz uzyskać informacje na temat Pobierz przykładową aplikację na ten temat, zapoznaj się z instrukcjami w [przykłady i samouczki](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) tematu.

Następnie dodaj następującą metodę w Twojej `Program` klasy (bezpośrednio pod `Main` metody):

```csharp
static IEnumerable<string> ReadFrom(string file)
{
    string line;
    using (var reader = File.OpenText(file))
    {
        while ((line = reader.ReadLine()) != null)
        {
            yield return line;
        }
    }
}
```

Ta metoda używa typów z dwóch nowych przestrzeni nazw. W tym celu należy skompilować należy dodać następujące dwa wiersze na początku pliku:

```csharp
using System.Collections.Generic;
using System.IO;
```

<xref:System.Collections.Generic.IEnumerable%601> Interfejsu jest zdefiniowany w <xref:System.Collections.Generic> przestrzeni nazw. <xref:System.IO.File> Klasa jest zdefiniowana w <xref:System.IO> przestrzeni nazw.

Ta metoda jest specjalnym rodzajem metody C# o nazwie *metody Iterator*. Moduł wyliczający metody zwracają sekwencji, które są oceniane w trybie opóźnienia. Oznacza to, że każdej pozycji w sekwencji jest generowany, zgodnie z wymaganiami kodu wykorzystywanie sekwencji. Moduł wyliczający metody to metody, które zawierają jedną lub więcej [ `yield return` ](../language-reference/keywords/yield.md) instrukcje. Obiekt zwrócony przez `ReadFrom` metoda zawiera kod, aby wygenerować każdej pozycji w sekwencji. W tym przykładzie, który obejmuje odczytu następnego wiersza tekstu z pliku źródłowego i zwraca ten ciąg. Za każdym żądaniem kod wywołujący następnego elementu z sekwencji kod odczytuje następnego wiersza tekstu z pliku i zwraca go. Jeśli plik jest całkowicie do odczytu, sekwencja wskazuje, że nie ma więcej elementów.

Istnieją dwa inne C# składni elementy, które mogą być nowe dla Ciebie. [ `using` ](../language-reference/keywords/using-statement.md) Instrukcji w tej metodzie zarządza oczyszczania zasobu. Zmienna, która została zainicjowana w `using` instrukcji (`reader`, w tym przykładzie) musi implementować <xref:System.IDisposable> interfejsu. Ten interfejs definiuje jedną metodę `Dispose`, która powinna być wywoływana, gdy zasobu powinny zostać zwolnione. Kompilator generuje tego wywołania, gdy wykonanie osiągnie zamykającym `using` instrukcji. Kod wygenerowany przez kompilator zapewnia zwolnienie zasobu, nawet w przypadku zgłoszenia wyjątku z kodu w bloku zdefiniowany przy użyciu instrukcji.

`reader` Zmiennej jest definiowana za pomocą `var` — słowo kluczowe. [`var`](../language-reference/keywords/var.md) definiuje *niejawnie wpisane zmiennej lokalnej*. Oznacza to, że typ zmiennej jest określana przez typ kompilacji obiektu przypisaną do zmiennej. Tutaj, która jest wartością zwracaną przez <xref:System.IO.File.OpenText(System.String)> metodę, która jest <xref:System.IO.StreamReader> obiektu.

Teraz załóżmy wprowadź kod, aby odczytać plik w `Main` metody:

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line);
}
```

Uruchom program (przy użyciu `dotnet run`), aby zobaczyć każdy wiersz wydrukowane do konsoli.

## <a name="adding-delays-and-formatting-output"></a>Dodawanie opóźnień i formatowanie danych wyjściowych

Możesz mieć jest wyświetlany zbyt szybko, aby odczytywać. Teraz musisz dodać opóźnienia w danych wyjściowych. Po rozpoczęciu, użytkownik będzie zbudować części kodu core, który umożliwia przetwarzanie asynchroniczne. Jednak te pierwsze kroki są zgodne z kilku wzorców układ. Układ wzorce są wskazać w komentarzach Dodaj kod, a kod zostanie zaktualizowany w kolejnych krokach.

Istnieją dwa kroki, aby w tej sekcji. Najpierw będzie aktualizowana metodę iteratora Aby przywrócić pojedyncze słowa zamiast całego wierszy. Który wykonuje się za pomocą tych zmian. Zastąp `yield return line;` instrukcji z następującym kodem:

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

Następnie należy zmodyfikować sposób korzystać wiersze pliku i Dodaj opóźnienia po zapisaniu każdego wyrazu. Zastąp `Console.WriteLine(line)` instrukcji w `Main` metodę z następującym fragmencie:

```csharp
Console.Write(line);
if (!string.IsNullOrWhiteSpace(line))
{
    var pause = Task.Delay(200);
    // Synchronously waiting on a task is an
    // anti-pattern. This will get fixed in later
    // steps.
    pause.Wait();
}
```

<xref:System.Threading.Tasks.Task> Klasa znajduje się w <xref:System.Threading.Tasks> przestrzeni nazw, dlatego należy dodać go `using` instrukcji w górnej części pliku:

```csharp
using System.Threading.Tasks;
```

Uruchamianie przykładowej i sprawdź dane wyjściowe. Teraz każdego pojedynczego wyrazu drukowania, a następnie z opóźnieniem 200 ms. Jednak wyświetlanych wyników zawiera niektóre problemy, ponieważ plik źródłowy, tekst ma kilka wierszy, które mają więcej niż 80 znaków bez podziału wiersza. Może to być trudny do odczytania, gdy jest on przewijanie przez. To łatwe rozwiązać problem. Będzie tylko informacje o długości każdego wiersza i generować nowy wiersz w każdym przypadku, gdy długość wiersza osiągnie określony próg. Deklarowanie zmiennej lokalnej po deklaracji `words` w `ReadFrom` metody, która przechowuje długość wiersza:

```csharp
var lineLength = 0;
```

Następnie dodaj następujący kod po `yield return word + " ";` instrukcji (przed nawiasem zamykającym):

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```

Uruchom próbkę i będzie mogła odczytywać na jego wstępnie skonfigurowane tempie.

## <a name="async-tasks"></a>Zadań asynchronicznych

W tym ostatnim kroku dodasz kod, aby zapisać dane wyjściowe asynchronicznie w jedno zadanie podczas również uruchamiania innego zadania, które można odczytać wejściowych od użytkownika, jeśli chcą, aby przyspieszyć lub spowolnić wyświetlania tekstu. Ma kilka kroków oraz do końca, będziesz mieć wszystkie aktualizacje, które są potrzebne.
Pierwszym krokiem jest utworzenie asynchronicznego <xref:System.Threading.Tasks.Task> zwracanie metodę, która reprezentuje kod po utworzeniu wykonanej do tej pory do odczytywania i wyświetlić plik.

Dodaj tę metodę, aby Twoje `Program` klasy (jest ona pobierana z treści Twojej `Main` — metoda):

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(200);
        }
    }
}
```

Można zauważyć dwie zmiany. Pierwszy w treści metody, zamiast wywoływać metodę <xref:System.Threading.Tasks.Task.Wait> synchronicznie oczekiwania na zakończenie zadania, korzysta z tej wersji `await` — słowo kluczowe. Aby to zrobić, należy dodać `async` modyfikator w podpisie metody. Ta metoda zwraca `Task`. Zwróć uwagę, że nie ma żadnych instrukcji return, które zwracają `Task` obiektu. Zamiast tego, który `Task` obiekt jest tworzony przez kompilator generuje, korzystając z kodu `await` operatora. Wyobraź sobie ta metoda zwraca po osiągnięciu `await`. Zwrócona `Task` wskazuje, że nie zakończył pracy.
Metoda wznawia działanie po ukończeniu zadania oczekiwano. Gdy jest wykonywana do ukończenia zwróconego `Task` wskazuje, że została zakończona.
Wywoływanie kodu można monitorować zwróconą `Task` ustalenie, kiedy została ukończona.

Ta nowa metoda można wywołać w Twojej `Main` metody:

```csharp
ShowTeleprompter().Wait();
```

W tym miejscu, w `Main`, kod synchronicznie oczekiwania. Należy używać `await` operator zamiast oczekiwać synchronicznie, jeśli to możliwe. Jednak w aplikacji konsoli `Main` metody, nie można użyć `await` operatora. Które mogłyby spowodować aplikacji został zakończony zanim wszystkie zadania zostały ukończone.

> [!NOTE]
> Jeśli używasz 7.1 C# lub później, należy utworzyć aplikacje konsoli z [ `async` `Main` metody](../whats-new/csharp-7-1.md#async-main).

Następnie należy napisać drugi metody asynchronicznej do odczytu z konsoli i obserwować "<" i ">" kluczy. Oto metoda dodane do tego zadania:

```csharp
private static async Task GetInput()
{
    var delay = 200;
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
            {
                delay -= 10;
            }
            else if (key.KeyChar == '<')
            {
                delay += 10;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

Spowoduje to utworzenie wyrażenia lambda do reprezentowania <xref:System.Action> delegata, który będzie odczytywać klucza z konsoli i modyfikuje zmienną lokalną reprezentujący opóźnienie, gdy użytkownik naciśnie ' <' lub ' >' kluczy. Ta metoda używa <xref:System.Console.ReadKey> zablokować i poczekaj, aż użytkownik o naciśnięcie klawisza.

Aby zakończyć tę funkcję, musisz utworzyć nowy `async Task` zwracanie metody, która rozpoczyna się oba te zadania (`GetInput` i `ShowTeleprompter`) i zarządza także udostępnionych danych między tymi dwoma zadaniami.

Nadszedł czas, aby utworzyć klasę, która może obsłużyć udostępnionych danych między tymi dwoma zadaniami. Ta klasa zawiera dwie właściwości publicznej: opóźnienie i flagę `Done` wskazująca całkowicie odczytać pliku:

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        private object lockHandle = new object();
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            lock (lockHandle)
            {
                DelayInMilliseconds = newDelay;
            }
        }

        public bool Done { get; private set; }

        public void SetDone()
        {
            Done = true;
        }
    }
}
```

Umieść tej klasy w pliku i ująć tej klasy w `TeleprompterConsole` przestrzeni nazw, jak pokazano powyżej. Należy również dodać `using static` instrukcji, dzięki czemu można odwoływać się `Min` i `Max` metody bez otaczającej nazwy klasy lub obszaru nazw. A [ `using static` ](../language-reference/keywords/using-static.md) instrukcji imports metody z jedną klasę. Jest to contrast z `using` instrukcji używany do tego punktu, które zostały zaimportowane wszystkie klasy z przestrzeni nazw.

```csharp
using static System.Math;
```

Jest inna funkcja języka, który jest nowy [ `lock` ](../language-reference/keywords/lock-statement.md) instrukcji. Ta instrukcja zapewnia tylko jednego wątku można w tym kod w danym momencie. Jeśli jeden wątek znajduje się w sekcji zablokowane, inne wątki należy poczekać na zakończenie tej sekcji pierwszy wątku. `lock` Instrukcja używa obiektu, który chroni sekcji blokady. Ta klasa jest zgodna standardowe idiom można zablokować obiektu prywatny w klasie.

Następnie należy zaktualizować `ShowTeleprompter` i `GetInput` metod do używania nowych `config` obiektu. Zapis final jeden `Task` zwracanie `async` metody w celu uruchamiania obu zadań i zamknąć po zakończeniu pierwszego zadania:

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

Jeden nowej metody w tym miejscu jest <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> wywołania. Który tworzy `Task` który zakończy się natychmiast po ukończeniu zadań z listy argumentów.

Następnie należy zaktualizować zarówno `ShowTeleprompter` i `GetInput` metod do zastosowania `config` obiektu opóźnienia:

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(config.DelayInMilliseconds);
        }
    }
    config.SetDone();
}

private static async Task GetInput(TelePrompterConfig config)
{
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
                config.UpdateDelay(-10);
            else if (key.KeyChar == '<')
                config.UpdateDelay(10);
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

Tej nowej wersji `ShowTeleprompter` odwołuje się nowa metoda `TeleprompterConfig` klasy. Teraz, musisz zaktualizować `Main` do wywołania `RunTeleprompter` zamiast `ShowTeleprompter`:

```csharp
RunTeleprompter().Wait();
```

## <a name="conclusion"></a>Wniosek

W tym samouczku przedstawiono możesz szereg funkcji języka C# i bibliotek .NET Core powiązane z pracy w aplikacji konsoli.
Można tworzyć na ta wiedza, aby zapoznać się więcej o języku i klasy wprowadzone w tym miejscu. Przedstawiono podstawowe informacje o pliku i konsoli operacje We/Wy, użyj blokujące i nieblokujące programowania asynchronicznego opartego na zadaniach, samouczek języka C# i organizowania programów C# i interfejsu wiersza polecenia programu .NET Core i narzędzi.

Aby uzyskać więcej informacji na temat We/Wy plików, zobacz [plików i we/wy strumienia](../../standard/io/index.md) tematu. Aby uzyskać więcej informacji na temat asynchronicznej model programowania używany w tym samouczku, zobacz [opartego na zadaniach asynchronicznej programowania](../..//standard/parallel-programming/task-based-asynchronous-programming.md) tematu i [programowanie asynchroniczne](../async.md) tematu.
