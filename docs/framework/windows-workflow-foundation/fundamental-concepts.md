---
title: Windows podstawowych koncepcji przepływu pracy
ms.date: 03/30/2017
ms.assetid: 0e930e80-5060-45d2-8a7a-95c0690105d4
ms.openlocfilehash: c5306f8616086835373bc52bdd8195564441b8b7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="fundamental-windows-workflow-concepts"></a>Windows podstawowych koncepcji przepływu pracy
Programowanie przepływu pracy w [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] używa pojęcia, które mogą być nowe dla niektórych deweloperów. W tym temacie opisano niektóre z pojęć i ich implementacji.  
  
## <a name="workflows-and-activities"></a>Przepływy pracy i działań  
 Przepływ pracy jest strukturalnych kolekcję akcji, która modele procesu. Każdego działania w przepływie pracy jest modelowana jako działania. Host współdziała z przepływu pracy przy użyciu <xref:System.Activities.WorkflowInvoker> do wywoływania przepływu pracy, tak jakby był on metodę, <xref:System.Activities.WorkflowApplication> jawne kontrolować wykonywanie wystąpienia przepływu pracy pojedynczego, i <xref:System.ServiceModel.WorkflowServiceHost> oparta na komunikatach interakcji w wielu wystąpieniach scenariusze. Ponieważ kroki przepływu pracy są zdefiniowane jako hierarchię działań, działanie najwyższego poziomu w hierarchii można powiedzieć do definiowania sam przepływ pracy. Ten model hierarchii ma miejsce jawne `SequentialWorkflow` i `StateMachineWorkflow` klasy z poprzedniej wersji. Działania sami są tworzone jako kolekcje innych działań (przy użyciu <xref:System.Activities.Activity> klasy jako podstawa, zazwyczaj definiowane przy użyciu języka XAML) lub są tworzone za pomocą niestandardowych <xref:System.Activities.CodeActivity> klasy, którego można użyć środowiska uruchomieniowego dla dostępu do danych lub za pomocą <xref:System.Activities.NativeActivity> klasy, która przedstawia szerokość określony przez autora działania środowiska uruchomieniowego przepływu pracy. Działań utworzonych za pomocą <xref:System.Activities.CodeActivity> i <xref:System.Activities.NativeActivity> są tworzone za pomocą zgodne CLR języków, takich jak C#.  
  
## <a name="activity-data-model"></a>Model danych działania  
 Działania przechowywać i udostępniać dane przy użyciu typów pokazano w poniższej tabeli.  
  
|||  
|-|-|  
|Zmienna|Przechowuje dane w działaniu.|  
|Argument|Przenosi dane do i z działania.|  
|Wyrażenie|Działanie z podwyższonym poziomem uprawnień, zwracając wartość używana w powiązaniach argumentu.|  
  
## <a name="workflow-runtime"></a>Środowiska uruchomieniowego przepływu pracy  
 Środowisko wykonawcze przepływu pracy jest środowisko, w którym wykonania przepływów pracy. <xref:System.Activities.WorkflowInvoker> to najprostszy sposób wykonania przepływu pracy. Host używa <xref:System.Activities.WorkflowInvoker> dla następujących:  
  
-   Aby wywołać synchronicznie przepływ pracy.  
  
-   Podaj dane wejściowe lub pobrać dane wyjściowe z przepływu pracy.  
  
-   Aby dodać rozszerzenia do użycia przez działania.  
  
 <xref:System.Activities.ActivityInstance> to proxy wątkowo, który hostów można użyć do interakcji z środowiska uruchomieniowego. Host używa <xref:System.Activities.ActivityInstance> dla następujących:  
  
-   Uzyskanie wystąpienia przez go utworzyć lub załadować go ze sklepu wystąpienia.  
  
-   Aby otrzymywać powiadomienia wystąpienia zdarzeń cyklu życia.  
  
-   Aby kontrolować wykonywanie przepływu pracy.  
  
-   Podaj dane wejściowe lub pobrać dane wyjściowe z przepływu pracy.  
  
-   Sygnał kontynuacji przepływu pracy i wartości przekazywane do przepływu pracy.  
  
-   Aby zachować dane przepływu pracy.  
  
-   Aby dodać rozszerzenia do użycia przez działania.  
  
 Działania uzyskania dostępu do środowiska uruchomieniowego przepływu pracy przy użyciu odpowiednich <xref:System.Activities.ActivityContext> pochodnej klasy, takich jak <xref:System.Activities.NativeActivityContext> lub <xref:System.Activities.CodeActivityContext>. Używają to rozpoznawania argumentów i zmienne, do planowania działań podrzędnych i do innych celów.  
  
## <a name="services"></a>Usługi  
 Przepływy pracy umożliwiają fizyczne do wdrożenia i uzyskiwać dostęp do usług luźno połączonych, przy użyciu działań komunikacji. Działania obsługi komunikatów są tworzone na WCF i to podstawowy mechanizm używany do pobierania danych do i z przepływu pracy. Można utworzyć działania obsługi wiadomości ze sobą w celu modelowania dowolnego rodzaju wymiany komunikatów, które mają. Aby uzyskać więcej informacji, zobacz zobacz [wiadomości działania](../../../docs/framework/wcf/feature-details/messaging-activities.md). Usługi przepływu pracy są obsługiwane przy użyciu <xref:System.ServiceModel.Activities.WorkflowServiceHost> klasy. Aby uzyskać więcej informacji, zobacz [Hosting przegląd usług przepływu pracy](../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md). Aby uzyskać więcej informacji na temat usług przepływu pracy zobacz [usług przepływu pracy](../../../docs/framework/wcf/feature-details/workflow-services.md)  
  
## <a name="persistence-unloading-and-long-running-workflows"></a>Przepływy pracy zwalniania i długotrwałe trwałości,  
 Windows Workflow upraszcza tworzenie programów czynnych długotrwałe zapewniając:  
  
-   Działania, które uzyskują dostęp do zewnętrznych danych wejściowych.  
  
-   Możliwość tworzenia <xref:System.Activities.Bookmark> obiektów, które można wznowić przez odbiornik hosta.  
  
-   Zdolność do utrwalenia danych przepływu pracy i zwolnienia przepływu pracy, Załaduj ponownie i Uaktywnij ponownie przepływu pracy w odpowiedzi na wznowienie <xref:System.Activities.Bookmark> obiektów w szczególności przepływu pracy.  
  
 Przepływ pracy stale wykonuje działania, dopóki nie ma żadnych więcej działań do wykonania lub aż wszystkie aktualnie wykonywanego działania oczekuje na dane wejściowe. W tym ostatnim stanie przepływu pracy jest w stanie bezczynności. Często hosta można zwolnić przepływów pracy, które przeszły bezczynności i załadować ponownie je, aby kontynuować wykonywanie, gdy komunikat dociera. <xref:System.ServiceModel.Activities.WorkflowServiceHost> zapewnia funkcje dla tej funkcji i zawiera zasady rozszerzonego, zwolnienia. Dla bloków wykonywania korzystających z danych o stanie volatile lub innych danych, która nie może zostać utrwalona, działanie może wskazywać na hoście że nie należy go utrwalone przy użyciu <xref:System.Activities.NoPersistHandle>. Przepływ pracy można również jawnie utrwalić danych jego średni magazynu trwałego za pomocą <xref:System.Activities.Statements.Persist> działania.
