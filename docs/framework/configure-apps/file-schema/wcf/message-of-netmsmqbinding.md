---
title: '&lt;message&gt; w &lt;netMsmqBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f3b03fcce02c51563ed006e62a3f77f76bede777
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="56e5a-102">&lt;message&gt; w &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="56e5a-102">&lt;message&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="56e5a-103">Definiuje ustawienia zabezpieczeń wiadomości SOAP na tym `netMsmqBinding` powiązania.</span><span class="sxs-lookup"><span data-stu-id="56e5a-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>  
  
 <span data-ttu-id="56e5a-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="56e5a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="56e5a-105">\<powiązania ></span><span class="sxs-lookup"><span data-stu-id="56e5a-105">\<bindings></span></span>  
<span data-ttu-id="56e5a-106">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="56e5a-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="56e5a-107">\<Powiązanie ></span><span class="sxs-lookup"><span data-stu-id="56e5a-107">\<binding></span></span>  
<span data-ttu-id="56e5a-108">\<Zabezpieczenia ></span><span class="sxs-lookup"><span data-stu-id="56e5a-108">\<security></span></span>  
<span data-ttu-id="56e5a-109">\<komunikat ></span><span class="sxs-lookup"><span data-stu-id="56e5a-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e5a-110">Składnia</span><span class="sxs-lookup"><span data-stu-id="56e5a-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56e5a-111">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="56e5a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="56e5a-112">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="56e5a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56e5a-113">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="56e5a-113">Attributes</span></span>  
  
|<span data-ttu-id="56e5a-114">Atrybut</span><span class="sxs-lookup"><span data-stu-id="56e5a-114">Attribute</span></span>|<span data-ttu-id="56e5a-115">Opis</span><span class="sxs-lookup"><span data-stu-id="56e5a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56e5a-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="56e5a-116">algorithmSuite</span></span>|<span data-ttu-id="56e5a-117">Ustawia komunikat algorytmów szyfrowania i zawijania klucza, które są używane do uzyskania zabezpieczenia oparte na komunikatu dla komunikatów wysyłanych za pośrednictwem transportu MSMQ.</span><span class="sxs-lookup"><span data-stu-id="56e5a-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="56e5a-118">Wartość domyślna to `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="56e5a-118">The default value is `Aes256`.</span></span> <span data-ttu-id="56e5a-119">Ten atrybut jest typu <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="56e5a-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|  
|<span data-ttu-id="56e5a-120">Właściwość clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="56e5a-120">clientCredentialType</span></span>|<span data-ttu-id="56e5a-121">Określa typ poświadczenia, które będą używane podczas uwierzytelniania klienta dla komunikatów wysyłanych za pomocą transportu MSMQ.</span><span class="sxs-lookup"><span data-stu-id="56e5a-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="56e5a-122">Prawidłowe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="56e5a-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="56e5a-123">-Brak: Dzięki usłudze na współdziałanie z anonimowego klientów.</span><span class="sxs-lookup"><span data-stu-id="56e5a-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="56e5a-124">Usługa ani klient wymagane jest podanie poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="56e5a-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="56e5a-125">-Windows: Umożliwia wymianę SOAP się pod uwierzytelnionego kontekstu poświadczenia systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="56e5a-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="56e5a-126">To jest zawsze przeprowadza uwierzytelnianie za pomocą protokołu Kerberos.</span><span class="sxs-lookup"><span data-stu-id="56e5a-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="56e5a-127">-UserName: Włącza usługę, aby wymagać który uwierzytelnienia klienta przy użyciu poświadczeń UserName.</span><span class="sxs-lookup"><span data-stu-id="56e5a-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="56e5a-128">Poświadczenia w takim przypadku należy określić przy użyciu `clientCredentials` zachowanie **Przestroga:** [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] nie obsługuje wysyłanie hasła klawiszy skrótu lub wyprowadzanie przy użyciu hasła i te klucze dla zabezpieczenia wiadomości.  </span><span class="sxs-lookup"><span data-stu-id="56e5a-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="56e5a-129">W związku z tym [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] wymusza, że programu exchange jest zabezpieczone przy użyciu poświadczeń UserName.</span><span class="sxs-lookup"><span data-stu-id="56e5a-129">Therefore, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="56e5a-130">Ten tryb wymaga określenia certyfikatu usługi przy użyciu po stronie klienta `clientCredential` zachowania i `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="56e5a-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="56e5a-131">-Certyfikat: Włącza usługę, aby wymagać który uwierzytelnienia klienta za pomocą certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="56e5a-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="56e5a-132">W takim przypadku poświadczeń klienta należy określić przy użyciu `clientCredentials` zachowanie.</span><span class="sxs-lookup"><span data-stu-id="56e5a-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="56e5a-133">Poświadczenia usługi w takim przypadku należy określić przy użyciu `clientCredentials` zachowanie, określając `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="56e5a-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="56e5a-134">-CardSpace: Umożliwia usłudze wymagają który uwierzytelnienia klienta za pomocą programu CardSpace.</span><span class="sxs-lookup"><span data-stu-id="56e5a-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="56e5a-135">`serviceCertiifcate` Należy udostępnić w `clientCredential` zachowanie.</span><span class="sxs-lookup"><span data-stu-id="56e5a-135">The `serviceCertiifcate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="56e5a-136">Wartość domyślna to `Windows`.</span><span class="sxs-lookup"><span data-stu-id="56e5a-136">The default value is `Windows`.</span></span> <span data-ttu-id="56e5a-137">Ten atrybut jest typu <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="56e5a-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56e5a-138">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="56e5a-138">Child Elements</span></span>  
 <span data-ttu-id="56e5a-139">Brak</span><span class="sxs-lookup"><span data-stu-id="56e5a-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56e5a-140">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="56e5a-140">Parent Elements</span></span>  
  
|<span data-ttu-id="56e5a-141">Element</span><span class="sxs-lookup"><span data-stu-id="56e5a-141">Element</span></span>|<span data-ttu-id="56e5a-142">Opis</span><span class="sxs-lookup"><span data-stu-id="56e5a-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56e5a-143">\<Zabezpieczenia ></span><span class="sxs-lookup"><span data-stu-id="56e5a-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="56e5a-144">Definiuje ustawienia zabezpieczeń dla powiązania.</span><span class="sxs-lookup"><span data-stu-id="56e5a-144">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56e5a-145">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="56e5a-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [<span data-ttu-id="56e5a-146">Kolejki programu WCF</span><span class="sxs-lookup"><span data-stu-id="56e5a-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="56e5a-147">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="56e5a-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="56e5a-148">Powiązania</span><span class="sxs-lookup"><span data-stu-id="56e5a-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="56e5a-149">Konfigurowanie powiązań dostarczanych przez System</span><span class="sxs-lookup"><span data-stu-id="56e5a-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="56e5a-150">Konfigurowanie usług Windows Communication Foundation i klientów za pomocą powiązań</span><span class="sxs-lookup"><span data-stu-id="56e5a-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="56e5a-151">\<Powiązanie ></span><span class="sxs-lookup"><span data-stu-id="56e5a-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)