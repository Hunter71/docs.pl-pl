---
title: 'Porady: wywoływanie procedury właściwości (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 61d79b9ff99ec144a9c629872abd2a7e7ebda4d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Porady: wywoływanie procedury właściwości (Visual Basic)
Przechowywanie wartości we właściwości lub pobierania jej wartość jest wywoływanie procedury właściwości. Dostępu do właściwości taki sam sposób, dostęp do zmiennej.  
  
 Właściwość `Set` procedury przechowuje wartość, a jego `Get` procedury pobiera wartość. Jednak nie zostanie jawnie wywołana procedury te według nazwy. Możesz użyć właściwości w instrukcji przypisania lub wyrażenie, tak samo, jak będzie przechowywać lub pobrać wartości zmiennej. Visual Basic wywołań procedur właściwości.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Aby wywołać procedura Get właściwości  
  
1.  Użyj nazwy właściwości w wyrażeniu taki sam sposób, należy użyć nazwy zmiennej. Można użyć właściwości dowolnym można użyć zmiennej lub stałą.  
  
     —lub—  
  
     Użyj nazwy właściwości po równości (`=`) Zaloguj się w instrukcji przypisania.  
  
     Poniższy przykład odczytuje wartość <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> właściwości niejawnie wywoływanie jej `Get` procedury.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Jeśli właściwość przyjmuje argumenty, wykonaj nazwa właściwości w nawiasach należy ująć listy argumentów. Jeśli nie ma żadnych argumentów, opcjonalnie można pominąć nawiasów.  
  
3.  Umieść listy argumentów w nawiasie rozdzielone przecinkami argumenty. Upewnij się, że podać argumenty w tej samej kolejności, że właściwość definiuje odpowiednich parametrów.  
  
 Wartość właściwości uczestniczy w wyrażeniu tylko jako zmienną czy stałą lub jest ona przechowywana w zmiennej lub właściwości po lewej stronie instrukcji przypisania.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Wywoływanie właściwości ustawione przez procedury  
  
1.  Po lewej stronie instrukcji przypisania, należy użyć nazwy właściwości.  
  
     W poniższym przykładzie ustawiono wartość <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> właściwości niejawnie wywoływania `Set` procedury.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Jeśli właściwość przyjmuje argumenty, wykonaj nazwa właściwości w nawiasach należy ująć listy argumentów. Jeśli nie ma żadnych argumentów, opcjonalnie można pominąć nawiasów.  
  
3.  Umieść listy argumentów w nawiasie rozdzielone przecinkami argumenty. Upewnij się, że podać argumenty w tej samej kolejności, że właściwość definiuje odpowiednich parametrów.  
  
 Generowane po prawej stronie instrukcji przypisania wartość jest przechowywana we właściwości.  
  
## <a name="see-also"></a>Zobacz też  
 [Procedury właściwości](./property-procedures.md)  
 [Parametry i argumenty procedur](./procedure-parameters-and-arguments.md)  
 [Property, instrukcja](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Różnice pomiędzy właściwościami i zmiennymi w Visual Basic](./differences-between-properties-and-variables.md)  
 [Instrukcje: tworzenie właściwości](./how-to-create-a-property.md)  
 [Instrukcje: deklarowanie właściwości z mieszanymi poziomami dostępu](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Porady: deklarowanie i wywoływanie w właściwości domyślnej w Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Instrukcje: umieszczanie wartości we właściwości](./how-to-put-a-value-in-a-property.md)  
 [Instrukcje: pobieranie wartości z właściwości](./how-to-get-a-value-from-a-property.md)  
 [Get, instrukcja](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set, instrukcja](../../../../visual-basic/language-reference/statements/set-statement.md)
