---
title: "Funkcjonalności transformacji XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 0ccb9251-38d7-44e3-9b84-1b5fe25e4b59
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bd63407901ed32f982a30aa7610590c853f15cf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="functional-transformation-of-xml-c"></a><span data-ttu-id="f9bb6-102">Funkcjonalności transformacji XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f9bb6-102">Functional Transformation of XML (C#)</span></span>
<span data-ttu-id="f9bb6-103">W tym temacie omówiono podejście czysty przekształcania funkcjonalności do modyfikowania dokumentów XML i zachowanie różni się od jego podejście procedurach.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-103">This topic discusses the pure functional transformation approach to modifying XML documents, and contrasts it with a procedural approach.</span></span>  
  
## <a name="modifying-an-xml-document"></a><span data-ttu-id="f9bb6-104">Modyfikowanie dokumentu XML</span><span class="sxs-lookup"><span data-stu-id="f9bb6-104">Modifying an XML Document</span></span>  
 <span data-ttu-id="f9bb6-105">Jest jednym z najbardziej typowych zadań dla programisty XML Przekształcanie XML z jednego kształtu do innego.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-105">One of the most common tasks for an XML programmer is transforming XML from one shape to another.</span></span> <span data-ttu-id="f9bb6-106">Kształt dokumentu XML jest strukturę dokumentu, który obejmuje następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="f9bb6-106">The shape of an XML document is the structure of the document, which includes the following:</span></span>  
  
-   <span data-ttu-id="f9bb6-107">Hierarchia, wyrażone w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-107">The hierarchy expressed by the document.</span></span>  
  
-   <span data-ttu-id="f9bb6-108">Nazwy elementów i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-108">The element and attribute names.</span></span>  
  
-   <span data-ttu-id="f9bb6-109">Typy danych elementów i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-109">The data types of the elements and attributes.</span></span>  
  
 <span data-ttu-id="f9bb6-110">Ogólnie rzecz biorąc najbardziej efektywnym sposobem Przekształcanie XML z jednego kształtu do innego jest czysty transformacji funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-110">In general, the most effective approach to transforming XML from one shape to another is that of pure functional transformation.</span></span> <span data-ttu-id="f9bb6-111">Takie podejście zadanie programisty podstawowy jest utworzyć transformację, która jest stosowana do całego dokumentu XML (lub jeden lub więcej węzłów ściśle określonych).</span><span class="sxs-lookup"><span data-stu-id="f9bb6-111">In this approach, the primary programmer task is to create a transformation which is applied to the entire XML document (or to one or more strictly defined nodes).</span></span> <span data-ttu-id="f9bb6-112">Przekształcenie funkcjonalności jest raczej najłatwiejsza do kodu (po programisty jest znany z podejścia), zwraca najbardziej łatwy w obsłudze kodu i jest często bardziej compact niż alternatywnych metod.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-112">Functional transformation is arguably the easiest to code (after a programmer is familiar with the approach), yields the most maintainable code, and is often more compact than alternative approaches.</span></span>  
  
### <a name="xml-functional-transformational-technologies"></a><span data-ttu-id="f9bb6-113">Funkcjonalności technologii Transformational XML</span><span class="sxs-lookup"><span data-stu-id="f9bb6-113">XML Functional Transformational Technologies</span></span>  
 <span data-ttu-id="f9bb6-114">Firma Microsoft oferuje dwie technologie przekształcania funkcjonalności do użycia w dokumentach XML: XSLT i LINQ do XML.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-114">Microsoft offers two functional transformation technologies for use on XML documents: XSLT and LINQ to XML.</span></span> <span data-ttu-id="f9bb6-115">XSLT jest obsługiwana w <xref:System.Xml.Xsl> zarządzane przestrzeni nazw w implementacji native COM programu MSXML.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-115">XSLT is supported in the <xref:System.Xml.Xsl> managed namespace and in the native COM implementation of MSXML.</span></span> <span data-ttu-id="f9bb6-116">Mimo że XSLT jest technologią niezawodne do manipulowania dokumentów XML, wymaga doświadczenia w domenie specjalne, czyli języka XSLT i jego obsługi interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-116">Although XSLT is a robust technology for manipulating XML documents, it requires expertise in a specialized domain, namely the XSLT language and its supporting APIs.</span></span>  
  
 <span data-ttu-id="f9bb6-117">LINQ do XML udostępnia narzędzia niezbędne do przekształcenia funkcjonalności czysty kod w obszerne i wydajny sposób kodem C# lub Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-117">LINQ to XML provides the tools necessary to code pure functional transformations in an expressive and powerful way, within C# or Visual Basic code.</span></span> <span data-ttu-id="f9bb6-118">Na przykład użyć wiele przykładów w składniku LINQ do XML dokumentacji czysty podejście funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-118">For example, many of the examples in the LINQ to XML documentation use a pure functional approach.</span></span> <span data-ttu-id="f9bb6-119">W przypadku [samouczek: manipulowanie zawartości w dokumencie schemat WordprocessingML (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) samouczku używamy LINQ do XML w funkcjonalności podejście do manipulowania informacje w dokumencie programu Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-119">Also, in the [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial, we use LINQ to XML in a functional approach to manipulate information in a Microsoft Word document.</span></span>  
  
 <span data-ttu-id="f9bb6-120">Bardziej szczegółowy porównanie LINQ do XML z innymi technologiami XML firmy Microsoft, zobacz [LINQ do XML programu vs. Inne technologie XML](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).</span><span class="sxs-lookup"><span data-stu-id="f9bb6-120">For a more complete comparison of LINQ to XML with other Microsoft XML technologies, see [LINQ to XML vs. Other XML Technologies](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).</span></span>  
  
 <span data-ttu-id="f9bb6-121">XSLT jest zalecanym narzędziem do przekształcenia zorientowany, gdy dokument źródłowy ma nieprawidłowe strukturę.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-121">XSLT is the recommended tool for  document-centric transformations when the source document has an irregular structure.</span></span> <span data-ttu-id="f9bb6-122">Jednak LINQ do XML można również wykonywać transformacje skoncentrowane na dokument.</span><span class="sxs-lookup"><span data-stu-id="f9bb6-122">However, LINQ to XML can also perform document-centric transforms.</span></span> <span data-ttu-id="f9bb6-123">Aby uzyskać więcej informacji, zobacz [porady: użycie adnotacji do przekształcania LINQ do XML drzew stylów XSLT (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style.md).</span><span class="sxs-lookup"><span data-stu-id="f9bb6-123">For more information, see [How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9bb6-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f9bb6-124">See Also</span></span>  
 [<span data-ttu-id="f9bb6-125">Wprowadzenie do przekształcenia funkcjonalności Pure (C#)</span><span class="sxs-lookup"><span data-stu-id="f9bb6-125">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
 [<span data-ttu-id="f9bb6-126">Samouczek: Manipulowanie zawartości w dokumencie schemat WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="f9bb6-126">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)  
 [<span data-ttu-id="f9bb6-127">LINQ do XML programu vs. Inne technologie XML</span><span class="sxs-lookup"><span data-stu-id="f9bb6-127">LINQ to XML vs. Other XML Technologies</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)