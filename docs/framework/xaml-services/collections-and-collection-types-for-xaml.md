---
title: Kolekcje i typy kolekcji dla XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
caps.latest.revision: "2"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 991360433b5fb09c13e59f63be94e0fa0ec94b61
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="collections-and-collection-types-for-xaml"></a><span data-ttu-id="8bc90-102">Kolekcje i typy kolekcji dla XAML</span><span class="sxs-lookup"><span data-stu-id="8bc90-102">Collections and Collection Types for XAML</span></span>
<span data-ttu-id="8bc90-103">W tym temacie opisano sposób definiowania właściwości typów, które są przeznaczone do obsługi kolekcji, a także do obsługi składni języka XAML dla wystąpienia elementy kolekcji jako elementy podrzędne elementu nadrzędnego obiektu lub właściwości elementu.</span><span class="sxs-lookup"><span data-stu-id="8bc90-103">This topic describes how to define properties of types that are intended to support a collection, and to support the XAML syntax for instantiating collection items as element children of a parent object element or property element.</span></span>  
  
## <a name="xaml-collection-concepts"></a><span data-ttu-id="8bc90-104">Pojęcia dotyczące kolekcji XAML</span><span class="sxs-lookup"><span data-stu-id="8bc90-104">XAML Collection Concepts</span></span>  
 <span data-ttu-id="8bc90-105">Koncepcyjnie żadnej z relacji w kodzie XAML, gdzie istnieje wiele elementów podrzędnych w zakresie XAML object element lub element właściwości XAML muszą zostać zaimplementowane jako kolekcja.</span><span class="sxs-lookup"><span data-stu-id="8bc90-105">Conceptually, any relationship in XAML where there are multiple child items within the scope of a XAML object element or XAML property element must be implemented as a collection.</span></span> <span data-ttu-id="8bc90-106">Tej kolekcji musi być skojarzona z właściwością XAML określonego typu XAML, który jest nadrzędny w tej relacji.</span><span class="sxs-lookup"><span data-stu-id="8bc90-106">That collection must be associated with a particular XAML property of the XAML type that is the parent in that relationship.</span></span> <span data-ttu-id="8bc90-107">Właściwość musi być kolekcją, ponieważ procesor XAML oczekuje można przypisać każdego elementu w znaczniku jako nowo dodanego elementu zapasowy właściwości kolekcji.</span><span class="sxs-lookup"><span data-stu-id="8bc90-107">The property must be a collection because a XAML processor expects to assign each item in markup to be a newly added item of the backing collection property.</span></span>  
  
 <span data-ttu-id="8bc90-108">Na poziomie języka XAML dokładne wymagania dotyczące obsługi kolekcji nie są całkowicie zdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="8bc90-108">At the XAML language level, the exact requirements of collection support are not fully defined.</span></span> <span data-ttu-id="8bc90-109">Koncepcji, że kolekcja może być albo listy lub słownika (ale nie oba) jest zdefiniowana na poziomie języka XAML, ale typy zapasowy, które reprezentują albo list lub słowników nie jest zdefiniowany w języku XAML.</span><span class="sxs-lookup"><span data-stu-id="8bc90-109">The concept that a collection can be either a list or a dictionary(but not both) is defined at the XAML language level, but which backing types represent either lists or dictionaries is not defined by the XAML language.</span></span>  
  
 <span data-ttu-id="8bc90-110">W programie .NET Framework XAML Services pojęcie XAML Obsługa kolekcji jest więcej jasno określone pod względem .NET Framework kopii typów.</span><span class="sxs-lookup"><span data-stu-id="8bc90-110">In .NET Framework XAML Services, the concept of XAML collection support is more clearly defined in terms of .NET Framework backing types.</span></span> <span data-ttu-id="8bc90-111">W szczególności XAML obsługę kolekcje opiera się na kilka pojęć .NET Framework i interfejsów API, które są używane w przypadku list i słowników w ogólne programowania .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8bc90-111">Specifically, the XAML support for collections is based on several .NET Framework concepts and APIs that are used for lists and dictionaries in general .NET Framework programming.</span></span>  
  
1.  <span data-ttu-id="8bc90-112"><xref:System.Collections.IList> Interfejsu wskazuje kolekcji list.</span><span class="sxs-lookup"><span data-stu-id="8bc90-112">The <xref:System.Collections.IList> interface indicates a list collection.</span></span>  
  
2.  <span data-ttu-id="8bc90-113"><xref:System.Collections.IDictionary> Interfejsu wskazuje dicionary kolekcji.</span><span class="sxs-lookup"><span data-stu-id="8bc90-113">The <xref:System.Collections.IDictionary> interface indicates a dicionary collection.</span></span>  
  
3.  <span data-ttu-id="8bc90-114"><xref:System.Array>reprezentuje tablicę i tablicy obsługuje <xref:System.Collections.IList> metody.</span><span class="sxs-lookup"><span data-stu-id="8bc90-114"><xref:System.Array> represents an array, and an array supports <xref:System.Collections.IList> methods.</span></span>  
  
 <span data-ttu-id="8bc90-115">W każdym z tych pojęć kolekcji procesora .NET Framework XAML Services XAML oczekuje, że wywołanie `Add` metody na określonym wystąpieniu typu właściwości kolekcji.</span><span class="sxs-lookup"><span data-stu-id="8bc90-115">In each of these collection concepts, a .NET Framework XAML Services XAML processor expects to call the `Add` method on a specific instance of the collection property's type.</span></span> <span data-ttu-id="8bc90-116">Lub, w przypadku serializacji, procesor XAML tworzy osobne wystąpienia typu XAML dla każdego elementu listy, słownika lub tablicy oparte na każdej kolekcji specyficzną koncepcję "Elementów".</span><span class="sxs-lookup"><span data-stu-id="8bc90-116">Or, in a serialization scenario, a XAML processor produces discrete XAML-type instances for each item found in the list, dictionary or array based on each collection's specific concept of "Items".</span></span> <span data-ttu-id="8bc90-117">Są to: <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; jawnych <xref:System.Array.System%23Collections%23IList%23Item%2A> dla <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="8bc90-117">These are : <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; the explicit <xref:System.Array.System%23Collections%23IList%23Item%2A> for <xref:System.Array>.</span></span>  
  
## <a name="generic-collections"></a><span data-ttu-id="8bc90-118">Kolekcje ogólne</span><span class="sxs-lookup"><span data-stu-id="8bc90-118">Generic Collections</span></span>  
 <span data-ttu-id="8bc90-119">Kolekcje ogólne mogą być przydatne podczas programowania ogólne .NET Framework i może również służyć do właściwości kolekcji XAML.</span><span class="sxs-lookup"><span data-stu-id="8bc90-119">Generic collections can be useful for general .NET Framework programming, and can also be used for XAML collection properties.</span></span> <span data-ttu-id="8bc90-120">Jednak ogólnych interfejsów <xref:System.Collections.Generic.IList%601> i <xref:System.Collections.Generic.IDictionary%602> nie są identyfikowane przez .NET Framework XAML Services XAML procesorów jako równoważne nieogólnego <xref:System.Collections.IList> lub <xref:System.Collections.IDictionary>.</span><span class="sxs-lookup"><span data-stu-id="8bc90-120">However, the generic interfaces <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IDictionary%602> are not identified by .NET Framework XAML Services XAML processors as being equivalent to the non-generic <xref:System.Collections.IList> or <xref:System.Collections.IDictionary>.</span></span> <span data-ttu-id="8bc90-121">Zamiast implementacji interfejsów, zalecane podejście do typy kolekcji ogólnych właściwości ma pochodzić od klasy <xref:System.Collections.Generic.List%601> lub <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="8bc90-121">Rather than implementing the interfaces, a recommended approach for generic collection property types is to derive from the classes <xref:System.Collections.Generic.List%601> or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="8bc90-122">Te klasy implementować interfejsów nieogólnego i w związku z tym obejmują oczekiwanego obsługę kolekcje XAML w implementacji podstawowej.</span><span class="sxs-lookup"><span data-stu-id="8bc90-122">These classes implement the non-generic interfaces and thus include the expected support for XAML collections in the base implementation.</span></span>  
  
## <a name="read-only-collections-and-initialization-logic"></a><span data-ttu-id="8bc90-123">Kolekcji tylko do odczytu i logikę inicjującą</span><span class="sxs-lookup"><span data-stu-id="8bc90-123">Read-Only Collections and Initialization Logic</span></span>  
 <span data-ttu-id="8bc90-124">W programie .NET Framework programowania jest wspólnego wzorca projektowego dokonanie dowolnej właściwości, która zawiera wartość z kolekcji jako kolekcji tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="8bc90-124">In .NET Framework programming, it is a common design pattern to make any property that holds a value of a collection as a read-only collection.</span></span> <span data-ttu-id="8bc90-125">Ten wzorzec zezwala na wystąpienie, które należą do lepszą kontrolę, co się dzieje z kolekcji właściwości kolekcji.</span><span class="sxs-lookup"><span data-stu-id="8bc90-125">This pattern permits the instance that owns the collection property to better control what happens to the collection..</span></span> <span data-ttu-id="8bc90-126">W szczególności wzorzec zapobiega przypadkowemu zastąpienie istniejącego całą kolekcję przez ustawienie właściwości.</span><span class="sxs-lookup"><span data-stu-id="8bc90-126">Specifically, the pattern prevents accidental replacement of the entire pre-existing collection by setting the property.</span></span> <span data-ttu-id="8bc90-127">W tym wzorcu dostęp do kolekcji przez obiekty wywołujące zamiast tego należy ustanowić przez wywołanie metody lub właściwości obsługiwana przez typ kolekcji i/lub interfejsy odpowiednich kolekcji, takie jak <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="8bc90-127">In this pattern, any access to the collection by callers should instead be made by calling methods or properties as supported by the collection type and/or the relevant collection interfaces such as <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="8bc90-128">Za pomocą tego wzorca oznacza, że każdej klasy, która udostępnia właściwości kolekcji tylko do odczytu najpierw należy zainicjować tej właściwości, aby pomieścić pustą kolekcję.</span><span class="sxs-lookup"><span data-stu-id="8bc90-128">Using this pattern implies that any class that exposes a read-only collection property must first initialize that property to hold an empty collection.</span></span> <span data-ttu-id="8bc90-129">Zwykle inicjowania jest wykonywane jako część konstrukcji zachowanie dla klasy.</span><span class="sxs-lookup"><span data-stu-id="8bc90-129">Typically the initialization is performed as part of the construction behavior for the class.</span></span> <span data-ttu-id="8bc90-130">Powinna być użyteczna dla XAML, jest ważne, że takie logiki zawsze odwołuje się konstruktora domyślnego ponieważ XAML zazwyczaj wywołuje konstruktor domyślny przed przetworzeniem właściwości (właściwości kolekcji lub w inny sposób).</span><span class="sxs-lookup"><span data-stu-id="8bc90-130">To be useful for XAML, it is important that such logic is always referenced by the default constructor, because XAML generally calls the default constructor prior to processing the properties (collection properties or otherwise).</span></span>  
  
## <a name="xaml-type-system-support-and-collections"></a><span data-ttu-id="8bc90-131">Obsługa systemu typu XAML i kolekcji</span><span class="sxs-lookup"><span data-stu-id="8bc90-131">XAML Type System Support and Collections</span></span>  
 <span data-ttu-id="8bc90-132">Poza podstawowa mechanika analizowania XAML i wypełnianie lub serializowania właściwości kolekcji system typów języka XAML zgodnie z implementacją w .NET Framework XAML Services zawiera kilka funkcji projektowania odnoszą się do kolekcji w języku XAML.</span><span class="sxs-lookup"><span data-stu-id="8bc90-132">Beyond the basic mechanics of parsing XAML and populating or serializing collection properties, the XAML type system as implemented in .NET Framework XAML Services includes several design features that pertain to collections in XAML.</span></span>  
  
1.  <span data-ttu-id="8bc90-133"><xref:System.Xaml.XamlType.IsCollection%2A>Zwraca wartość true, jeśli typ XAML nie jest obsługiwana przez typ, który zapewnia obsługę kolekcji XAML.</span><span class="sxs-lookup"><span data-stu-id="8bc90-133"><xref:System.Xaml.XamlType.IsCollection%2A> returns true if the XAML type is backed by a type that provides XAML collection support.</span></span>  
  
2.  <span data-ttu-id="8bc90-134"><xref:System.Xaml.XamlType.IsDictionary%2A>i <xref:System.Xaml.XamlType.IsArray%2A> dalsze zidentyfikuje, który typ XAML obsługuje tryb kolekcji.</span><span class="sxs-lookup"><span data-stu-id="8bc90-134"><xref:System.Xaml.XamlType.IsDictionary%2A> and <xref:System.Xaml.XamlType.IsArray%2A> can further identify which collection mode the XAML type supports.</span></span> <span data-ttu-id="8bc90-135">Dla XAML niestandardowych procesorów, które są oparte na usług .NET Framework XAML i XAML system typów, ale nie jest oparty na istniejących <xref:System.Xaml.XamlWriter> implementacji, wiedząc, który tryb kolekcji jest używany może być konieczne, aby wiedzieć, którego metoda do wywołania dla Przetwarzanie kolekcji.</span><span class="sxs-lookup"><span data-stu-id="8bc90-135">For custom XAML processors that are based on .NET Framework XAML Services and the XAML type system but not based on existing <xref:System.Xaml.XamlWriter> implementations, knowing which collection mode is used might be necessary in order to know which method to invoke for collection processing.</span></span>  
  
3.  <span data-ttu-id="8bc90-136">Poprzednie wartości właściwości potencjalnie wpływało przesłonięcia <xref:System.Xaml.XamlType.LookupCollectionKind%2A> typu XAML.</span><span class="sxs-lookup"><span data-stu-id="8bc90-136">Each of the previous property values are potentially influenced by overrides of <xref:System.Xaml.XamlType.LookupCollectionKind%2A> on a XAML type.</span></span>