---
title: -docelowego (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /target
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
ms.openlocfilehash: 7736b8850a7b09f7212e83e05acf0e1994bce0fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="-target-c-compiler-options"></a>-docelowego (opcje kompilatora C#)
**-Docelowy** — opcja kompilatora można określić w jednym z czterech formularzy:  
  
 [-target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 Aby utworzyć plik .exe [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] aplikacji.  
  
 [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 Aby utworzyć plik .exe.  
  
 [-target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 Aby utworzyć biblioteki kodu.  
  
 [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 Aby utworzyć moduł.  
  
 [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 Aby utworzyć program systemu Windows.  
  
 [-target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 Aby utworzyć plik pośredni .winmdobj.  
  
 Chyba że zostanie **-docelowych: moduł**, **-docelowy** powoduje, że manifestu zestawu .NET Framework do umieszczenia w pliku wyjściowym. Aby uzyskać więcej informacji, zobacz [zestawy w środowisku uruchomieniowym języka](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md) i [takie same atrybuty wspólne](../../programming-guide/concepts/attributes/common-attributes.md).  
  
 Manifest zestawu jest umieszczany w pierwszym pliku wyjściowego .exe w kompilacji lub w pierwszej biblioteki DLL, jeśli plik wyjściowy .exe nie istnieje. Na przykład, w wierszu polecenia następujący plik manifestu zostaną umieszczone w `1.exe`:  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 Kompilator tworzy tylko jeden manifest zestawu kompilacji. Informacje o wszystkich plików w kompilacji jest umieszczany w manifeście zestawu. Wszystkie pliki z wyjątkiem tych, utworzone za pomocą wyjściowe **-docelowych: moduł** może zawierać manifest zestawu. Podczas produkowania wielu plików wyjściowych w wierszu polecenia, można utworzyć tylko jeden zestaw manifestu i należy przejść do pierwszego pliku wyjściowego, określona w wierszu polecenia. Niezależnie od tego, jakie pierwszy plik wyjściowy jest (**-docelowych: exe**, **-docelowych: winexe**, **— docelowa: Biblioteka** lub **-docelowych: moduł**) wszystkie inne pliki wyjściowe wygenerowane w tej samej kompilacji musi być modułów (**-docelowych: moduł**).  
  
 W przypadku utworzenia zestawu, może oznaczać, że całość lub część kodu jest zgodny ze specyfikacją CLS <xref:System.CLSCompliantAttribute> atrybutu.  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 Aby uzyskać więcej informacji na temat ustawiania tej opcji kompilatora programowo, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="see-also"></a>Zobacz też  
 [Opcje kompilatora C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Zarządzanie właściwościami projektu i rozwiązania](/visualstudio/ide/managing-project-and-solution-properties)  
 [-subsystemversion (opcje kompilatora C#)](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)
