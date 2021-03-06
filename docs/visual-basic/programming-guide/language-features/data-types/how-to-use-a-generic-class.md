---
title: 'Porady: używanie klasy ogólnej (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters [Visual Basic], data type
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
ms.openlocfilehash: adea9f7e7dbbc2317e5b857a5153e3ec67d63344
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-generic-class-visual-basic"></a>Porady: używanie klasy ogólnej (Visual Basic)
Klasa, która przyjmuje *parametry typu* jest nazywany *klasy ogólnej*. Jeśli korzystasz z klasy ogólnej, można wygenerować *skonstruowany klasy* z niego podając *argument typu* dla każdego z tych parametrów. Następnie można zadeklarować zmiennej typu klasy utworzone i może utworzyć wystąpienia klasy skonstruowane i przypisz je do tej zmiennej.  
  
 Oprócz klas można również zdefiniować i używać struktury ogólne, interfejsów, procedury i delegatów.  
  
 Poniższa procedura ma klasy ogólnej zdefiniowane w [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] i tworzy wystąpienie z niego.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Aby użyć klasy, która przyjmuje parametr typu  
  
1.  Na początku pliku źródłowego, obejmują [Importy — instrukcja (.NET Namespace i Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) do zaimportowania <xref:System.Collections.Generic?displayProperty=nameWithType> przestrzeni nazw. Dzięki temu można odwoływać się do <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> klasy bez konieczności pełnej kwalifikacji go w odróżnieniu od innych klas kolejki takich jak <xref:System.Collections.Queue?displayProperty=nameWithType>.  
  
2.  Utwórz obiekt w zwykły sposób, ale Dodaj `(Of` `type``)` natychmiast po nazwie klasy.  
  
     W poniższym przykładzie użyto tej samej klasy (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) można utworzyć dwa obiekty kolejki zawierających elementy różnych typów danych. Dodaje elementy na końcu każdej kolejki, a następnie usuwa i wyświetla elementy z na początku każdej kolejki.  
  
     [!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a>Zobacz też  
 [Typy danych](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Typy ogólne w Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Niezależność od języka i składniki niezależne od języka](../../../../standard/language-independence-and-language-independent-components.md)  
 [z](../../../../visual-basic/language-reference/statements/of-clause.md)  
 [Imports, instrukcja (przestrzeń nazw i typ .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Instrukcje: definiowanie klasy, która może zapewnić identyczną funkcjonalność różnych typów danych](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [Iteratory](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)
