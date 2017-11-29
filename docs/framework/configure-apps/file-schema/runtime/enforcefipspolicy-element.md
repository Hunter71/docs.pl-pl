---
title: "&lt;enforcefipspolicy —&gt; — Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9bd593c17d752b35919985aad37f675c62e6ce34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltenforcefipspolicygt-element"></a><span data-ttu-id="bb54c-102">&lt;enforcefipspolicy —&gt; — Element</span><span class="sxs-lookup"><span data-stu-id="bb54c-102">&lt;enforceFIPSPolicy&gt; Element</span></span>
<span data-ttu-id="bb54c-103">Określa, czy można wymusić wymagania konfiguracji komputera, że algorytmy kryptograficzne musi być zgodne z przetwarzania standardami FIPS (Federal Information).</span><span class="sxs-lookup"><span data-stu-id="bb54c-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="bb54c-104">\<Konfiguracja > — Element</span><span class="sxs-lookup"><span data-stu-id="bb54c-104">\<configuration> Element</span></span>  
<span data-ttu-id="bb54c-105">\<środowisko uruchomieniowe > — Element</span><span class="sxs-lookup"><span data-stu-id="bb54c-105">\<runtime> Element</span></span>  
<span data-ttu-id="bb54c-106">\<enforcefipspolicy — > — Element</span><span class="sxs-lookup"><span data-stu-id="bb54c-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb54c-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="bb54c-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb54c-108">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="bb54c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bb54c-109">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="bb54c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb54c-110">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="bb54c-110">Attributes</span></span>  
  
|<span data-ttu-id="bb54c-111">Atrybut</span><span class="sxs-lookup"><span data-stu-id="bb54c-111">Attribute</span></span>|<span data-ttu-id="bb54c-112">Opis</span><span class="sxs-lookup"><span data-stu-id="bb54c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb54c-113">włączone</span><span class="sxs-lookup"><span data-stu-id="bb54c-113">enabled</span></span>|<span data-ttu-id="bb54c-114">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="bb54c-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="bb54c-115">Określa, czy włączyć wymuszania wymaganie konfiguracji komputera, że algorytmy kryptograficzne muszą być zgodne z trybem FIPS.</span><span class="sxs-lookup"><span data-stu-id="bb54c-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bb54c-116">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="bb54c-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="bb54c-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="bb54c-117">Value</span></span>|<span data-ttu-id="bb54c-118">Opis</span><span class="sxs-lookup"><span data-stu-id="bb54c-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="bb54c-119">Gdy komputer jest skonfigurowany do żądania algorytmów kryptograficznych za zgodny ze standardem FIPS, ten wymóg jest wymuszana.</span><span class="sxs-lookup"><span data-stu-id="bb54c-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="bb54c-120">Jeśli klasa implementuje algorytmu, który nie jest zgodna z trybem FIPS, konstruktorów lub `Create` metody tej klasy zgłaszają wyjątki, gdy są uruchamiane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="bb54c-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="bb54c-121">Domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="bb54c-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="bb54c-122">Algorytmy kryptograficzne, które są używane przez aplikację nie są wymagane, aby było zgodne z trybem FIPS, niezależnie od konfiguracji komputera.</span><span class="sxs-lookup"><span data-stu-id="bb54c-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb54c-123">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="bb54c-123">Child Elements</span></span>  
 <span data-ttu-id="bb54c-124">Brak.</span><span class="sxs-lookup"><span data-stu-id="bb54c-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb54c-125">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="bb54c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bb54c-126">Element</span><span class="sxs-lookup"><span data-stu-id="bb54c-126">Element</span></span>|<span data-ttu-id="bb54c-127">Opis</span><span class="sxs-lookup"><span data-stu-id="bb54c-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bb54c-128">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb54c-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bb54c-129">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="bb54c-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb54c-130">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bb54c-130">Remarks</span></span>  
 <span data-ttu-id="bb54c-131">Począwszy od programu .NET Framework 2.0, tworzenie klas implementujących algorytmów kryptograficznych jest kontrolowana przez konfiguracji komputera.</span><span class="sxs-lookup"><span data-stu-id="bb54c-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="bb54c-132">Jeśli komputer jest skonfigurowany do żądania algorytmów, aby było zgodne z trybem FIPS, a klasa implementuje algorytmu, który nie jest zgodna z trybem FIPS, wszelkie próby utworzenia wystąpienia tej klasy zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="bb54c-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="bb54c-133">Konstruktory throw <xref:System.InvalidOperationException> wyjątek, i `Create` metod generują <xref:System.Reflection.TargetInvocationException> wyjątek z wewnętrznego <xref:System.InvalidOperationException> wyjątku.</span><span class="sxs-lookup"><span data-stu-id="bb54c-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="bb54c-134">W przypadku aplikacja działa na komputerach, na których konfiguracje wymagają zgodności z trybem FIPS, a aplikacja używa algorytmu, który nie jest zgodna z trybem FIPS, można użyć tego elementu w pliku konfiguracji, aby zapobiec środowisko uruchomieniowe języka wspólnego (CLR) z Wymuszanie zgodności ze standardem FIPS.</span><span class="sxs-lookup"><span data-stu-id="bb54c-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="bb54c-135">Ten element został wprowadzony w [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb54c-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb54c-136">Przykład</span><span class="sxs-lookup"><span data-stu-id="bb54c-136">Example</span></span>  
 <span data-ttu-id="bb54c-137">Poniższy przykład pokazuje, jak zapobiec CLR Wymuszanie zgodności ze standardem FIPS.</span><span class="sxs-lookup"><span data-stu-id="bb54c-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb54c-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bb54c-138">See Also</span></span>  
 [<span data-ttu-id="bb54c-139">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="bb54c-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="bb54c-140">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="bb54c-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="bb54c-141">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="bb54c-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)