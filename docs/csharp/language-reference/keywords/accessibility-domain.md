---
title: "Domena dostępności (odwołanie w C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 127bacda4bf8363fccff3dd3ef6770ad50984cfb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="474e0-102">Domena dostępności (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="474e0-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="474e0-103">Domena dostępności elementu członkowskiego Określa, w sekcjach program, który może być przywoływany element członkowski.</span><span class="sxs-lookup"><span data-stu-id="474e0-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="474e0-104">Jeśli element członkowski jest zagnieżdżony w ramach innego rodzaju, jej domena dostępności jest określany przez zarówno [poziom dostępności](../../../csharp/language-reference/keywords/accessibility-levels.md) członka i domena dostępności typu zawierającego natychmiast.</span><span class="sxs-lookup"><span data-stu-id="474e0-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="474e0-105">Domena dostępności najwyższego poziomu typu jest co najmniej tekst programu projektu, które są zadeklarowane w.</span><span class="sxs-lookup"><span data-stu-id="474e0-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="474e0-106">Oznacza to, że domeny obejmuje wszystkie pliki źródłowe projektu.</span><span class="sxs-lookup"><span data-stu-id="474e0-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="474e0-107">Domena dostępności typu zagnieżdżonego jest co najmniej tekstu program typu, w którym jest zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="474e0-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="474e0-108">Oznacza to, że domena jest treści typu, który zawiera wszystkie typy zagnieżdżone.</span><span class="sxs-lookup"><span data-stu-id="474e0-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="474e0-109">Domena dostępności typu zagnieżdżonego nigdy nie przekracza typu zawierającego.</span><span class="sxs-lookup"><span data-stu-id="474e0-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="474e0-110">W poniższym przykładzie przedstawiono w tych pojęć.</span><span class="sxs-lookup"><span data-stu-id="474e0-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="474e0-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="474e0-111">Example</span></span>  
 <span data-ttu-id="474e0-112">Ten przykład zawiera typ najwyższego poziomu, `T1`, a dwie klasy zagnieżdżone `M1` i `M2`.</span><span class="sxs-lookup"><span data-stu-id="474e0-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="474e0-113">Klasy zawiera pola, które mają różne zadeklarowane dostępności.</span><span class="sxs-lookup"><span data-stu-id="474e0-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="474e0-114">W `Main` metody komentarz następuje każdej instrukcji, aby wskazać domeny ułatwień dostępu dla każdego elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="474e0-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="474e0-115">Należy zauważyć, że instrukcji, które próbuje odwołać niedostępny elementy członkowskie są oznaczone jako komentarz. Jeśli chcesz zobaczyć błędy kompilatora spowodowane odwołuje się do elementu członkowskiego niedostępny, Usuń komentarze jeden naraz.</span><span class="sxs-lookup"><span data-stu-id="474e0-115">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="474e0-116">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="474e0-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="474e0-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="474e0-117">See Also</span></span>  
 [<span data-ttu-id="474e0-118">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="474e0-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="474e0-119">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="474e0-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="474e0-120">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="474e0-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="474e0-121">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="474e0-121">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="474e0-122">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="474e0-122">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="474e0-123">Ograniczenia dotyczące używania poziomów ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="474e0-123">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="474e0-124">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="474e0-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="474e0-125">publiczny</span><span class="sxs-lookup"><span data-stu-id="474e0-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="474e0-126">prywatne</span><span class="sxs-lookup"><span data-stu-id="474e0-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="474e0-127">chronione</span><span class="sxs-lookup"><span data-stu-id="474e0-127">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="474e0-128">wewnętrzny</span><span class="sxs-lookup"><span data-stu-id="474e0-128">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)