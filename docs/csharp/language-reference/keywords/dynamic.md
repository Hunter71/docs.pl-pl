---
title: dynamic (odwołanie w C#)
ms.date: 07/20/2015
f1_keywords:
- dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
ms.openlocfilehash: 59957ce6b2a26c1d24dc1178630eef8551db3340
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="dynamic-c-reference"></a>dynamic (odwołanie w C#)
`dynamic` Typ umożliwia operacje, w których występuje Pomiń sprawdzanie typów w czasie kompilacji. Jednak te operacje zostaną rozwiązane w czasie wykonywania. `dynamic` Typu ułatwiają dostęp do interfejsów API modelu COM, takich jak Office interfejsów API automatyzacji i również do dynamicznego interfejsów API, takich jak biblioteki IronPython oraz do HTML modelu DOM (Document Object).  
  
 Typ `dynamic` zachowuje się jak typ `object` w większości przypadków. Jednak operacje, które zawierają wyrażenia typu `dynamic` nie są rozpoznawane lub typ sprawdzana przez kompilator. Pakiety kompilatora razem informacje na temat operacji, a tych informacji jest później używany do oceny operacji w czasie wykonywania. W trakcie procesu zmiennych typu `dynamic` są kompilowane do zmiennych typu `object`. W związku z tym wpisz `dynamic` istnieje tylko w czasie kompilacji, nie w czasie wykonywania.  
  
 Poniższy przykład zachowanie różni się od zmiennej typu `dynamic` do zmiennej typu `object`. Aby sprawdzić typ każdej zmiennej w czasie kompilacji, umieść wskaźnik myszy nad `dyn` lub `obj` w `WriteLine` instrukcje. Pokazuje IntelliSense **dynamiczne** dla `dyn` i **obiektu** dla `obj`.  
  
 [!code-csharp[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]  
  
 `WriteLine` Instrukcje prezentuje typy środowiska wykonawczego `dyn` i `obj`. W tym momencie mają ten sam typ, liczbę całkowitą. Są następujące wyniki:  
  
 `System.Int32`  
  
 `System.Int32`  
  
 Różnice między `dyn` i `obj` w czasie kompilacji, Dodaj następujące dwa wiersze między deklaracjami i `WriteLine` instrukcje w poprzednim przykładzie.  
  
```csharp  
dyn = dyn + 3;  
obj = obj + 3;  
```  
  
 Błąd kompilatora jest zgłaszany, próba dodania całkowitą i obiektu w wyrażeniu `obj + 3`. Jednak nie będzie zgłaszany błąd dla `dyn + 3`. Wyrażenie, które zawiera `dyn` nie są sprawdzane w czasie kompilacji, ponieważ typ `dyn` jest `dynamic`.  
  
## <a name="context"></a>Kontekst  
 `dynamic` — Słowo kluczowe może występować bezpośrednio lub jako składnik skonstruowanego typu w następujących sytuacjach:  
  
-   W deklaracjach jako typ właściwości, pola, indeksatora, parametr zwracają wartość zmiennej lokalnej lub ograniczenie typu. Następujące klasy używa definicji `dynamic` w kilka różnych deklaracji.  
  
     [!code-csharp[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]  
  
-   Podczas konwersji typu jawnego jako typ docelowy konwersji.  
  
     [!code-csharp[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]  
  
-   W dowolnym kontekście, gdy typy służyć jako wartości, takich jak prawej strony `is` operator lub `as` , operator lub jako argument `typeof` jako część skonstruowanego typu. Na przykład `dynamic` mogą być używane w następujących wyrażeń.  
  
     [!code-csharp[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto `dynamic` w wielu deklaracjach. `Main` Metody różnic między Sprawdzanie typu run-time sprawdzenia typu kompilacji.  
  
 [!code-csharp[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]  
  
 Aby uzyskać dodatkowe informacje i przykłady, zobacz [przy użyciu typu dynamicznego](../../../csharp/programming-guide/types/using-type-dynamic.md).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>  
 <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>  
 [Używanie typu dynamicznego](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [object](../../../csharp/language-reference/keywords/object.md)  
 [is](../../../csharp/language-reference/keywords/is.md)  
 [as](../../../csharp/language-reference/keywords/as.md)  
 [typeof](../../../csharp/language-reference/keywords/typeof.md)  
 [Instrukcje: bezpieczne rzutowanie za pomocą operatorów as i is](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)  
 [Wskazówki: Tworzenie obiektów dynamicznych i posługiwanie](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
