---
title: dirtyCastAndCallOnInterface MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5c54b8c2600dca1c7b24ac663a6ed506ca8ef24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="dirtycastandcalloninterface-mda"></a>dirtyCastAndCallOnInterface MDA
`dirtyCastAndCallOnInterface` Zarządzany Asystent debugowania (MDA) jest aktywowany, gdy w interfejsie klasy, która została oznaczona jako późnym wiązaniem tylko podejmowane są próby wywołania z wczesnym wiązaniem vtable.  
  
## <a name="symptoms"></a>Symptomy  
 Aplikacja zgłasza naruszenie zasad dostępu lub ma nieoczekiwanego zachowania podczas umieszczania wywołania z wczesnym wiązaniem za pośrednictwem modelu COM do środowiska CLR.  
  
## <a name="cause"></a>Przyczyna  
 Kod jest próba wywołania z wczesnym wiązaniem vtable za pośrednictwem interfejsu klasy, które są tylko późnym wiązaniem. Należy pamiętać, że przez domyślną klasę interfejsy są identyfikowane jako trwa późnym wiązaniem tylko. Można również zidentyfikować je jako późnym wiązaniem z <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atrybutem <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> wartość (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).  
  
## <a name="resolution"></a>Rozwiązanie  
 Zalecane rozwiązanie jest zdefiniować jawnego interfejsu do użycia przez model COM, a wywołania klientów modelu COM za pośrednictwem tego interfejsu zamiast za pomocą interfejsu automatycznie wygenerowana klasa. Alternatywnie wywołania z modelu COM może służyć za pośrednictwem wywołania późnym wiązaniem `IDispatch`.  
  
 Ponadto istnieje możliwość identyfikowania klasy jako <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) umożliwia wywołania z wczesnym wiązaniem do umieszczenia z modelu COM; jednak za pomocą <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> jest zalecane z powodu ograniczeń versioning opisanego w <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  
 To zdarzenie MDA nie ma wpływu na środowisko CLR. Zwraca tylko dane o wywołania z wczesnym wiązaniem dla interfejsów z późnym wiązaniem.  
  
## <a name="output"></a>Dane wyjściowe  
 Nazwa metody lub nazwę pola, do której uzyskuje dostęp z wczesnym wiązaniem.  
  
## <a name="configuration"></a>Konfiguracja  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>  
 [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
