---
title: "&lt;provideroption —&gt; — Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
caps.latest.revision: "22"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3a01a64ab8828104e8404f7d4efdd7b37eea373e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltprovideroptiongt-element"></a><span data-ttu-id="49aa7-102">&lt;provideroption —&gt; — Element</span><span class="sxs-lookup"><span data-stu-id="49aa7-102">&lt;providerOption&gt; Element</span></span>
<span data-ttu-id="49aa7-103">Określa atrybuty wersji kompilatora dla dostawcy języka.</span><span class="sxs-lookup"><span data-stu-id="49aa7-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="49aa7-104">\<Element konfiguracji ></span><span class="sxs-lookup"><span data-stu-id="49aa7-104">\<configuration Element></span></span>  
<span data-ttu-id="49aa7-105">\<System.CodeDom — Element ></span><span class="sxs-lookup"><span data-stu-id="49aa7-105">\<system.codedom Element></span></span>  
<span data-ttu-id="49aa7-106">\<Element kompilatorów ></span><span class="sxs-lookup"><span data-stu-id="49aa7-106">\<compilers Element></span></span>  
<span data-ttu-id="49aa7-107">\<Kompilator > — Element</span><span class="sxs-lookup"><span data-stu-id="49aa7-107">\<compiler> Element</span></span>  
<span data-ttu-id="49aa7-108">\<provideroption — > — Element</span><span class="sxs-lookup"><span data-stu-id="49aa7-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49aa7-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="49aa7-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49aa7-110">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="49aa7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="49aa7-111">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="49aa7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49aa7-112">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="49aa7-112">Attributes</span></span>  
  
|<span data-ttu-id="49aa7-113">Atrybut</span><span class="sxs-lookup"><span data-stu-id="49aa7-113">Attribute</span></span>|<span data-ttu-id="49aa7-114">Opis</span><span class="sxs-lookup"><span data-stu-id="49aa7-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="49aa7-115">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="49aa7-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="49aa7-116">Określa nazwę opcji; na przykład "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="49aa7-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="49aa7-117">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="49aa7-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="49aa7-118">Określa wartość opcji; na przykład "v3.5".</span><span class="sxs-lookup"><span data-stu-id="49aa7-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49aa7-119">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="49aa7-119">Child Elements</span></span>  
 <span data-ttu-id="49aa7-120">Brak.</span><span class="sxs-lookup"><span data-stu-id="49aa7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="49aa7-121">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="49aa7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="49aa7-122">Element</span><span class="sxs-lookup"><span data-stu-id="49aa7-122">Element</span></span>|<span data-ttu-id="49aa7-123">Opis</span><span class="sxs-lookup"><span data-stu-id="49aa7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49aa7-124">\<Konfiguracja > — Element</span><span class="sxs-lookup"><span data-stu-id="49aa7-124">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="49aa7-125">Element główny w każdym pliku konfiguracyjnym, który jest używany przez środowisko uruchomieniowe języka wspólnego i aplikacji programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="49aa7-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="49aa7-126">\<System.CodeDom — > — Element</span><span class="sxs-lookup"><span data-stu-id="49aa7-126">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="49aa7-127">Określa ustawienia kompilatora konfiguracji dla dostawcy dostępnych języków.</span><span class="sxs-lookup"><span data-stu-id="49aa7-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="49aa7-128">\<kompilatory > — Element</span><span class="sxs-lookup"><span data-stu-id="49aa7-128">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="49aa7-129">Kontener dla elementy kompilatora konfiguracji; zawiera zero lub więcej `<compiler>` elementów.</span><span class="sxs-lookup"><span data-stu-id="49aa7-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="49aa7-130">\<Kompilator > — Element</span><span class="sxs-lookup"><span data-stu-id="49aa7-130">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="49aa7-131">Określa atrybuty kompilatora konfiguracji dostawcy języka.</span><span class="sxs-lookup"><span data-stu-id="49aa7-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49aa7-132">Uwagi</span><span class="sxs-lookup"><span data-stu-id="49aa7-132">Remarks</span></span>  
 <span data-ttu-id="49aa7-133">W programie .NET Framework w wersji 3.5, dostawców kodu kodu Document Object Model (CodeDOM) może obsługiwać opcji specyficznych dla dostawcy przy użyciu `<providerOption>` elementu.</span><span class="sxs-lookup"><span data-stu-id="49aa7-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="49aa7-134">.NET Framework 3.5 zawiera zaktualizowane zestawy .NET Framework 2.0 i udostępnia nowe zestawy w wersji 3.5, które zawiera nowe typy.</span><span class="sxs-lookup"><span data-stu-id="49aa7-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="49aa7-135">Dostawcy kodu języka Microsoft C# i Visual Basic są zawarte w zestawach .NET Framework 2.0, ale zostały zaktualizowane do obsługi kompilatory w wersji 3.5.</span><span class="sxs-lookup"><span data-stu-id="49aa7-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="49aa7-136">Domyślnie dostawców zaktualizowanego kodu wygenerować kod dla kompilatory w wersji 2.0.</span><span class="sxs-lookup"><span data-stu-id="49aa7-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="49aa7-137">Można użyć `<providerOption>` element, aby zmienić docelową wersję kompilatora 3.5.</span><span class="sxs-lookup"><span data-stu-id="49aa7-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="49aa7-138">Aby to zrobić, należy określić "CompilerVersion" `name` oraz "v3.5" dla atrybutu `value` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="49aa7-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="49aa7-139">Należy poprzedzić numer wersji, z małymi literami "v".</span><span class="sxs-lookup"><span data-stu-id="49aa7-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="49aa7-140">Możesz wprowadzić Specyfikacja wersji globalnej, dodając `<providerOption>` elementu .NET Framework 2.0 w pliku Machine.config lub głównym pliku Web.config.</span><span class="sxs-lookup"><span data-stu-id="49aa7-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="49aa7-141">Po zaktualizowaniu domyślnej wersji kompilatora 3.5 w pliku Machine.config, można zmienić go do 2.0 na poszczególnych aplikacji, co przy użyciu `<providerOption>` elementu w pliku konfiguracyjnym aplikacji.</span><span class="sxs-lookup"><span data-stu-id="49aa7-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="49aa7-142">Implementacje dostawcy kodu codeDOM może przetwarzać niestandardowych opcji zapewniając konstruktora przyjmującego `providerOptions` parametr typu <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="49aa7-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49aa7-143">Przykład</span><span class="sxs-lookup"><span data-stu-id="49aa7-143">Example</span></span>  
 <span data-ttu-id="49aa7-144">W poniższym przykładzie pokazano, jak określić tego dostawcę w wersji 3.5 C# kodu będzie używana.</span><span class="sxs-lookup"><span data-stu-id="49aa7-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="49aa7-145">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="49aa7-145">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="49aa7-146">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="49aa7-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="49aa7-147">\<kompilatory > — Element</span><span class="sxs-lookup"><span data-stu-id="49aa7-147">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="49aa7-148">Określanie w pełni kwalifikowane nazwy typów</span><span class="sxs-lookup"><span data-stu-id="49aa7-148">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [<span data-ttu-id="49aa7-149">Kompilator elementu dla kompilatory kompilacji (schemat ustawień programu ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="49aa7-149">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/en-us/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)