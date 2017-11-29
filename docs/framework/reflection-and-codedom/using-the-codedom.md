---
title: "Używanie modelu CodeDOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- Code Document Object Model
- Code Document Object Model, graphs
- types, CodeDOM
- namespaces [.NET Framework], CodeDOM
- templated code generation
- dynamically representing source code
- source code models
- CodeDOM
- graphing with CodeDOM
- dynamic compilation
- code generators
- CodeDOM, graphs
ms.assetid: 0444ddf3-c3f6-44ed-a999-f710d9c3e0cf
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 939a64919e9982232f6e8bd99070fe96e242b9bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-codedom"></a><span data-ttu-id="7d06a-102">Używanie modelu CodeDOM</span><span class="sxs-lookup"><span data-stu-id="7d06a-102">Using the CodeDOM</span></span>
<span data-ttu-id="7d06a-103">Modelu CodeDOM zawiera typy, które reprezentują wiele typów wspólnych elementów kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="7d06a-103">The CodeDOM provides types that represent many common types of source code elements.</span></span> <span data-ttu-id="7d06a-104">Można zaprojektować program, który tworzy modelu kodu źródłowego za pomocą modelu CodeDOM elementów do łączenia z wykresu obiektu.</span><span class="sxs-lookup"><span data-stu-id="7d06a-104">You can design a program that builds a source code model using CodeDOM elements to assemble an object graph.</span></span> <span data-ttu-id="7d06a-105">Ten wykres obiektu może być renderowany jako kodu źródłowego za pomocą modelu CodeDOM generator kodu dla obsługiwanych języków programowania.</span><span class="sxs-lookup"><span data-stu-id="7d06a-105">This object graph can be rendered as source code using a CodeDOM code generator for a supported programming language.</span></span> <span data-ttu-id="7d06a-106">Modelu CodeDOM mogą służyć do kompilowania kodu źródłowego w ramach zestawu binarnego.</span><span class="sxs-lookup"><span data-stu-id="7d06a-106">The CodeDOM can also be used to compile source code into a binary assembly.</span></span>  
  
 <span data-ttu-id="7d06a-107">Niektóre typowe zastosowania modelu CodeDOM obejmują:</span><span class="sxs-lookup"><span data-stu-id="7d06a-107">Some common uses for the CodeDOM include:</span></span>  
  
-   <span data-ttu-id="7d06a-108">Generowanie kodu opartego na szablonie: generowanie kodu dla platformy ASP.NET, serwery proxy klienta usług XML sieci Web, kreatorów kodu, projektantów lub innych mechanizmów emitowanie kodu.</span><span class="sxs-lookup"><span data-stu-id="7d06a-108">Templated code generation: generating code for ASP.NET, XML Web services client proxies, code wizards, designers, or other code-emitting mechanisms.</span></span>  
  
-   <span data-ttu-id="7d06a-109">Dynamiczne kompilowanie: Obsługa kompilacji kodu w jednym lub wielu języków.</span><span class="sxs-lookup"><span data-stu-id="7d06a-109">Dynamic compilation: supporting code compilation in single or multiple languages.</span></span>  
  
## <a name="building-a-codedom-graph"></a><span data-ttu-id="7d06a-110">Tworzenie wykresu CodeDOM</span><span class="sxs-lookup"><span data-stu-id="7d06a-110">Building a CodeDOM Graph</span></span>  
 <span data-ttu-id="7d06a-111"><xref:System.CodeDom> Przestrzeń nazw zawiera klasy reprezentujący struktury logicznej kodu źródłowego, niezależnie od składni języka.</span><span class="sxs-lookup"><span data-stu-id="7d06a-111">The <xref:System.CodeDom> namespace provides classes for representing the logical structure of source code, independent of language syntax.</span></span>  
  
### <a name="the-structure-of-a-codedom-graph"></a><span data-ttu-id="7d06a-112">Struktura wykresu CodeDOM</span><span class="sxs-lookup"><span data-stu-id="7d06a-112">The Structure of a CodeDOM Graph</span></span>  
 <span data-ttu-id="7d06a-113">Struktura wykresu CodeDOM przypomina drzewa kontenerów.</span><span class="sxs-lookup"><span data-stu-id="7d06a-113">The structure of a CodeDOM graph is like a tree of containers.</span></span> <span data-ttu-id="7d06a-114">Najwyższy, lub główny, kontener każdego można skompilować dla wykresu CodeDOM jest <xref:System.CodeDom.CodeCompileUnit>.</span><span class="sxs-lookup"><span data-stu-id="7d06a-114">The top-most, or root, container of each compilable CodeDOM graph is a <xref:System.CodeDom.CodeCompileUnit>.</span></span> <span data-ttu-id="7d06a-115">Każdy element modelu kodu źródłowego musi być połączony do wykresu za pomocą właściwości <xref:System.CodeDom.CodeObject> na wykresie.</span><span class="sxs-lookup"><span data-stu-id="7d06a-115">Every element of your source code model must be linked into the graph through a property of a <xref:System.CodeDom.CodeObject> in the graph.</span></span>  
  
### <a name="building-a-source-code-model-for-a-sample-hello-world-program"></a><span data-ttu-id="7d06a-116">Tworzenie modelu kodu źródłowego przykładowy Program Hello World</span><span class="sxs-lookup"><span data-stu-id="7d06a-116">Building a Source Code Model for a Sample Hello World Program</span></span>  
 <span data-ttu-id="7d06a-117">Poniższe wskazówki zawiera przykład sposobu tworzenia wykresu CodeDOM obiekt reprezentujący kod prostej aplikacji Hello World.</span><span class="sxs-lookup"><span data-stu-id="7d06a-117">The following walkthrough provides an example of how to build a CodeDOM object graph that represents the code for a simple Hello World application.</span></span> <span data-ttu-id="7d06a-118">Aby kod źródłowy pełną w tym przykładzie kodu, zobacz <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> tematu.</span><span class="sxs-lookup"><span data-stu-id="7d06a-118">For the complete source code for this code example, see the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> topic.</span></span>  
  
#### <a name="creating-a-compile-unit"></a><span data-ttu-id="7d06a-119">Tworzenie jednostki kompilacji</span><span class="sxs-lookup"><span data-stu-id="7d06a-119">Creating a compile unit</span></span>  
 <span data-ttu-id="7d06a-120">Modelu CodeDOM definiuje obiekt o nazwie <xref:System.CodeDom.CodeCompileUnit>, które odwołują się CodeDOM wykres obiektu, który modele kodu źródłowego, aby skompilować.</span><span class="sxs-lookup"><span data-stu-id="7d06a-120">The CodeDOM defines an object called a <xref:System.CodeDom.CodeCompileUnit>, which can reference a CodeDOM object graph that models the source code to compile.</span></span> <span data-ttu-id="7d06a-121">A **elementu CodeCompileUnit** ma właściwości do przechowywania odwołań do atrybutów, obszary nazw i zestawów.</span><span class="sxs-lookup"><span data-stu-id="7d06a-121">A **CodeCompileUnit** has properties for storing references to attributes, namespaces, and assemblies.</span></span>  
  
 <span data-ttu-id="7d06a-122">Dostawcy CodeDom, które pochodzą z <xref:System.CodeDom.Compiler.CodeDomProvider> klasa zawiera metody, które przetwarzają wykres obiektu odwołuje się **elementu CodeCompileUnit**.</span><span class="sxs-lookup"><span data-stu-id="7d06a-122">The CodeDom providers that derive from the <xref:System.CodeDom.Compiler.CodeDomProvider> class contain methods that process the object graph referenced by a **CodeCompileUnit**.</span></span>  
  
 <span data-ttu-id="7d06a-123">Aby utworzyć wykres obiektu dla prostej aplikacji, należy utworzyć model kodu źródłowego i odwołania z **elementu CodeCompileUnit**.</span><span class="sxs-lookup"><span data-stu-id="7d06a-123">To create an object graph for a simple application, you must assemble the source code model and reference it from a **CodeCompileUnit**.</span></span>  
  
 <span data-ttu-id="7d06a-124">Można utworzyć nową jednostkę kompilacji przy użyciu składni zostało to pokazane w tym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="7d06a-124">You can create a new compile unit with the syntax demonstrated in this example:</span></span>  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 <span data-ttu-id="7d06a-125">A <xref:System.CodeDom.CodeSnippetCompileUnit> może zawierać części kodu źródłowego, który jest już w języku docelowym, ale nie można renderować na inny język.</span><span class="sxs-lookup"><span data-stu-id="7d06a-125">A <xref:System.CodeDom.CodeSnippetCompileUnit> can contain a section of source code that is already in the target language, but cannot be rendered to another language.</span></span>  
  
#### <a name="defining-a-namespace"></a><span data-ttu-id="7d06a-126">Definiowanie przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="7d06a-126">Defining a namespace</span></span>  
 <span data-ttu-id="7d06a-127">Aby zdefiniować przestrzeni nazw, należy utworzyć <xref:System.CodeDom.CodeNamespace> i przypisać mu nazwę dla niego przy użyciu odpowiedniego konstruktora lub przez ustawienie jej **nazwa** właściwości.</span><span class="sxs-lookup"><span data-stu-id="7d06a-127">To define a namespace, create a <xref:System.CodeDom.CodeNamespace> and assign a name for it using the appropriate constructor or by setting its **Name** property.</span></span>  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### <a name="importing-a-namespace"></a><span data-ttu-id="7d06a-128">Importowanie przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="7d06a-128">Importing a namespace</span></span>  
 <span data-ttu-id="7d06a-129">Aby dodać dyrektywy importu przestrzeni nazw do przestrzeni nazw, należy dodać <xref:System.CodeDom.CodeNamespaceImport> wskazujące przestrzeni nazw, aby zaimportować **CodeNamespace.Imports** kolekcji.</span><span class="sxs-lookup"><span data-stu-id="7d06a-129">To add a namespace import directive to the namespace, add a <xref:System.CodeDom.CodeNamespaceImport> that indicates the namespace to import to the **CodeNamespace.Imports** collection.</span></span>  
  
 <span data-ttu-id="7d06a-130">Poniższy kod dodaje importu dla **systemu** przestrzeni nazw do **importów** Kolekcja **Element CodeNamespace** o nazwie `samples`:</span><span class="sxs-lookup"><span data-stu-id="7d06a-130">The following code adds an import for the **System** namespace to the **Imports** collection of a **CodeNamespace** named `samples`:</span></span>  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### <a name="linking-code-elements-into-the-object-graph"></a><span data-ttu-id="7d06a-131">Łączenie elementów kodu do obiektu wykresu</span><span class="sxs-lookup"><span data-stu-id="7d06a-131">Linking code elements into the object graph</span></span>  
 <span data-ttu-id="7d06a-132">Wszystkie elementy kodu, które tworzą wykresu CodeDOM musi być połączone z <xref:System.CodeDom.CodeCompileUnit> będący elementem głównym drzewa przez szereg odwołania między elementami odwoływać się bezpośrednio z właściwości obiektu głównego wykresu.</span><span class="sxs-lookup"><span data-stu-id="7d06a-132">All code elements that form a CodeDOM graph must be linked to the <xref:System.CodeDom.CodeCompileUnit> that is the root element of the tree by a series of references between elements directly referenced from the properties of the root object of the graph.</span></span> <span data-ttu-id="7d06a-133">Ustaw obiektu z właściwością obiektu kontenera, aby ustanowić odwołanie z obiektu kontenera.</span><span class="sxs-lookup"><span data-stu-id="7d06a-133">Set an object to a property of a container object to establish a reference from the container object.</span></span>  
  
 <span data-ttu-id="7d06a-134">Następująca instrukcja dodaje `samples` **Element CodeNamespace** do **przestrzeni nazw** właściwości kolekcji głównego **elementu CodeCompileUnit**.</span><span class="sxs-lookup"><span data-stu-id="7d06a-134">The following statement adds the `samples` **CodeNamespace** to the **Namespaces** collection property of the root **CodeCompileUnit**.</span></span>  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### <a name="defining-a-type"></a><span data-ttu-id="7d06a-135">Definiowanie typu</span><span class="sxs-lookup"><span data-stu-id="7d06a-135">Defining a type</span></span>  
 <span data-ttu-id="7d06a-136">Aby zadeklarować klasy, struktury, interfejsu lub wyliczenia za pomocą modelu CodeDOM, Utwórz nową <xref:System.CodeDom.CodeTypeDeclaration>i przypisz mu nazwę.</span><span class="sxs-lookup"><span data-stu-id="7d06a-136">To declare a class, structure, interface, or enumeration using the CodeDOM, create a new <xref:System.CodeDom.CodeTypeDeclaration>, and assign it a name.</span></span> <span data-ttu-id="7d06a-137">W poniższym przykładzie pokazano, to można ustawić przy użyciu przeładowania konstruktora **nazwa** właściwości:</span><span class="sxs-lookup"><span data-stu-id="7d06a-137">The following example demonstrates this using a constructor overload to set the **Name** property:</span></span>  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 <span data-ttu-id="7d06a-138">Aby dodać typ do przestrzeni nazw, należy dodać <xref:System.CodeDom.CodeTypeDeclaration> reprezentujący typu do dodania do przestrzeni nazw do **typy** Kolekcja **Element CodeNamespace**.</span><span class="sxs-lookup"><span data-stu-id="7d06a-138">To add a type to a namespace, add a <xref:System.CodeDom.CodeTypeDeclaration> that represents the type to add to the namespace to the **Types** collection of a **CodeNamespace**.</span></span>  
  
 <span data-ttu-id="7d06a-139">W poniższym przykładzie pokazano, jak dodać klasę o nazwie `class1` do **Element CodeNamespace** o nazwie `samples`:</span><span class="sxs-lookup"><span data-stu-id="7d06a-139">The following example demonstrates how to add a class named `class1` to a **CodeNamespace** named `samples`:</span></span>  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### <a name="adding-class-members-to-a-class"></a><span data-ttu-id="7d06a-140">Dodawanie elementów członkowskich klasy do klasy</span><span class="sxs-lookup"><span data-stu-id="7d06a-140">Adding class members to a class</span></span>  
 <span data-ttu-id="7d06a-141"><xref:System.CodeDom> Przestrzeń nazw zawiera różne elementy, które mogą służyć do reprezentowania elementów członkowskich klasy.</span><span class="sxs-lookup"><span data-stu-id="7d06a-141">The <xref:System.CodeDom> namespace provides a variety of elements that can be used to represent class members.</span></span> <span data-ttu-id="7d06a-142">Każdy element członkowski klasy mogą być dodawane do **członków** kolekcji <xref:System.CodeDom.CodeTypeDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="7d06a-142">Each class member can be added to the **Members** collection of a <xref:System.CodeDom.CodeTypeDeclaration>.</span></span>  
  
#### <a name="defining-a-code-entry-point-method-for-an-executable"></a><span data-ttu-id="7d06a-143">Definiowanie metoda punktu wejścia w kodzie pliku wykonywalnego</span><span class="sxs-lookup"><span data-stu-id="7d06a-143">Defining a code entry point method for an executable</span></span>  
 <span data-ttu-id="7d06a-144">Jeśli tworzysz kod program wykonywalny, należy wskazać punkt wejścia programu, tworząc <xref:System.CodeDom.CodeEntryPointMethod> do metody w programu, które należy rozpocząć wykonywania reprezentowania.</span><span class="sxs-lookup"><span data-stu-id="7d06a-144">If you are building code for an executable program, it is necessary to indicate the entry point of a program by creating a <xref:System.CodeDom.CodeEntryPointMethod> to represent the method at which program execution should begin.</span></span>  
  
 <span data-ttu-id="7d06a-145">W poniższym przykładzie pokazano sposób definiowania metoda punktu wejścia, który zawiera <xref:System.CodeDom.CodeMethodInvokeExpression> wywołującym **System.Console.WriteLine** do drukowania "Witaj świecie!":</span><span class="sxs-lookup"><span data-stu-id="7d06a-145">The following example demonstrates how to define an entry point method that contains a <xref:System.CodeDom.CodeMethodInvokeExpression> that calls **System.Console.WriteLine** to print "Hello World!":</span></span>  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 <span data-ttu-id="7d06a-146">Następująca instrukcja dodaje metodę punktu wejścia o nazwie `Start` do **członków** Kolekcja `class1`:</span><span class="sxs-lookup"><span data-stu-id="7d06a-146">The following statement adds the entry point method named `Start` to the **Members** collection of `class1`:</span></span>  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 <span data-ttu-id="7d06a-147">Teraz <xref:System.CodeDom.CodeCompileUnit> o nazwie `compileUnit` zawiera wykresu CodeDOM dla prosty program Hello World.</span><span class="sxs-lookup"><span data-stu-id="7d06a-147">Now the <xref:System.CodeDom.CodeCompileUnit> named `compileUnit` contains the CodeDOM graph for a simple Hello World program.</span></span> <span data-ttu-id="7d06a-148">Aby uzyskać informacje na generowanie i kompilowanie kodu z wykresu CodeDOM, zobacz [generowanie kodu źródłowego i kompilowanie programu z wykresu CodeDOM](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md).</span><span class="sxs-lookup"><span data-stu-id="7d06a-148">For information on generating and compiling code from a CodeDOM graph, see [Generating Source Code and Compiling a Program from a CodeDOM Graph](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md).</span></span>  
  
### <a name="more-information-on-building-a-codedom-graph"></a><span data-ttu-id="7d06a-149">Więcej informacji na temat tworzenia wykresu CodeDOM</span><span class="sxs-lookup"><span data-stu-id="7d06a-149">More information on building a CodeDOM graph</span></span>  
 <span data-ttu-id="7d06a-150">Modelu CodeDOM obsługuje wiele typów wspólnych elementów kodu w językach programowania, które obsługują środowisko uruchomieniowe języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="7d06a-150">The CodeDOM supports the many common types of code elements found in programming languages that support the common language runtime.</span></span> <span data-ttu-id="7d06a-151">Modelu CodeDOM nie został zaprojektowany do przekazywania elementów do reprezentowania wszystkich możliwości funkcji języka programowania.</span><span class="sxs-lookup"><span data-stu-id="7d06a-151">The CodeDOM was not designed to provide elements to represent all possible programming language features.</span></span> <span data-ttu-id="7d06a-152">Kod, który nie może być reprezentowana łatwo CodeDOM elementów można hermetyzowane w <xref:System.CodeDom.CodeSnippetExpression>, <xref:System.CodeDom.CodeSnippetStatement>, <xref:System.CodeDom.CodeSnippetTypeMember>, lub <xref:System.CodeDom.CodeSnippetCompileUnit>.</span><span class="sxs-lookup"><span data-stu-id="7d06a-152">Code that cannot be represented easily with CodeDOM elements can be encapsulated in a <xref:System.CodeDom.CodeSnippetExpression>, a <xref:System.CodeDom.CodeSnippetStatement>, a <xref:System.CodeDom.CodeSnippetTypeMember>, or a <xref:System.CodeDom.CodeSnippetCompileUnit>.</span></span> <span data-ttu-id="7d06a-153">Jednak fragmentów nie można przetłumaczyć na inne języki automatycznie za pomocą modelu CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="7d06a-153">However, snippets cannot be translated to other languages automatically by the CodeDOM.</span></span>  
  
 <span data-ttu-id="7d06a-154">Dokumentacja dla każdego z typów CodeDOM, zobacz dokumentację odwołanie <xref:System.CodeDom> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="7d06a-154">For documentation for the each of the CodeDOM types, see the reference documentation for the <xref:System.CodeDom> namespace.</span></span>  
  
 <span data-ttu-id="7d06a-155">Szybkie wykresu można znaleźć elementu CodeDOM, który reprezentuje element kodu dla określonego typu, zobacz [CodeDOM krótkimi opisami](http://msdn.microsoft.com/en-us/c77b8bfd-0a32-4e36-b59a-4f687f32c524).</span><span class="sxs-lookup"><span data-stu-id="7d06a-155">For a quick chart to locate the CodeDOM element that represents a specific type of code element, see the [CodeDOM Quick Reference](http://msdn.microsoft.com/en-us/c77b8bfd-0a32-4e36-b59a-4f687f32c524).</span></span>