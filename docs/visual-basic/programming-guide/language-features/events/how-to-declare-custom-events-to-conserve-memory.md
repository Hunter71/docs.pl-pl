---
title: 'Porady: deklarowanie zdarzeń niestandardowych w celu zachowywania pamięci (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: d19c91d66e458ca2317dc049d517b92fa7406ef6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Porady: deklarowanie zdarzeń niestandardowych w celu zachowywania pamięci (Visual Basic)
Istnieje kilka okoliczności podczas należy pamiętać, że aplikacja zachować jego użycie pamięci niski. Zdarzeń niestandardowych Zezwalaj aplikacji na używanie pamięci tylko dla zdarzeń, które obsługuje on.  
  
 Domyślnie po klasie deklaruje zdarzenia, kompilator przydziela pamięć dla pola do przechowywania informacji o zdarzeniu. Jeśli klasa zawiera wiele zdarzeń nieużywanych, niepotrzebnie zajmują pamięć.  
  
 Zamiast Domyślna implementacja zdarzeń, które zapewnia Visual Basic zdarzeń niestandardowych służy do zarządzania bardziej dokładnie zużycie pamięci.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie klasa korzysta z jednego wystąpienia <xref:System.ComponentModel.EventHandlerList> klasy przechowywane w `Events` pola do przechowywania informacji o zdarzeniach w użyciu. <xref:System.ComponentModel.EventHandlerList> Klasa jest klasą zoptymalizowane listy przeznaczony do przechowywania obiektów delegowanych.  
  
 Wszystkie zdarzenia w przypadku użycia klasy `Events` pola do śledzenia metod są obsługi każdego zdarzenia.  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ComponentModel.EventHandlerList>  
 [Zdarzenia](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Instrukcje: deklarowanie zdarzeń niestandardowych w celu unikania blokowania](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
