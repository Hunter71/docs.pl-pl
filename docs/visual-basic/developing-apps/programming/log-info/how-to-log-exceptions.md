---
title: 'Porady: wyjątki rejestru w Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: b8ec45f43438f8181d9e045cdf43c81db34e4242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-log-exceptions-in-visual-basic"></a>Porady: wyjątki rejestru w Visual Basic
Można użyć `My.Application.Log` i `My.Log` obiektów do rejestrowania informacji o wyjątków, które występują w aplikacji. Poniższe przykłady pokazują, jak użyć `My.Application.Log.WriteException` metody do rejestrowania wyjątków, które zostaną jawnie wychwycone i wyjątków, które są nieobsługiwane.  
  
 Rejestrowanie informacji śledzenia, użyj `My.Application.Log.WriteEntry` metody. Aby uzyskać więcej informacji zobacz <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
  
### <a name="to-log-a-handled-exception"></a>Aby rejestrować obsłużył wyjątek  
  
1.  Tworzenie metody, która będzie generować informacje o wyjątku.  
  
     [!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]  
  
2.  Użyj `Try...Catch` bloku catch wyjątku.  
  
     [!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]  
  
3.  Umieść kod, który można wygenerować wyjątek `Try` bloku.  
  
     Usuń znaczniki komentarza `Dim` i `MsgBox` wiersze spowodują <xref:System.NullReferenceException> wyjątku.  
  
     [!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]  
  
4.  W `Catch` bloków, użyj `My.Application.Log.WriteException` metodę, aby zapisać informacje o wyjątku.  
  
     [!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]  
  
     Poniższy przykład przedstawia kompletny kod dla rejestrowania obsłużył wyjątek.  
  
     [!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]  
  
### <a name="to-log-an-unhandled-exception"></a>Wystąpił nieobsługiwany wyjątek logowania  
  
1.  Projekt wybrany w **Eksploratora rozwiązań**. Na **projektu** menu, wybierz **właściwości**.  
  
2.  Kliknij przycisk **aplikacji** kartę.  
  
3.  Kliknij przycisk **Wyświetl zdarzenia aplikacji** przycisk, aby otworzyć edytora kodu.  
  
     Spowoduje to otwarcie pliku ApplicationEvents.vb.  
  
4.  ApplicationEvents.vb plik zostać otwarty w edytorze kodu. Na **ogólne** menu, wybierz **zdarzenia moja_aplikacja**.  
  
5.  Na **deklaracje** menu, wybierz **UnhandledException**.  
  
     Generuje aplikacji <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> zdarzeń przed uruchomieniem aplikacji głównej.  
  
6.  Dodaj `My.Application.Log.WriteException` metodę `UnhandledException` obsługi zdarzeń.  
  
     [!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]  
  
     Poniższy przykład przedstawia kompletny kod dla rejestrowania nieobsługiwany wyjątek.  
  
     [!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [Praca z dziennikami aplikacji](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [Instrukcje: zapisywanie komunikatów dziennika](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)  
 [Przewodnik: ustalanie, gdzie My.Application.Log zapisuje informacje](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 [Przewodnik: zmienianie lokalizacji, w której My.Application.Log zapisuje informacje](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
