---
title: /reference (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f8c6851802afa818cc80b3f6d7eafc2ef47ac689
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="reference-visual-basic"></a><span data-ttu-id="1b2bc-102">/reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b2bc-102">/reference (Visual Basic)</span></span>
<span data-ttu-id="1b2bc-103">Powoduje, że kompilator, aby udostępnić informacje o typie w określonych zestawów do projektu, które są aktualnie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b2bc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1b2bc-104">Syntax</span></span>  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="1b2bc-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="1b2bc-105">Arguments</span></span>  
  
|<span data-ttu-id="1b2bc-106">Termin</span><span class="sxs-lookup"><span data-stu-id="1b2bc-106">Term</span></span>|<span data-ttu-id="1b2bc-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="1b2bc-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="1b2bc-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-108">Required.</span></span> <span data-ttu-id="1b2bc-109">Rozdzielana przecinkami lista nazw plików zestawu.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="1b2bc-110">Jeśli nazwa pliku zawiera spację, nazwę należy ująć w cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b2bc-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1b2bc-111">Remarks</span></span>  
 <span data-ttu-id="1b2bc-112">Pliki, które należy zaimportować musi zawierać metadane zestawu.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="1b2bc-113">Tylko typy publiczne są widoczne poza zestaw.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="1b2bc-114">[/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opcja importuje metadane z modułu.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="1b2bc-115">Jeśli odwołanie do zestawu (zestawów A) które odwołuje się do innego zestawu (zestaw B), należy odwołanie do zestawu B, jeśli:</span><span class="sxs-lookup"><span data-stu-id="1b2bc-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="1b2bc-116">Typ z zestawu A dziedziczy z typu lub implementuje interfejs z zestawu B.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="1b2bc-117">Pola, właściwości, zdarzenia lub metodę, która ma zwracany typ lub parametr typu z B zestawu jest wywoływany.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="1b2bc-118">Użyj [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) Aby określić katalog, w którym znajduje się co najmniej jednego odwołania do zestawów.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-118">Use [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="1b2bc-119">Dla kompilatora do rozpoznawania typu w zestawie (nie w module) należy wymusić można rozpoznać typu.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="1b2bc-120">Definiowanie wystąpienia typu jest przykładem jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="1b2bc-121">Inne metody są dostępne do rozpoznania nazwy typów w zestawie dla kompilatora.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="1b2bc-122">Na przykład jeśli można dziedziczyć po typie w zestawie, nazwa typu następnie staje się znane do kompilatora.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="1b2bc-123">Vbc.rsp plik odpowiedzi, który odwołuje się do najczęściej używanych [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] zestawy, jest używany domyślnie.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="1b2bc-124">Użyj `/noconfig` Jeśli nie chcesz, aby kompilator, aby używał Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-124">Use `/noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="1b2bc-125">Krótka forma z `/reference` jest `/r`.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-125">The short form of `/reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b2bc-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="1b2bc-126">Example</span></span>  
 <span data-ttu-id="1b2bc-127">Poniższy kod tworzy plik źródłowy `Input.vb` i odwołuje się do zestawów z `Metad1.dll` i `Metad2.dll` do produkcji `Out.exe`.</span><span class="sxs-lookup"><span data-stu-id="1b2bc-127">The following code compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b2bc-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1b2bc-128">See Also</span></span>  
 [<span data-ttu-id="1b2bc-129">Kompilator w wierszu polecenia programu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b2bc-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1b2bc-130">/ noconfig</span><span class="sxs-lookup"><span data-stu-id="1b2bc-130">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="1b2bc-131">/ TARGET (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b2bc-131">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="1b2bc-132">Publiczna</span><span class="sxs-lookup"><span data-stu-id="1b2bc-132">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="1b2bc-133">Kompilacja przykładów — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="1b2bc-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)