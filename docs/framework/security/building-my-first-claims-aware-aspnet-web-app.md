---
title: "Tworzenie mojej pierwszej aplikacji sieci Web ASP.NET obsługujących oświadczenia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: aa25f163199652618e35399c6548a9864a17370a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a><span data-ttu-id="45f3b-102">Tworzenie mojej pierwszej aplikacji sieci Web ASP.NET obsługujących oświadczenia</span><span class="sxs-lookup"><span data-stu-id="45f3b-102">Building My First Claims-Aware ASP.NET Web Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="45f3b-103">Dotyczy:</span><span class="sxs-lookup"><span data-stu-id="45f3b-103">Applies To</span></span>  
  
-   <span data-ttu-id="45f3b-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="45f3b-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="45f3b-105">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="45f3b-105">ASP.NET</span></span>  
  
 <span data-ttu-id="45f3b-106">W tym temacie opisano scenariusz tworzenia przy użyciu programu WIF aplikacji sieci Web programu ASP.NET obsługującej oświadczenia.</span><span class="sxs-lookup"><span data-stu-id="45f3b-106">This topic outlines the scenario of building claims-aware ASP.NET web applications using WIF.</span></span> <span data-ttu-id="45f3b-107">W scenariuszu aplikacji obsługującej oświadczenia zazwyczaj uczestniczą trzy strony: sama aplikacja, użytkownik końcowy i usługa tokenu zabezpieczającego (STS).</span><span class="sxs-lookup"><span data-stu-id="45f3b-107">There are usually three participants in a claims-aware application scenario: the application itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="45f3b-108">Następujący rysunek opisuje ten scenariusz:</span><span class="sxs-lookup"><span data-stu-id="45f3b-108">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="45f3b-109">![Aplikacja sieci Web podstawowe WIF](../../../docs/framework/security/media/wifbasicwebapp.gif "WIFBasicWebApp")</span><span class="sxs-lookup"><span data-stu-id="45f3b-109">![WIF Basic Web App](../../../docs/framework/security/media/wifbasicwebapp.gif "WIFBasicWebApp")</span></span>  
  
1.  <span data-ttu-id="45f3b-110">Aplikacja obsługująca oświadczenia używa programu WIF do identyfikowania nieuwierzytelnionych żądań i przekierowywania ich do usługi STS.</span><span class="sxs-lookup"><span data-stu-id="45f3b-110">The claims-aware application uses WIF to identify unauthenticated requests and to redirect them to the STS.</span></span>  
  
2.  <span data-ttu-id="45f3b-111">Użytkownik końcowy podaje poświadczenia usłudze STS i po pomyślnym uwierzytelnieniu usługa STS wystawia mu token.</span><span class="sxs-lookup"><span data-stu-id="45f3b-111">The end user provides credentials to the STS and upon successful authentication the user is issued a token by the STS.</span></span>  
  
3.  <span data-ttu-id="45f3b-112">Przy użyciu tokenu wystawionego przez usługę STS w żądaniu użytkownik jest przekierowywany z usługi STS do aplikacji obsługującej oświadczenia.</span><span class="sxs-lookup"><span data-stu-id="45f3b-112">The user is redirected from the STS to the claims-aware application with the STS-issued token in the request.</span></span>  
  
4.  <span data-ttu-id="45f3b-113">Aplikacja obsługująca oświadczenia jest skonfigurowana do ufania usłudze STS i wystawianym przez nią tokenem.</span><span class="sxs-lookup"><span data-stu-id="45f3b-113">The claims-aware application is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="45f3b-114">Aplikacja obsługująca oświadczenia używa programu WIF do weryfikacji i analizy tokenu.</span><span class="sxs-lookup"><span data-stu-id="45f3b-114">The claims-aware application uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="45f3b-115">Deweloperzy Użyj odpowiedniego interfejsu API WIF i typów, na przykład **ClaimsPrincpal** na potrzeby aplikacji, takich jak wdrażanie autoryzacji dla niego.</span><span class="sxs-lookup"><span data-stu-id="45f3b-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincpal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="45f3b-116">Począwszy od platformy .NET 4.5, WIF jest częścią pakietu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="45f3b-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="45f3b-117">O klasach WIF bezpośrednio dostępne w ramach umożliwia znacznie lepsza integracja tożsamości opartego na oświadczeniach w środowisku .NET, co ułatwia użyć oświadczeń.</span><span class="sxs-lookup"><span data-stu-id="45f3b-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="45f3b-118">Mając program WIF 4.5, nie trzeba instalować żadnych składników zewnętrznych, aby rozpocząć projektowanie aplikacji sieci Web obsługujących oświadczenia.</span><span class="sxs-lookup"><span data-stu-id="45f3b-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="45f3b-119">Klasy programu WIF rozciągają się obecnie na rozmaite zestawy, z których najważniejsze to System.Security.Claims, System.IdentityModel i System.IdentityModel.Services.</span><span class="sxs-lookup"><span data-stu-id="45f3b-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="45f3b-120">STS to usługa, która wystawia tokeny po pomyślnym uwierzytelnieniu.</span><span class="sxs-lookup"><span data-stu-id="45f3b-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="45f3b-121">Firma Microsoft oferuje dwie usługi STS będące standardami branżowymi:</span><span class="sxs-lookup"><span data-stu-id="45f3b-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   <span data-ttu-id="45f3b-122">[Usługi Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span><span class="sxs-lookup"><span data-stu-id="45f3b-122">[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span></span>  
  
-   <span data-ttu-id="45f3b-123">[Usługi kontroli dostępu na platformie Azure systemu Windows (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span><span class="sxs-lookup"><span data-stu-id="45f3b-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span></span>  
  
 <span data-ttu-id="45f3b-124">Usługa AD FS 2.0 jest częścią systemu Windows Server R2 i może służyć jako usługa STS w scenariuszach lokalnych.</span><span class="sxs-lookup"><span data-stu-id="45f3b-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="45f3b-125">ACS to usługa w chmurze oferowana jako część platformy Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="45f3b-125">ACS is a cloud service, offered as part of the Windows Azure Platform.</span></span> <span data-ttu-id="45f3b-126">Na potrzeby testowania lub w celach edukacyjnych można również używać innych usług STS do tworzenia aplikacji obsługujących oświadczenia.</span><span class="sxs-lookup"><span data-stu-id="45f3b-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="45f3b-127">Na przykład można użyć lokalnego STS programowanie, który jest częścią [tożsamości i dostępu do narzędzi dla programu Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) który jest dostępny w trybie online.</span><span class="sxs-lookup"><span data-stu-id="45f3b-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="45f3b-128">Aby przy użyciu programu WIF utworzyć swoją pierwszą aplikację programu ASP.NET obsługującą oświadczenia, postępuj zgodnie z instrukcjami podanymi w jednym z następujących tematów:</span><span class="sxs-lookup"><span data-stu-id="45f3b-128">To build your first claims-aware ASP.NET application using WIF, follow the instructions in one of the following:</span></span>  
  
-   [<span data-ttu-id="45f3b-129">Porady: Tworzenie aplikacji sieci Web obsługujący oświadczenia platformy ASP.NET MVC za pomocą WIF</span><span class="sxs-lookup"><span data-stu-id="45f3b-129">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [<span data-ttu-id="45f3b-130">Porady: Tworzenie aplikacji formularzy sieci Web obsługujący oświadczenia ASP.NET za pomocą WIF</span><span class="sxs-lookup"><span data-stu-id="45f3b-130">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [<span data-ttu-id="45f3b-131">Porady: Tworzenie aplikacji obsługującej oświadczenia ASP.NET przy użyciu uwierzytelniania opartego na formularzach</span><span class="sxs-lookup"><span data-stu-id="45f3b-131">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="45f3b-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="45f3b-132">See Also</span></span>  
 [<span data-ttu-id="45f3b-133">Wprowadzenie do korzystania z programu WIF</span><span class="sxs-lookup"><span data-stu-id="45f3b-133">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)