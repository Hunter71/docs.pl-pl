---
title: "Zestawy i wykonywanie równoczesne"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d0f5e5d0e9a2385d3ebf1c2f1dc7838de79b27e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="assemblies-and-side-by-side-execution"></a>Zestawy i wykonywanie równoczesne
Wykonanie Side-by-side jest możliwość przechowywania i wykonywanie wielu wersji aplikacji lub składnika na tym samym komputerze. Oznacza to, że może mieć wiele wersji środowiska uruchomieniowego i wiele wersji aplikacji i składników, których używana jest wersja środowiska uruchomieniowego, na tym samym komputerze, w tym samym czasie. Wykonanie Side-by-side zapewnia większą kontrolę nad jakich wersji składnika aplikacji wiąże i większą kontrolę nad którą wersję środowiska uruchomieniowego aplikacji używane.  
  
 Obsługa magazynu side-by-side i wykonywania różnych wersji tego samego zestawu jest integralną częścią silne nazwy i jest wbudowana w infrastrukturze środowiska uruchomieniowego. Ponieważ numer wersji zestawu o silnej nazwie jest częścią jego tożsamość, środowisko uruchomieniowe można przechowywać wiele wersji tego samego zestawu w pamięci podręcznej GAC i ładowanie tych zestawów w czasie wykonywania.  
  
 Mimo że środowisko uruchomieniowe umożliwia tworzenie aplikacji side-by-side, wykonanie side-by-side nie jest automatyczna. Aby uzyskać więcej informacji na temat tworzenia aplikacji dla wykonywania side-by-side, zobacz [wytyczne dotyczące tworzenia składników do wykonania Side-by-Side](../../../docs/framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Jak lokalizuje zestawów przez środowisko uruchomieniowe](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Zestawy w środowisko uruchomieniowe języka wspólnego](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)