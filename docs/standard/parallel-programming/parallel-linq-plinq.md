---
title: Równoległe LINQ (PLINQ)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ, overview
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccd30ee987fbc4ad75008a28c030c4f44a2368dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="parallel-linq-plinq"></a>Równoległe LINQ (PLINQ)
Równoległe LINQ (PLINQ) to implementacja równoległe LINQ do obiektów. PLINQ implementuje pełnego zestawu LINQ standardowych operatorów zapytań jako metody rozszerzenia dla <xref:System.Linq> przestrzeni nazw i ma dodatkowe operatory dla operacji równoległych. PLINQ łączy prostotę i czytelność składni LINQ dzięki możliwościom Programowanie równoległe. Podobnie jak kod którego element docelowy Biblioteka zadań równoległych, zapytania dotyczące technologii PLINQ skalować stopień współbieżności oparta na funkcjach komputera-hosta.  
  
 W wielu scenariuszach PLINQ może znacznie zwiększyć szybkość LINQ do obiektów zapytania przy użyciu wszystkie dostępne rdzenie wydajniej na komputerze hosta. To zwiększenie wydajności zapewnia wysoką wydajność mocy obliczeniowej na pulpit.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Wprowadzenie do PLINQ](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [Ogólne informacje o przyspieszeniach w PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [Zachowywanie kolejności w PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [Opcje scalania w PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [Instrukcje: tworzenie i wykonywanie prostego zapytania PLINQ](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [Instrukcje: sterowanie szeregowaniem w zapytaniu PLINQ](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [Instrukcje: łączenie równoległych i sekwencyjnych zapytań LINQ](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [Instrukcje: obsługa wyjątków w zapytaniu PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [Instrukcje: anulowanie zapytania PLINQ](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [Instrukcje: pisanie niestandardowej funkcji agregowania w PLINQ](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [Instrukcje: określanie trybu wykonywania w PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [Instrukcje: określanie opcji scalania w PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [Instrukcje: iteracja katalogów plików przy użyciu technologii PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [Instrukcje: mierzenie wydajności zapytań PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [Próbka danych PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Linq.ParallelEnumerable>  
 [Programowanie równoległe](../../../docs/standard/parallel-programming/index.md)  
 [LINQ (zapytania o języku zintegrowanym)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
