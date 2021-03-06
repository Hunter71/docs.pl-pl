---
title: true — Operator (odwołanie w C#)
ms.date: 07/20/2015
helpviewer_keywords:
- true operator [C#]
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
ms.openlocfilehash: 71f522b3860f7461f5c52dd77bb424f7ba0f9bf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="true-operator-c-reference"></a>true — Operator (odwołanie w C#)
Zwraca [bool](../../../csharp/language-reference/keywords/bool.md) wartość `true` aby wskazać, że argument ma wartość PRAWDA i zwraca `false` inaczej.  
  
 Przed C# 2.0 `true` i `false` operatory były używane do tworzenia typów zdefiniowanych przez użytkownika wartości null, które były zgodne z typami, takich jak `SqlBool`. Jednak język teraz udostępnia wbudowaną obsługę dla typów wartości null, a w miarę możliwości należy używać tych zamiast przeładowanie `true` i `false` operatorów. Aby uzyskać więcej informacji, zobacz [typy dopuszczające wartości zerowe](../../../csharp/programming-guide/nullable-types/index.md).  
  
 O wartości null wartości logiczne, wyrażenie `a != b` nie jest zawsze równa `!(a == b)` ponieważ jedną lub obie wartości może mieć wartości null. Musisz przeciążenia obu `true` i `false` operatory oddzielnie, aby wykryć wartości null w wyrażeniu. Poniższy przykład przedstawia sposób przeciążenia i użyj `true` i `false` operatorów.  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]  
  
 Typ, który overloads `true` i `false` operatorów można używać do kontrolowania wyrażenie w [Jeśli](../../../csharp/language-reference/keywords/if-else.md), [czy](../../../csharp/language-reference/keywords/do.md), [podczas](../../../csharp/language-reference/keywords/while.md), i [ Aby uzyskać](../../../csharp/language-reference/keywords/for.md) instrukcje i [wyrażenia warunkowe](../../../csharp/language-reference/operators/conditional-operator.md).  
  
 Jeśli typ definiuje operator `true`, również muszą definiować operator [false](../../../csharp/language-reference/keywords/false.md).  
  
 Typem bezpośrednio nie mogą przeciążać operatory logiczne warunkowe ([ && ](../../../csharp/language-reference/operators/conditional-and-operator.md) i [ &#124; &#124; ](../../../csharp/language-reference/operators/conditional-or-operator.md)), ale sam efekt można osiągnąć przez przeładowanie zwykłej logiczne operatory i operatory `true` i `false`.  
  
## <a name="c-language-specification"></a>Specyfikacja języka C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie w C#](../../../csharp/language-reference/index.md)  
 [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
 [Słowa kluczowe języka C#](../../../csharp/language-reference/keywords/index.md)  
 [Operatory języka C#](../../../csharp/language-reference/operators/index.md)  
 [false](../../../csharp/language-reference/keywords/false.md)
