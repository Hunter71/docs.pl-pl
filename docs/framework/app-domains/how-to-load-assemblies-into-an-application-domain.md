---
title: "Porady: ładowanie zestawów do domeny aplikacji"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90e1d16b47e1f603ac7faaa582388ec682591850
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-assemblies-into-an-application-domain"></a>Porady: ładowanie zestawów do domeny aplikacji
Istnieje kilka sposobów, aby załadować zestawu do domeny aplikacji. Zalecaną metodą jest użycie `static` (`Shared` w języku Visual Basic) <xref:System.Reflection.Assembly.Load%2A> metody <xref:System.Reflection.Assembly?displayProperty=nameWithType> klasy. Inne metody, które zestawy można załadować to:  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A> Metody <xref:System.Reflection.Assembly> klasy ładuje zestaw podanej lokalizacji pliku. Ładowanie zestawów przy użyciu tej metody używa kontekstu różne obciążenia.  
  
-   <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> i <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> metody załadowania zestawu do kontekstu reflection-only. Zestawy ładowane w tym kontekście można zbadać, ale nie zostanie wykonane, dzięki czemu badania zestawy, które odnoszą się do innych platform. Zobacz [porady: ładowanie zestawów do kontekstu Reflection-Only](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
> [!NOTE]
>  Kontekstu reflection-only jest nowa w programie .NET Framework w wersji 2.0.  
  
-   Metody, takie jak <xref:System.AppDomain.CreateInstance%2A> i <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> z <xref:System.AppDomain> klasy można załadować zestawów do domeny aplikacji.  
  
-   <xref:System.Type.GetType%2A> Metody <xref:System.Type> klasy można ładować zestawów.  
  
-   <xref:System.AppDomain.Load%2A> Metody <xref:System.AppDomain?displayProperty=nameWithType> klasy można ładować zestawów, ale jest używany głównie dla współdziałanie COM. Nie można stosować ładowanie zestawów do domeny aplikacji innych niż domena aplikacji, z którego jest wywoływana.  
  
> [!NOTE]
>  W programie .NET Framework w wersji 2.0, środowisko uruchomieniowe nie zostanie załadowany zestaw, który został skompilowany przy użyciu wersji programu .NET Framework, która ma wyższy numer wersji niż aktualnie załadowany. Dotyczy to kombinacja główne i pomocnicze składniki numeru wersji.  
  
 Można określić sposób just-in-time (JIT) skompilowany kod z zestawów załadowanych jest udostępniana między domenami aplikacji. Aby uzyskać więcej informacji, zobacz [zestawów i domen aplikacji](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346).  
  
## <a name="example"></a>Przykład  
 Następujące obciążenia kod pobiera zestawu o nazwie "example.exe" lub "example.dll" do bieżącej domeny aplikacji typu o nazwie `Example` z zestawu, pobiera bez parametrów metodę o nazwie `MethodA` wpisz i wykonuje metodę. Pełne omówienie na uzyskiwanie informacji z załadować zestawu, zobacz [dynamiczne ładowanie i przy użyciu typów](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>  
 [Programowanie za pomocą domeny aplikacji](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [Odbicie](../../../docs/framework/reflection-and-codedom/reflection.md)  
 [Używanie domeny aplikacji](../../../docs/framework/app-domains/use.md)  
 [Porady: ładowanie zestawów do kontekstu Reflection-Only](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)  
 [Zestawów i domen aplikacji](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)