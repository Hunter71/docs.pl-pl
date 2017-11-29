---
title: "Przegląd korelacji"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edcc0315-5d26-44d6-a36d-ea554c418e9f
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3d4320c088c66abdc2c4ff226eb99d66fcbd3b38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="correlation-overview"></a><span data-ttu-id="57121-102">Przegląd korelacji</span><span class="sxs-lookup"><span data-stu-id="57121-102">Correlation Overview</span></span>
<span data-ttu-id="57121-103">Korelacja jest mechanizm dotyczących komunikatów usługi przepływu pracy lub stan wystąpienia aplikacji, takich jak odpowiedzi na żądanie początkowej lub identyfikator określonej kolejności stanu utrwalonego kolejność przetwarzania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="57121-103">Correlation is the mechanism for relating workflow service messages to each other or to the application instance state, such as a reply to an initial request, or a particular order ID to the persisted state of an order-processing workflow.</span></span> <span data-ttu-id="57121-104">Ten temat zawiera przegląd korelacji.</span><span class="sxs-lookup"><span data-stu-id="57121-104">This topic provides an overview of correlation.</span></span> <span data-ttu-id="57121-105">W innych tematach w tej sekcji zawierają dodatkowe informacje dla każdego typu korelacji.</span><span class="sxs-lookup"><span data-stu-id="57121-105">The other topics in this section provide additional information for each type of correlation.</span></span>  
  
## <a name="types-of-correlation"></a><span data-ttu-id="57121-106">Typy korelacji</span><span class="sxs-lookup"><span data-stu-id="57121-106">Types of Correlation</span></span>  
 <span data-ttu-id="57121-107">Korelacja może być opartych na protokole lub na podstawie zawartości.</span><span class="sxs-lookup"><span data-stu-id="57121-107">Correlation can be protocol-based or content-based.</span></span> <span data-ttu-id="57121-108">Opartych na protokole korelacji Użyj dane dostarczone przez infrastrukturę dostarczania wiadomości, aby określić mapowanie między wiadomości.</span><span class="sxs-lookup"><span data-stu-id="57121-108">Protocol-based correlations use data provided by the message delivery infrastructure to provide the mapping between messages.</span></span> <span data-ttu-id="57121-109">Wiadomości, które są skorelowane przy użyciu opartych na protokole korelacji są powiązane ze sobą przy użyciu obiektu w pamięci, takich jak <xref:System.ServiceModel.Channels.RequestContext>, lub przez token dostarczony przez protokół transportu.</span><span class="sxs-lookup"><span data-stu-id="57121-109">Messages that are correlated using protocol-based correlation are related to each other using an object in memory, such as a <xref:System.ServiceModel.Channels.RequestContext>, or by a token provided by the transport protocol.</span></span> <span data-ttu-id="57121-110">Na podstawie zawartości korelacji odnoszą się komunikaty ze sobą przy użyciu danych z określonych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="57121-110">Content-based correlations relate messages to each other using application-specified data.</span></span> <span data-ttu-id="57121-111">Wiadomości, które są skorelowane przy użyciu korelacji na podstawie zawartości są ze sobą powiązane przez niektóre dane zdefiniowane przez aplikację w wiadomości, takie jak numer klienta.</span><span class="sxs-lookup"><span data-stu-id="57121-111">Messages that are correlated using content-based correlation are related to each other by some application-defined data in the message, such as a customer number.</span></span>  
  
 <span data-ttu-id="57121-112">Działania, które uczestniczą w użyciu korelacji <xref:System.ServiceModel.Activities.CorrelationHandle> powiązać razem działania obsługi wiadomości.</span><span class="sxs-lookup"><span data-stu-id="57121-112">Activities that participate in correlation use a <xref:System.ServiceModel.Activities.CorrelationHandle> to tie the messaging activities together.</span></span> <span data-ttu-id="57121-113">Na przykład <xref:System.ServiceModel.Activities.Send> używany do wywołania usługi i kolejnej <xref:System.ServiceModel.Activities.Receive> używany do odbierania wywołania zwrotnego z usługą, identyczny <xref:System.ServiceModel.Activities.CorrelationHandle>.</span><span class="sxs-lookup"><span data-stu-id="57121-113">For example, a <xref:System.ServiceModel.Activities.Send> that is used to call a service and a subsequent <xref:System.ServiceModel.Activities.Receive> that is used to receive a callback from the service, share the same <xref:System.ServiceModel.Activities.CorrelationHandle>.</span></span> <span data-ttu-id="57121-114">Ten wzorzec podstawowe służy czy korelacji jest zawartość lub protokół.</span><span class="sxs-lookup"><span data-stu-id="57121-114">This basic pattern is used whether the correlation is content based or protocol based.</span></span> <span data-ttu-id="57121-115">Dojście korelacji można jawnie ustawiona na każde działanie lub działania mogą być zawarte w <xref:System.ServiceModel.Activities.CorrelationScope> działania.</span><span class="sxs-lookup"><span data-stu-id="57121-115">The correlation handle can be explicitly set on each activity or the activities can be contained in a <xref:System.ServiceModel.Activities.CorrelationScope> activity.</span></span> <span data-ttu-id="57121-116">Działań zawartych w <xref:System.ServiceModel.Activities.CorrelationScope> ma ich dojścia korelacji zarządza <xref:System.ServiceModel.Activities.CorrelationScope> i nie wymagają <xref:System.ServiceModel.Activities.CorrelationHandle> należy jawnie ustawić.</span><span class="sxs-lookup"><span data-stu-id="57121-116">Activities contained in a <xref:System.ServiceModel.Activities.CorrelationScope> have their correlation handles managed by the <xref:System.ServiceModel.Activities.CorrelationScope> and do not require the <xref:System.ServiceModel.Activities.CorrelationHandle> to be explicitly set.</span></span> <span data-ttu-id="57121-117">A <xref:System.ServiceModel.Activities.CorrelationScope> zakres udostępnia <xref:System.ServiceModel.Activities.CorrelationHandle> zarządzania dla korelacji żądanie odpowiedź i jeden typ dodatkowe korelacji.</span><span class="sxs-lookup"><span data-stu-id="57121-117">A <xref:System.ServiceModel.Activities.CorrelationScope> scope provides <xref:System.ServiceModel.Activities.CorrelationHandle> management for a request-reply correlation and one additional correlation type.</span></span> <span data-ttu-id="57121-118">Hostowane przy użyciu usługi przepływu pracy <xref:System.ServiceModel.Activities.WorkflowServiceHost> mają tej samej obsługi korelacji domyślne jako <xref:System.ServiceModel.Activities.CorrelationScope> działania.</span><span class="sxs-lookup"><span data-stu-id="57121-118">Workflow services hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost> have the same default correlation management as the <xref:System.ServiceModel.Activities.CorrelationScope> activity.</span></span> <span data-ttu-id="57121-119">Zarządzanie korelacji ten domyślny zazwyczaj oznacza, że w wielu scenariuszach wiadomości działań w <xref:System.ServiceModel.Activities.CorrelationScope> lub usługi przepływu pracy nie wymagają ich <xref:System.ServiceModel.Activities.CorrelationHandle> ustawić wiele działań wiadomości znajdują się w równoległego lub nakładają się na siebie, takie jak dwa <xref:System.ServiceModel.Activities.Receive> działania równoległego lub dwóch <xref:System.ServiceModel.Activities.Send> czynności zostały wykonane przez dwa <xref:System.ServiceModel.Activities.Receive> działań.</span><span class="sxs-lookup"><span data-stu-id="57121-119">This default correlation management generally means that in many scenarios, messaging activities in a <xref:System.ServiceModel.Activities.CorrelationScope> or a workflow service do not require their <xref:System.ServiceModel.Activities.CorrelationHandle> set unless multiple messaging activities are in parallel or overlap, such as two <xref:System.ServiceModel.Activities.Receive> activities in parallel, or two <xref:System.ServiceModel.Activities.Send> activities followed by two <xref:System.ServiceModel.Activities.Receive> activities.</span></span> <span data-ttu-id="57121-120">Więcej informacji na temat korelacji domyślny znajduje się w tematach w tej sekcji, które obejmują poszczególnych typów korelacji.</span><span class="sxs-lookup"><span data-stu-id="57121-120">More information about default correlation is provided in the topics in this section that cover each specific type of correlation.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="57121-121">działania obsługi komunikatów, zobacz [wiadomości działania](../../../../docs/framework/wcf/feature-details/messaging-activities.md) i [porady: Tworzenie usługi przepływu pracy z działaniami wiadomości](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md).</span><span class="sxs-lookup"><span data-stu-id="57121-121"> messaging activities see [Messaging Activities](../../../../docs/framework/wcf/feature-details/messaging-activities.md) and [How to: Create a Workflow Service with Messaging Activities](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md).</span></span>  
  
## <a name="protocol-based-correlation"></a><span data-ttu-id="57121-122">Opartych na protokole korelacji</span><span class="sxs-lookup"><span data-stu-id="57121-122">Protocol-Based Correlation</span></span>  
 <span data-ttu-id="57121-123">Opartych na protokole korelacji używany mechanizm transportu do powiązania wiadomości i odpowiednie wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="57121-123">Protocol-based correlation uses the transport mechanism to relate messages to each other and the appropriate instance.</span></span> <span data-ttu-id="57121-124">Niektóre korelacji protokołu dostarczane przez system obejmują korelacja żądań i odpowiedzi i kontekstowa korelacji.</span><span class="sxs-lookup"><span data-stu-id="57121-124">Some system-provided protocol correlations include request-reply correlation and context-based correlation.</span></span> <span data-ttu-id="57121-125">Korelacja żądań i odpowiedzi służy do skorelowania pojedynczego parę działania obsługi komunikatów do utworzenia dwukierunkowe operacji, takich jak <xref:System.ServiceModel.Activities.Send> sparowanego z <xref:System.ServiceModel.Activities.ReceiveReply>, lub <xref:System.ServiceModel.Activities.Receive> sparowanego z <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="57121-125">A request-reply correlation is used to correlate a single pair of messaging activities to form a two-way operation, such as a <xref:System.ServiceModel.Activities.Send> paired with a <xref:System.ServiceModel.Activities.ReceiveReply>, or a <xref:System.ServiceModel.Activities.Receive> paired with a <xref:System.ServiceModel.Activities.SendReply>.</span></span> <span data-ttu-id="57121-126">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Projektanta przepływów pracy udostępnia również zestaw szablonów działania szybkie rozpoczęcie tego wzorca.</span><span class="sxs-lookup"><span data-stu-id="57121-126">The [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Workflow Designer also provides a set of activity templates to quickly implement this pattern.</span></span> <span data-ttu-id="57121-127">Kontekstowa korelacji jest oparta na mechanizm wymiany kontekstu opisanego w [Specyfikacja protokół wymiany kontekstu .NET](http://go.microsoft.com/fwlink/?LinkID=166059).</span><span class="sxs-lookup"><span data-stu-id="57121-127">A context-based correlation is based on the context exchange mechanism described in the [.NET Context Exchange Protocol Specification](http://go.microsoft.com/fwlink/?LinkID=166059).</span></span> <span data-ttu-id="57121-128">Do użycia na podstawie kontekstu korelacji, na podstawie kontekstu wiązania takich jak <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> lub <xref:System.ServiceModel.NetTcpContextBinding> musi być używany w punkcie końcowym.</span><span class="sxs-lookup"><span data-stu-id="57121-128">To use context-based correlation, a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> or <xref:System.ServiceModel.NetTcpContextBinding> must be used on the endpoint.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="57121-129">Protokół korelacji, zobacz [wymiana kontekstu](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md), [trwałe dupleksu](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md), i [żądanie-odpowiedź](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md).</span><span class="sxs-lookup"><span data-stu-id="57121-129"> protocol correlation, see [Context Exchange](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md), [Durable Duplex](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md), and [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="57121-130">przy użyciu [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] szablony działania projektanta przepływów pracy, zobacz [wiadomości działania](../../../../docs/framework/wcf/feature-details/messaging-activities.md).</span><span class="sxs-lookup"><span data-stu-id="57121-130"> using the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Workflow Designer activity templates, see [Messaging Activities](../../../../docs/framework/wcf/feature-details/messaging-activities.md).</span></span> <span data-ttu-id="57121-131">Przykładowy kod, zobacz [trwałe dupleksu &#91; WF — przykłady &#93; ](../../../../docs/framework/windows-workflow-foundation/samples/durable-duplex.md) i [NetContextExchangeCorrelation](http://msdn.microsoft.com/en-us/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) próbek.</span><span class="sxs-lookup"><span data-stu-id="57121-131">For sample code, see the [Durable Duplex &#91;WF Samples&#93;](../../../../docs/framework/windows-workflow-foundation/samples/durable-duplex.md) and [NetContextExchangeCorrelation](http://msdn.microsoft.com/en-us/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) samples.</span></span>  
  
## <a name="content-based-correlation"></a><span data-ttu-id="57121-132">Korelacja na podstawie zawartości</span><span class="sxs-lookup"><span data-stu-id="57121-132">Content-Based Correlation</span></span>  
 <span data-ttu-id="57121-133">Na podstawie zawartości korelacji używa elementu informacji w komunikacie Aby skojarzyć ją do określonego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="57121-133">Content-based correlation uses some piece of information in the message to associate it to a particular instance.</span></span> <span data-ttu-id="57121-134">W przeciwieństwie do opartych na protokole korelacji korelacji na podstawie zawartości wymaga Autor aplikacji jawnie określić, gdzie te dane znajdują się w każdej wiadomości pokrewne.</span><span class="sxs-lookup"><span data-stu-id="57121-134">Unlike protocol-based correlation, content-based correlation requires the application author to explicitly state where this data can be found in each related message.</span></span> <span data-ttu-id="57121-135">Operacje używające korelacji na podstawie zawartości określić te dane wiadomości przy użyciu <xref:System.ServiceModel.MessageQuerySet>.</span><span class="sxs-lookup"><span data-stu-id="57121-135">Activities that use content-based correlation specify this message data by using a <xref:System.ServiceModel.MessageQuerySet>.</span></span> <span data-ttu-id="57121-136">Na podstawie zawartości korelacji jest przydatne podczas komunikowania się z usługami, które nie korzystają z jednym z powiązań kontekstu, takich jak <xref:System.ServiceModel.BasicHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="57121-136">Content-based correlation is useful when communicating with services that do not use one of the context bindings such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="57121-137">Korelacja na podstawie zawartości, zobacz [na podstawie zawartości](../../../../docs/framework/wcf/feature-details/content-based-correlation.md).</span><span class="sxs-lookup"><span data-stu-id="57121-137"> content-based correlation, see [Content Based](../../../../docs/framework/wcf/feature-details/content-based-correlation.md).</span></span> <span data-ttu-id="57121-138">Przykładowy kod, zobacz [na podstawie zawartości korelacji](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md) i [skorelowane Kalkulator](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md) próbek.</span><span class="sxs-lookup"><span data-stu-id="57121-138">For sample code, see the [Content-Based Correlation](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md) and [Correlated Calculator](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md) samples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57121-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="57121-139">See Also</span></span>  
 [<span data-ttu-id="57121-140">Korelacja na podstawie zawartości</span><span class="sxs-lookup"><span data-stu-id="57121-140">Content-Based Correlation</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md)  
 [<span data-ttu-id="57121-141">Kalkulator skorelowane</span><span class="sxs-lookup"><span data-stu-id="57121-141">Correlated Calculator</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)  
 [<span data-ttu-id="57121-142">Niezawodna komunikacja dwukierunkowa &#91; WF — przykłady &#93;</span><span class="sxs-lookup"><span data-stu-id="57121-142">Durable Duplex &#91;WF Samples&#93;</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/durable-duplex.md)  
 [<span data-ttu-id="57121-143">NetContextExchangeCorrelation</span><span class="sxs-lookup"><span data-stu-id="57121-143">NetContextExchangeCorrelation</span></span>](http://msdn.microsoft.com/en-us/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf)