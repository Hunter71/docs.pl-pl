---
title: 'Porady: nasłuchiwanie wielu żądań anulowania'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afa22ed1fe1986712493c2aaa844d7f2c6ffd5bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a>Porady: nasłuchiwanie wielu żądań anulowania
W tym przykładzie przedstawiono sposób słuchać dwa tokeny anulowania jednocześnie tak, aby anulować operację, jeśli albo token żądania.  
  
> [!NOTE]
>  Po włączeniu "Tylko mój kod" programu Visual Studio w niektórych przypadkach będzie podział wiersza, która zgłasza wyjątek i wyświetlony komunikat o błędzie stwierdzający "wyjątek nie obsłużony przez kod użytkownika." Ten błąd jest niegroźne. Naciśnij klawisz F5, aby nadal z niego i zachowanie obsługi wyjątków, które przedstawiono w poniższych przykładach. Aby zapobiec dzieleniu pierwszego błędu w Visual Studio, wystarczy usunąć zaznaczenie pola wyboru "Tylko mój kod" w obszarze **narzędzia, opcje, debugowanie, ogólne**.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> metoda jest używana do przyłączenia dwa tokeny do jednego tokenu. Dzięki temu token mają być przekazane do metody przyjmujących token jako argument tylko jeden anulowania. W przykładzie pokazano typowy scenariusz, w którym metody muszą przestrzegać zarówno token przekazanych z poza klasą a token wygenerowany wewnątrz klasy.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 Gdy generuje token połączony <xref:System.OperationCanceledException>, token, który jest przekazywany do wyjątku jest token połączony, nie albo tokenów poprzednik. Aby ustalić, które tokenów zostało anulowane, sprawdź stan tokenów poprzednik bezpośrednio.  
  
 W tym przykładzie <xref:System.AggregateException> nigdy nie powinien zostać zgłoszony, ale go tutaj zostanie przechwycony ponieważ w rzeczywistych scenariuszach pozostałe wyjątki, oprócz <xref:System.OperationCanceledException> które są generowane z delegat zadań są ujęte w <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>Zobacz też  
 [Anulowanie w zarządzanych wątkach](../../../docs/standard/threading/cancellation-in-managed-threads.md)
