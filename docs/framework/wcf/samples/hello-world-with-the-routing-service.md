---
title: Program Hello World z usługą routingu
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 881636097cf342de09164804c6df6acfbcd97c45
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="hello-world-with-the-routing-service"></a>Program Hello World z usługą routingu
W tym przykładzie pokazano, usługa routingu Windows Communication Foundation (WCF). Usługa routingu jest składnikiem usługi WCF, który ułatwia obejmują routerem na podstawie zawartości w aplikacji. W tym przykładzie dostosowuje standardowej próbki Kalkulator WCF do komunikowania się przy użyciu usługi routingu. W tym przykładzie klient Kalkulator jest skonfigurowany do wysyłania komunikatów do punktu końcowego udostępnianych przez router. Usługa routingu jest skonfigurowany do akceptowania wszystkich wiadomości wysłanych do niego i przekazują je do punktu końcowego, który odpowiada usługi Kalkulator. W związku z tym komunikatów wysłanych z klienta są odbierane przez router i skierowane do rzeczywistego usługi Kalkulator. Komunikaty z usługi Kalkulator są wysyłane do routera, który z kolei przekazuje je do Kalkulatora klienta.  
  
### <a name="to-use-this-sample"></a>Aby użyć tego przykładu  
  
1.  Przy użyciu [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], otwórz HelloRoutingService.sln.  
  
2.  Naciśnij klawisz F5 lub CTRL + SHIFT + B.  
  
    > [!NOTE]
    >  Jeśli zostanie naciśnięty klawisz F5, klient Kalkulator jest uruchamiana automatycznie. Po naciśnięciu klawiszy CTRL + SHIFT + B (Kompilacja), należy uruchomić następujące aplikacje samodzielnie.  
    >   
    >  1.  Kalkulator klienta (./CalculatorClient/bin/client.exe  
    > 2.  Usługa kalkulatora (. / CalculatorService/bin/service.exe)  
    > 3.  Usługa routingu (. / RoutingService/bin/RoutingService.exe)  
  
3.  Naciśnij klawisz ENTER, aby uruchomić klienta.  
  
     Powinny być widoczne następujące dane wyjściowe:  
  
     Add(100,15.99) = 115.99  
  
     SUBTRACT(145,76.54) = 68.46  
  
     MULTIPLY(9,81.25) = 731.25  
  
     Divide(22,7) = 3.14285714285714  
  
## <a name="configurable-via-code-or-appconfig"></a>Można konfigurować za pomocą kodu lub pliku App.Config  
 Jest skonfigurowany do używania pliku App.config do definiowania zachowania routera dostarczany próbki. Można również zmienić nazwę pliku App.config do innego elementu tak, aby nie został rozpoznany i Usuń komentarz wywołanie metody ConfigureRouterViaCode(). Każda z tych metod powoduje takie samo zachowanie z routera.  
  
### <a name="scenario"></a>Scenariusz  
 W przykładzie pokazano router działający jako pompa podstawowe wiadomości. Usługa routingu działa jako węzeł przezroczystego obiektu pośredniczącego skonfigurowane do przekazywania wiadomości bezpośrednio do zbioru wstępnie skonfigurowane miejsce docelowe punktów końcowych.  
  
### <a name="real-world-scenario"></a>Scenariusz rzeczywistych  
 Firma Contoso chce zwiększyć elastyczność, który ma w nazewnictwa, adresy, konfiguracji i zabezpieczeń w usługach. Aby to zrobić, umieść one pompowania podstawowe komunikatów przed ich usług do działania jako publiczny punkt końcowy połączonej. Pozwala na umieszczenie dodatkowe zabezpieczenia przed ich rzeczywiste usługi i ułatwić do zaimplementowania Skalowanie rozwiązań lub przechowywanie wersji usługi później.  
  
> [!IMPORTANT]
>  Próbki mogą być zainstalowane na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) do pobrania wszystkich Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a>Zobacz też  
 [Przykłady trwałości i hostingu AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)
