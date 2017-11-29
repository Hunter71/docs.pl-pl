---
title: "Oblicza sumę wartości liczbowych sekwencji"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1735fcd28156b9060c6001eeda6743dfc160d8bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a><span data-ttu-id="56773-102">Oblicza sumę wartości liczbowych sekwencji</span><span class="sxs-lookup"><span data-stu-id="56773-102">Compute the Sum of Values in a Numeric Sequence</span></span>
<span data-ttu-id="56773-103">Użyj <xref:System.Linq.Enumerable.Sum%2A> operatora, aby obliczyć sumę wartości liczbowe w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="56773-103">Use the <xref:System.Linq.Enumerable.Sum%2A> operator to compute the sum of numeric values in a sequence.</span></span>  
  
 <span data-ttu-id="56773-104">Należy zwrócić uwagę na następujące cechy `Sum` operatora w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="56773-104">Note the following characteristics of the `Sum` operator in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
-   <span data-ttu-id="56773-105">Operator zagregowany standardowe — Operator zapytań `Sum` ocenia równą zero dla pustej sekwencji lub sekwencję, która zawiera tylko wartości null.</span><span class="sxs-lookup"><span data-stu-id="56773-105">The Standard Query Operator aggregate operator `Sum` evaluates to zero for an empty sequence or a sequence that contains only nulls.</span></span> <span data-ttu-id="56773-106">W [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], semantykę SQL pozostaną niezmienione.</span><span class="sxs-lookup"><span data-stu-id="56773-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged.</span></span> <span data-ttu-id="56773-107">Z tego powodu `Sum` daje w wyniku wartość null zamiast od zera dla pustej sekwencji lub sekwencję, która zawiera tylko wartości null.</span><span class="sxs-lookup"><span data-stu-id="56773-107">For this reason, `Sum` evaluates to null instead of to zero for an empty sequence or for a sequence that contains only nulls.</span></span>  
  
-   <span data-ttu-id="56773-108">Ograniczenia SQL pośrednich wyników dotyczą wartości zagregowanych w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56773-108">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="56773-109">Sumę ilości 32-bitową liczbę całkowitą nie jest obliczana przy użyciu 64-bitowych wyników i mogą być przepełnienie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tłumaczenie `Sum`.</span><span class="sxs-lookup"><span data-stu-id="56773-109">Sum of 32-bit integer quantities is not computed by using 64-bit results, and overflow can occur for the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of `Sum`.</span></span> <span data-ttu-id="56773-110">Istnieje taka możliwość, nawet jeśli implementacja standardowe — Operator zapytań nie spowoduje przepełnienie w odpowiedniej sekwencji w pamięci.</span><span class="sxs-lookup"><span data-stu-id="56773-110">This possibility exists even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56773-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="56773-111">Example</span></span>  
 <span data-ttu-id="56773-112">Poniższy przykład umożliwia znalezienie całkowita transport wszystkich zamówień w `Order` tabeli.</span><span class="sxs-lookup"><span data-stu-id="56773-112">The following example finds the total freight of all orders in the `Order` table.</span></span>  
  
 <span data-ttu-id="56773-113">Po uruchomieniu tego zapytania względem przykładowej bazy danych Northwind, dane wyjściowe są: `64942.6900`.</span><span class="sxs-lookup"><span data-stu-id="56773-113">If you run this query against the Northwind sample database, the output is: `64942.6900`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="56773-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="56773-114">Example</span></span>  
 <span data-ttu-id="56773-115">Poniższy przykład umożliwia znalezienie łączna liczba jednostek w kolejności dla wszystkich produktów.</span><span class="sxs-lookup"><span data-stu-id="56773-115">The following example finds the total number of units on order for all products.</span></span>  
  
 <span data-ttu-id="56773-116">Po uruchomieniu tego zapytania względem przykładowej bazy danych Northwind, dane wyjściowe są: `780`.</span><span class="sxs-lookup"><span data-stu-id="56773-116">If you run this query against the Northwind sample database, the output is: `780`.</span></span>  
  
 <span data-ttu-id="56773-117">Należy pamiętać, że należy rzutować `short` typów (na przykład `UnitsOnOrder`) ponieważ `Sum` ma żadna metoda przeciążenia krótkich typów.</span><span class="sxs-lookup"><span data-stu-id="56773-117">Note that you must cast `short` types (for example, `UnitsOnOrder`) because `Sum` has no overload for short types.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="56773-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="56773-118">See Also</span></span>  
 [<span data-ttu-id="56773-119">Zapytania zagregowane</span><span class="sxs-lookup"><span data-stu-id="56773-119">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="56773-120">Pobieranie przykładowych baz danych</span><span class="sxs-lookup"><span data-stu-id="56773-120">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)