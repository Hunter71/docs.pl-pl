---
title: "Tworzenie Moje pierwszej usługi WCF obsługujący oświadczenia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: a27420609a6bcb6e30a351e4b84a899da9583d5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="building-my-first-claims-aware-wcf-service"></a><span data-ttu-id="4a14b-102">Tworzenie Moje pierwszej usługi WCF obsługujący oświadczenia</span><span class="sxs-lookup"><span data-stu-id="4a14b-102">Building My First Claims-Aware WCF Service</span></span>
## <a name="applies-to"></a><span data-ttu-id="4a14b-103">Dotyczy:</span><span class="sxs-lookup"><span data-stu-id="4a14b-103">Applies To</span></span>  
  
-   <span data-ttu-id="4a14b-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="4a14b-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="4a14b-105">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="4a14b-105">Windows Communication Foundation (WCF)</span></span>  
  
## <a name="overview"></a><span data-ttu-id="4a14b-106">Omówienie</span><span class="sxs-lookup"><span data-stu-id="4a14b-106">Overview</span></span>  
 <span data-ttu-id="4a14b-107">W tym temacie opisano scenariusz tworzenia przy użyciu programu WIF usług WCF obsługujących oświadczenia.</span><span class="sxs-lookup"><span data-stu-id="4a14b-107">This topic outlines the scenario of building claims-aware WCF services using WIF.</span></span> <span data-ttu-id="4a14b-108">W scenariuszu usługi sieci web obsługującej oświadczenia zazwyczaj uczestniczą trzy strony: sama usługa sieci web, użytkownik końcowy i usługa tokenu zabezpieczającego (STS).</span><span class="sxs-lookup"><span data-stu-id="4a14b-108">There are usually three participants in a claims-aware web service scenario: the web service itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="4a14b-109">Następujący rysunek opisuje ten scenariusz:</span><span class="sxs-lookup"><span data-stu-id="4a14b-109">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="4a14b-110">![WIF Basic oświadczeń usługi WCF pamiętać](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span><span class="sxs-lookup"><span data-stu-id="4a14b-110">![WIF Basic Claims Aware WCF Service](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span></span>  
  
1.  <span data-ttu-id="4a14b-111">Klient usługi WCF (czasami nazywany agentem) używa programu WIF w celu wysłania poświadczeń do usługi STS i po pomyślnym uwierzytelnieniu usługa STS wystawia mu token.</span><span class="sxs-lookup"><span data-stu-id="4a14b-111">The WCF service client (sometimes called agent) uses WIF to send credentials to the STS and upon successful authentication, the agent is issued a token by the STS.</span></span>  
  
2.  <span data-ttu-id="4a14b-112">Agent wysyła ten token wystawiony przez usługę STS do usługi WCF.</span><span class="sxs-lookup"><span data-stu-id="4a14b-112">The agent sends this STS-issued token to the WCF service.</span></span>  
  
3.  <span data-ttu-id="4a14b-113">Usługa WCF obsługująca oświadczenia jest skonfigurowana do ufania usłudze STS i wystawianym przez nią tokenem.</span><span class="sxs-lookup"><span data-stu-id="4a14b-113">The claims-aware WCF service is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="4a14b-114">Usługa WCF obsługująca oświadczenia używa programu WIF do weryfikacji i analizy tokenu.</span><span class="sxs-lookup"><span data-stu-id="4a14b-114">The claims-aware WCF service uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="4a14b-115">Deweloperzy Użyj odpowiedniego interfejsu API WIF i typów, na przykład **ClaimsPrincipal** na potrzeby aplikacji, takich jak wdrażanie autoryzacji dla niego.</span><span class="sxs-lookup"><span data-stu-id="4a14b-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincipal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="4a14b-116">Począwszy od platformy .NET 4.5, WIF jest częścią pakietu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a14b-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="4a14b-117">O klasach WIF bezpośrednio dostępne w ramach umożliwia znacznie lepsza integracja tożsamości opartego na oświadczeniach w środowisku .NET, co ułatwia użyć oświadczeń.</span><span class="sxs-lookup"><span data-stu-id="4a14b-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="4a14b-118">Mając program WIF 4.5, nie trzeba instalować żadnych składników zewnętrznych, aby rozpocząć projektowanie aplikacji sieci Web obsługujących oświadczenia.</span><span class="sxs-lookup"><span data-stu-id="4a14b-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="4a14b-119">Klasy programu WIF rozciągają się obecnie na rozmaite zestawy, z których najważniejsze to System.Security.Claims, System.IdentityModel i System.IdentityModel.Services.</span><span class="sxs-lookup"><span data-stu-id="4a14b-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="4a14b-120">STS to usługa, która wystawia tokeny po pomyślnym uwierzytelnieniu.</span><span class="sxs-lookup"><span data-stu-id="4a14b-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="4a14b-121">Firma Microsoft oferuje dwie usługi STS będące standardami branżowymi:</span><span class="sxs-lookup"><span data-stu-id="4a14b-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   <span data-ttu-id="4a14b-122">[Usługi Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span><span class="sxs-lookup"><span data-stu-id="4a14b-122">[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span></span>  
  
-   <span data-ttu-id="4a14b-123">[Usługi kontroli dostępu na platformie Azure systemu Windows (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span><span class="sxs-lookup"><span data-stu-id="4a14b-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span></span>  
  
 <span data-ttu-id="4a14b-124">Usługa AD FS 2.0 jest częścią systemu Windows Server R2 i może służyć jako usługa STS w scenariuszach lokalnych.</span><span class="sxs-lookup"><span data-stu-id="4a14b-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="4a14b-125">Azure Active Directory kontroli dostępu (znanej także jako usługa kontroli dostępu lub ACS) to usługa w chmurze, wchodzących w skład systemu Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="4a14b-125">Azure Active Directory Access Control (also known as Access Control Service or ACS) is a cloud service, offered as part of Microsoft Azure.</span></span> <span data-ttu-id="4a14b-126">Na potrzeby testowania lub w celach edukacyjnych można również używać innych usług STS do tworzenia aplikacji obsługujących oświadczenia.</span><span class="sxs-lookup"><span data-stu-id="4a14b-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="4a14b-127">Na przykład można użyć lokalnego STS programowanie, który jest częścią [tożsamości i dostępu do narzędzi dla programu Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) który jest dostępny w trybie online.</span><span class="sxs-lookup"><span data-stu-id="4a14b-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="4a14b-128">Aby utworzyć pierwszy obsługujący oświadczenia WCF usługi przy użyciu WIF, zobacz [jak: tworzenie oświadczeń WCF usługi przy użyciu WIF](http://msdn.microsoft.com/en-us/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).</span><span class="sxs-lookup"><span data-stu-id="4a14b-128">To build your first claims-aware WCF service using WIF, see [How To: Build Claims-Aware WCF Service Using WIF](http://msdn.microsoft.com/en-us/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a14b-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4a14b-129">See Also</span></span>  
 [<span data-ttu-id="4a14b-130">Wprowadzenie do korzystania z programu WIF</span><span class="sxs-lookup"><span data-stu-id="4a14b-130">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)