---
title: "Porady: Tworzenie magazynu wystąpienia niestandardowego"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 593c4e9d-8a49-4e12-8257-cee5e6b4c075
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c383d3af92ba2f76f8ba09bc194220c170beaa0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-custom-instance-store"></a><span data-ttu-id="a7e06-102">Porady: Tworzenie magazynu wystąpienia niestandardowego</span><span class="sxs-lookup"><span data-stu-id="a7e06-102">How to: Create a Custom Instance Store</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="a7e06-103">zawiera <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, magazynie wystąpień, który używa programu SQL Server do utrwalenia danych przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a7e06-103"> contains <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, an instance store that uses SQL Server to persist workflow data.</span></span> <span data-ttu-id="a7e06-104">Jeśli aplikacja jest wymagany do utrwalenia danych przepływu pracy na inny nośnik, na przykład innej bazy danych lub systemu plików, można zaimplementować magazynu niestandardowego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="a7e06-104">If your application is required to persist workflow data to another medium, such as a different database or a file system, you can implement a custom instance store.</span></span> <span data-ttu-id="a7e06-105">Magazynu niestandardowego wystąpienia jest tworzony przez rozszerzenie klasy abstrakcyjnej <xref:System.Runtime.DurableInstancing.InstanceStore> klasy i implementacja metody, które są wymagane do wykonania.</span><span class="sxs-lookup"><span data-stu-id="a7e06-105">A custom instance store is created by extending the abstract <xref:System.Runtime.DurableInstancing.InstanceStore> class and implementing the methods that are required for the implementation.</span></span> <span data-ttu-id="a7e06-106">Do zakończenia wdrożenia magazynu niestandardowego wystąpienia, zobacz [firmowej procesu zakupu](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) próbki.</span><span class="sxs-lookup"><span data-stu-id="a7e06-106">For a complete implementation of a custom instance store, see the [Corporate Purchase Process](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) sample.</span></span>  
  
## <a name="implementing-the-begintrycommand-method"></a><span data-ttu-id="a7e06-107">Implementacja metody BeginTryCommand</span><span class="sxs-lookup"><span data-stu-id="a7e06-107">Implementing the BeginTryCommand method</span></span>  
 <span data-ttu-id="a7e06-108"><xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> Wysyłany przez aparat trwałości w magazynie wystąpień.</span><span class="sxs-lookup"><span data-stu-id="a7e06-108">The <xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> is sent to the instance store by the persistence engine.</span></span> <span data-ttu-id="a7e06-109">Typ `command` parametr wskazuje, które polecenie jest wykonywane; ten parametr może być następujących typów:</span><span class="sxs-lookup"><span data-stu-id="a7e06-109">The type of the `command` parameter indicates which command is being executed; this parameter can be of the following types:</span></span>  
  
-   <span data-ttu-id="a7e06-110"><xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: Aparat trwałości wysyła tego polecenia w magazynie wystąpień, gdy przepływ pracy ma zostać utrwalony na nośniku.</span><span class="sxs-lookup"><span data-stu-id="a7e06-110"><xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: The persistence engine sends this command to the instance store when a workflow is to be persisted to the storage medium.</span></span> <span data-ttu-id="a7e06-111">Dane trwałości przepływu pracy jest przekazane do metody w <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> członkiem `command` parametru.</span><span class="sxs-lookup"><span data-stu-id="a7e06-111">The workflow persistence data is provided to the method in the <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> member of the `command` parameter.</span></span>  
  
-   <span data-ttu-id="a7e06-112"><xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: Aparat trwałości wysyła tego polecenia w magazynie wystąpień, gdy przepływ pracy ma być załadowany z nośnika magazynowania.</span><span class="sxs-lookup"><span data-stu-id="a7e06-112"><xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: The persistence engine sends this command to the instance store when a workflow is to be loaded from the storage medium.</span></span> <span data-ttu-id="a7e06-113">Identyfikator wystąpienia przepływu pracy do załadowania jest przekazane do metody w `instanceId` parametr <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> właściwość `context` parametru.</span><span class="sxs-lookup"><span data-stu-id="a7e06-113">The instance ID of the workflow to be loaded is provided to the method in the `instanceId` parameter of the <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> property of the `context` parameter.</span></span>  
  
-   <span data-ttu-id="a7e06-114"><xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>Wysyła aparat trwałości to polecenie, aby wystąpienie magazynu podczas obliczania <xref:System.ServiceModel.Activities.WorkflowServiceHost> musi być zarejestrowana jako właściciela blokady.</span><span class="sxs-lookup"><span data-stu-id="a7e06-114"><xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: The persistence engine sends this command to the instance store when a <xref:System.ServiceModel.Activities.WorkflowServiceHost> must be registered as a lock owner.</span></span> <span data-ttu-id="a7e06-115">Należy podać identyfikator wystąpienia przepływu pracy, bieżący przy użyciu magazynu wystąpienia <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> metody `context` parametru.</span><span class="sxs-lookup"><span data-stu-id="a7e06-115">The instance ID of the current workflow should be provided to the instance store using <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> method of the `context` parameter.</span></span>  
  
     <span data-ttu-id="a7e06-116">Poniższy fragment kodu przedstawia sposób wykonania polecenia CreateWorkflowOwner można przypisać właściciela blokady jawne.</span><span class="sxs-lookup"><span data-stu-id="a7e06-116">The following code snippet demonstrates how to implement the CreateWorkflowOwner command to assign an explicit lock owner.</span></span>  
  
    ```  
    XName WFInstanceScopeName = XName.Get(scopeName, "<namespace>");  
    ...  
    CreateWorkflowOwnerCommand createCommand = new CreateWorkflowOwnerCommand()  
    {  
        InstanceOwnerMetadata =  
        {  
            { WorkflowHostTypeName, new InstanceValue(WFInstanceScopeName) },  
        }  
    };  
    InstanceHandle ownerHandle = store.CreateInstanceHandle();  
    store.DefaultInstanceOwner = store.Execute(  
                                   ownerHandle,  
                                   createCommand,  
                                   TimeSpan.FromSeconds(30)).InstanceOwner;  
    childInstance.AddInitialInstanceValues(new Dictionary<XName, object>() { { WorkflowHostTypeName, WFInstanceScopeName } });  
    ```  
  
-   <span data-ttu-id="a7e06-117"><xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: Aparat trwałości wysyła tego polecenia w magazynie wystąpień, gdy właściciel blokady Identyfikatora wystąpienia może być usunięty z magazynu wystąpień.</span><span class="sxs-lookup"><span data-stu-id="a7e06-117"><xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: The persistence engine sends this command to the instance store when the instance ID of a lock owner can be removed from the instance store.</span></span> <span data-ttu-id="a7e06-118">Jak <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, identyfikator właściciela blokady powinny być dostarczone przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="a7e06-118">As with <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, the ID of the lock owner should be provided by the application.</span></span>  
  
     <span data-ttu-id="a7e06-119">Poniższy fragment kodu pokazano, jak zwolnić blokady przy użyciu <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>.</span><span class="sxs-lookup"><span data-stu-id="a7e06-119">The following code snippet demonstrates how to release a lock using <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>.</span></span>  
  
    ```  
    static void FreeHandleAndDeleteOwner(InstanceStore store, InstanceHandle handle)  
    {  
        handle.Free();  
        handle = store.CreateInstanceHandle(store.DefaultInstanceOwner);  
        try  
        {  
            // We need this sleep so that we dont prematurely delete the owner, we need time to update the database.  
            Thread.Sleep(10000);  
            store.Execute(handle, new DeleteWorkflowOwnerCommand(), TimeSpan.FromSeconds(10));  
        }  
        catch (InstancePersistenceCommandException ex) { Log.Inform(ex.Message); }  
        catch (InstanceOwnerException ex) { Log.Inform(ex.Message); }  
        catch (OperationCanceledException ex) { Log.Inform(ex.Message); }  
        catch (Exception ex) { Log.Inform(ex.Message); }  
        finally  
        {  
            handle.Free();  
            store.DefaultInstanceOwner = null;  
        }  
    }  
    ```  
  
     <span data-ttu-id="a7e06-120">Powyższej metody powinna być wywoływana w bloku Try/Catch, po uruchomieniu wystąpienia podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="a7e06-120">The above method should be called in a Try/Catch block when a child instance is run.</span></span>  
  
    ```  
    try  
    {  
        childInstance.Run();  
    }  
    catch (Exception)  
    {  
        throw ;  
    }  
    finally  
    {  
        FreeHandleAndDeleteOwner(store, ownerHandle);  
    }  
    ```  
  
-   <span data-ttu-id="a7e06-121"><xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: Gdy wystąpienia przepływu pracy ma być ładowane przy użyciu klucza wystąpienia przepływu pracy aparat trwałości wysyła do tego polecenia w magazynie wystąpień.</span><span class="sxs-lookup"><span data-stu-id="a7e06-121"><xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: The persistence engine sends this command to the instance store when a workflow instance is to be loaded using the workflow’s instance key.</span></span> <span data-ttu-id="a7e06-122">Identyfikator klucza wystąpienia można ustalić przy użyciu <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> parametru polecenia.</span><span class="sxs-lookup"><span data-stu-id="a7e06-122">The ID of the instance key can be determined by using the <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> parameter of the command.</span></span>  
  
-   <span data-ttu-id="a7e06-123"><xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: Aparat trwałości wysyła tego polecenia w magazynie wystąpień, pobrać parametrów aktywacji utrwalonych przepływów pracy, aby można było utworzyć hosta przepływu pracy, który można następnie załadować przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="a7e06-123"><xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: The persistence engine sends this command to the instance store to retrieve activation parameters for persisted workflows in order to create a workflow host that can then load workflows.</span></span> <span data-ttu-id="a7e06-124">To polecenie jest wysyłane przez aparat w odpowiedzi na wystąpienia wywoływanie magazynu <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> do hosta, gdy klient zlokalizuje wystąpienie, które może zostać uaktywniony.</span><span class="sxs-lookup"><span data-stu-id="a7e06-124">This command is sent by the engine in response to the instance store raising the <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> to the host when it locates an instance that can be activated.</span></span> <span data-ttu-id="a7e06-125">W magazynie wystąpień powinien sondowania w celu ustalenia, czy są przepływy pracy, które można aktywować.</span><span class="sxs-lookup"><span data-stu-id="a7e06-125">The instance store should be polled to determine if there are workflows that can be activated.</span></span>  
  
-   <span data-ttu-id="a7e06-126"><xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: Aparat trwałości wysyła tego polecenia w magazynie wystąpień, aby załadować wystąpienia przepływu pracy do uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="a7e06-126"><xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: The persistence engine sends this command to the instance store to load runnable workflow instances.</span></span> <span data-ttu-id="a7e06-127">To polecenie jest wysyłane przez aparat w odpowiedzi na wystąpienia wywoływanie magazynu <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> do hosta, gdy klient zlokalizuje wystąpienie, które mogą być uruchamiane.</span><span class="sxs-lookup"><span data-stu-id="a7e06-127">This command is sent by the engine in response to the instance store raising the <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> to the host when it locates an instance that can be run.</span></span> <span data-ttu-id="a7e06-128">W magazynie wystąpień powinien sondować przepływy pracy, które mogą być uruchamiane.</span><span class="sxs-lookup"><span data-stu-id="a7e06-128">The instance store should poll for workflows that can be run.</span></span> <span data-ttu-id="a7e06-129">Poniższy fragment kodu przedstawia sondowanie w magazynie wystąpień przepływów pracy, które można uruchomić lub aktywowane.</span><span class="sxs-lookup"><span data-stu-id="a7e06-129">The following code snippet demonstrates polling an instance store for workflows that can be run or activated.</span></span>  
  
    ```  
    public void PollForEvents()  
    {  
        InstanceOwner[] storeOwners = this.GetInstanceOwners();  
  
        foreach (InstanceOwner owner in storeOwners)  
        {  
            foreach (InstancePersistenceEvent ppEvent in this.GetEvents(owner))  
            {  
                if (ppEvent.Equals(HasRunnableWorkflowEvent.Value))  
                {  
                    bool hasRunnable = GetRunnableEvents(this.StoreId, owner.InstanceOwnerId, isActivable);  
                    if (hasRunnable)  
                    {  
                        this.SignalEvent(ppEvent, owner);  
                    }  
                    else  
                    {  
                        this.ResetEvent(ppEvent, owner);  
                    }  
                }  
                else if(ppEvent.Equals(HasActivatableWorkflowEvent.Value))  
                {  
                   bool hasActivable = GetActivableEvents(this.StoreId, owner.InstanceOwnerId);  
                   if (hasActivable)  
                    {  
                        this.SignalEvent(ppEvent, owner);  
                    }  
                    else  
                    {  
                        this.ResetEvent(ppEvent, owner);  
                    }  
                }  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="a7e06-130">W powyższym fragment kodu, w magazynie wystąpień kwerendy dostępnych zdarzeń i sprawdza, czy każdy z nich do określenia, czy jest <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="a7e06-130">In the above code snippet, the instance store queries the events available and examines each one to determine if it is a <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> event.</span></span> <span data-ttu-id="a7e06-131">Jeśli został znaleziony, <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> jest wywoływana w celu wysłania polecenia w magazynie wystąpień hosta.</span><span class="sxs-lookup"><span data-stu-id="a7e06-131">If one is found, <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> is called to signal the host to send a command to the instance store.</span></span>  <span data-ttu-id="a7e06-132">Poniższy fragment kodu przedstawia implementację programu obsługi dla tego polecenia.</span><span class="sxs-lookup"><span data-stu-id="a7e06-132">The following code snippet demonstrates an implementation of a handler for this command.</span></span>  
  
    ```  
    If (command is TryLoadRunnableWorkflowCommand)  
    {  
        Owner owner;  
        CheckOwner(context, command.Name, out owner);                          
        // Checking instance.Owner is like an InstanceLockQueryResult.  
        context.QueriedInstanceStore(new InstanceLockQueryResult(context.InstanceView.InstanceId, context.InstanceView.InstanceOwner.InstanceOwnerId));  
  
        XName ownerService = null;  
        InstanceValue value;  
        Instance runnableInstance = default(Instance);  
        bool foundRunnableInstance = false;  
  
        value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, owner.Data);  
        if (value != null && value.Value is XName)  
        {  
            ownerService = (XName)value.Value;  
        }  
  
        foreach (KeyValuePair<Guid, Instance> instance in MemoryStore.instances)  
        {  
            if (instance.Value.Owner != Guid.Empty || instance.Value.Completed)  
            {  
                continue;  
            }  
  
            if (ownerService != null)  
            {  
                value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, instance.Value.Metadata);  
                if (value == null || ((XName)value.Value) != ownerService)  
                {  
                    continue;  
                }  
            }  
  
            value = QueryPropertyBag(WorkflowServiceNamespace.SuspendReason, instance.Value.Metadata);  
            if (value != null && value.Value != null && value.Value is string)  
            {  
                continue;  
            }  
  
            value = QueryPropertyBag(WorkflowNamespace.Status, instance.Value.Data);  
            if (value != null && value.Value is string && ((string)value.Value) == "Executing")  
            {  
                runnableInstance = instance.Value;  
                foundRunnableInstance = true;  
            }  
  
            if (!foundRunnableInstance)  
            {  
                value = QueryPropertyBag(XNamespace.Get("urn:schemas-microsoft-com:System.Activities/4.0/properties").GetName("TimerExpirationTime"), instance.Value.Data);  
                if (value != null && value.Value is DateTime && ((DateTime)value.Value) <= DateTime.UtcNow)  
                {                          
                    runnableInstance = instance.Value;  
                    foundRunnableInstance = true;  
                }  
            }  
  
            if (foundRunnableInstance)  
            {  
                runnableInstance.LockVersion++;  
                runnableInstance.Owner = context.InstanceView.InstanceOwner.InstanceOwnerId;  
                MemoryStore.instances[instance.Key] = runnableInstance;  
                context.BindInstance(instance.Key);  
                context.BindAcquiredLock(runnableInstance.LockVersion);  
  
                Dictionary<Guid, IDictionary<XName, InstanceValue>> associatedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();  
                Dictionary<Guid, IDictionary<XName, InstanceValue>> completedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();  
                foreach (KeyValuePair<Guid, Key> keyEntry in MemoryStore.keys)  
                {  
                if (keyEntry.Value.Instance == context.InstanceView.InstanceId)  
                {  
                    if (keyEntry.Value.Completed)  
                    {  
                        completedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));  
                    }  
                    else  
                    {  
                        associatedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));  
                    }  
                }  
            }  
  
            context.LoadedInstance(InstanceState.Initialized, DeserializePropertyBag(runnableInstance.Data), DeserializePropertyBag(runnableInstance.Metadata), associatedKeys, completedKeys);  
            break;  
        }  
    }  
    ```  
  
     <span data-ttu-id="a7e06-133">W powyższym fragment kodu do uruchomienia wystąpień wyszukuje w magazynie wystąpień.</span><span class="sxs-lookup"><span data-stu-id="a7e06-133">In the above code snippet, the instance store searches for runnable instances.</span></span> <span data-ttu-id="a7e06-134">Jeśli wystąpienie zostanie wykryte, jest on powiązany z kontekstu wykonywania i załadowane.</span><span class="sxs-lookup"><span data-stu-id="a7e06-134">If an instance is found, it is bound to the execution context and loaded.</span></span>  
  
## <a name="using-a-custom-instance-store"></a><span data-ttu-id="a7e06-135">Za pomocą magazynu niestandardowego wystąpienia</span><span class="sxs-lookup"><span data-stu-id="a7e06-135">Using a custom instance store</span></span>  
 <span data-ttu-id="a7e06-136">Aby zaimplementować magazynu niestandardowego wystąpienia, przypisz wystąpienie w magazynie wystąpień, aby <xref:System.Activities.WorkflowApplication.InstanceStore%2A>i wdrożenie <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="a7e06-136">To implement a custom instance store, assign an instance of the instance store to the <xref:System.Activities.WorkflowApplication.InstanceStore%2A>, and implement the <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> method.</span></span>  <span data-ttu-id="a7e06-137">Zobacz [porady: tworzenie i uruchamianie długiego przepływu pracy z](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) samouczka, aby uzyskać szczegóły.</span><span class="sxs-lookup"><span data-stu-id="a7e06-137">See the [How to: Create and Run a Long Running Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) tutorial for specifics.</span></span>  
  
## <a name="a-sample-instance-store"></a><span data-ttu-id="a7e06-138">Magazyn wystąpienia próbki</span><span class="sxs-lookup"><span data-stu-id="a7e06-138">A sample instance store</span></span>  
 <span data-ttu-id="a7e06-139">Poniższy przykładowy kod jest pełne wystąpienie Implementacja magazynu, z [firmowej procesu zakupu](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) próbki.</span><span class="sxs-lookup"><span data-stu-id="a7e06-139">The following code sample is a complete instance store implementation, taken from the [Corporate Purchase Process](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) sample.</span></span> <span data-ttu-id="a7e06-140">Ten magazyn wystąpienia utrzymuje dane przepływu pracy w pliku za pomocą XML.</span><span class="sxs-lookup"><span data-stu-id="a7e06-140">This instance store persists workflow data to a file using XML.</span></span>  
  
```  
using System;  
using System.Activities.DurableInstancing;  
using System.Collections.Generic;  
using System.IO;  
using System.Runtime.DurableInstancing;  
using System.Runtime.Serialization;  
using System.ServiceModel.Persistence;  
using System.Xml;  
using System.Xml.Linq;  
  
namespace Microsoft.Samples.WF.PurchaseProcess  
{  
  
    public class XmlWorkflowInstanceStore : InstanceStore  
    {  
        Guid ownerInstanceID;  
  
        public XmlWorkflowInstanceStore() : this(Guid.NewGuid())  
        {  
  
        }  
  
        public XmlWorkflowInstanceStore(Guid id)  
        {  
            ownerInstanceID = id;  
        }  
  
        //Synchronous version of the Begin/EndTryCommand functions  
        protected override bool TryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout)  
        {  
            return EndTryCommand(BeginTryCommand(context, command, timeout, null, null));  
        }  
  
        //The persistence engine will send a variety of commands to the configured InstanceStore,  
        //such as CreateWorkflowOwnerCommand, SaveWorkflowCommand, and LoadWorkflowCommand.  
        //This method is where we will handle those commands  
        protected override IAsyncResult BeginTryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout, AsyncCallback callback, object state)  
        {  
            IDictionary<XName, InstanceValue> data = null;  
  
            //The CreateWorkflowOwner command instructs the instance store to create a new instance owner bound to the instanace handle  
            if (command is CreateWorkflowOwnerCommand)  
            {  
                context.BindInstanceOwner(ownerInstanceID, Guid.NewGuid());  
            }  
            //The SaveWorkflow command instructs the instance store to modify the instance bound to the instance handle or an instance key  
            else if (command is SaveWorkflowCommand)  
            {  
                SaveWorkflowCommand saveCommand = (SaveWorkflowCommand)command;  
                data = saveCommand.InstanceData;  
  
                Save(data);  
            }  
            //The LoadWorkflow command instructs the instance store to lock and load the instance bound to the identifier in the instance handle  
            else if (command is LoadWorkflowCommand)  
            {  
                string fileName = IOHelper.GetFileName(this.ownerInstanceID);  
  
                try  
                {  
                    using (FileStream inputStream = new FileStream(fileName, FileMode.Open))  
                    {  
                        data = LoadInstanceDataFromFile(inputStream);  
                        //load the data into the persistence Context  
                        context.LoadedInstance(InstanceState.Initialized, data, null, null, null);  
                    }  
                }  
                catch (Exception exception)  
                {  
                    throw new PersistenceException(exception.Message);  
                }  
            }  
  
            return new CompletedAsyncResult<bool>(true, callback, state);  
        }  
  
        protected override bool EndTryCommand(IAsyncResult result)  
        {  
            return CompletedAsyncResult<bool>.End(result);  
        }  
  
        //Reads data from xml file and creates a dictionary based off of that.  
        IDictionary<XName, InstanceValue> LoadInstanceDataFromFile(Stream inputStream)  
        {  
            IDictionary<XName, InstanceValue> data = new Dictionary<XName, InstanceValue>();  
  
            NetDataContractSerializer s = new NetDataContractSerializer();  
  
            XmlReader rdr = XmlReader.Create(inputStream);  
            XmlDocument doc = new XmlDocument();  
            doc.Load(rdr);  
  
            XmlNodeList instances = doc.GetElementsByTagName("InstanceValue");  
            foreach (XmlElement instanceElement in instances)  
            {  
                XmlElement keyElement = (XmlElement)instanceElement.SelectSingleNode("descendant::key");  
                XName key = (XName)DeserializeObject(s, keyElement);  
  
                XmlElement valueElement = (XmlElement)instanceElement.SelectSingleNode("descendant::value");  
                object value = DeserializeObject(s, valueElement);  
                InstanceValue instVal = new InstanceValue(value);  
  
                data.Add(key, instVal);  
            }  
  
            return data;  
        }  
  
        object DeserializeObject(NetDataContractSerializer serializer, XmlElement element)  
        {  
            object deserializedObject = null;  
  
            MemoryStream stm = new MemoryStream();  
            XmlDictionaryWriter wtr = XmlDictionaryWriter.CreateTextWriter(stm);  
            element.WriteContentTo(wtr);  
            wtr.Flush();  
            stm.Position = 0;  
  
            deserializedObject = serializer.Deserialize(stm);  
  
            return deserializedObject;  
        }  
  
        //Saves the persistence data to an xml file.  
        void Save(IDictionary<XName, InstanceValue> instanceData)  
        {  
            string fileName = IOHelper.GetFileName(this.ownerInstanceID);  
            XmlDocument doc = new XmlDocument();  
            doc.LoadXml("<InstanceValues/>");  
  
            foreach (KeyValuePair<XName,InstanceValue> valPair in instanceData)  
            {  
                XmlElement newInstance = doc.CreateElement("InstanceValue");  
  
                XmlElement newKey = SerializeObject("key", valPair.Key, doc);  
                newInstance.AppendChild(newKey);  
  
                XmlElement newValue = SerializeObject("value", valPair.Value.Value, doc);  
                newInstance.AppendChild(newValue);  
  
                doc.DocumentElement.AppendChild(newInstance);  
            }  
            doc.Save(fileName);  
       }  
  
        XmlElement SerializeObject(string elementName, object o, XmlDocument doc)  
        {  
            NetDataContractSerializer s = new NetDataContractSerializer();  
            XmlElement newElement = doc.CreateElement(elementName);  
            MemoryStream stm = new MemoryStream();  
  
            s.Serialize(stm, o);  
            stm.Position = 0;  
            StreamReader rdr = new StreamReader(stm);  
            newElement.InnerXml = rdr.ReadToEnd();  
  
            return newElement;  
        }  
    }  
}  
```