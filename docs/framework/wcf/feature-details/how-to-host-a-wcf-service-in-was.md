---
title: 'Instrukcje: Hostowanie usługi WCF w usłudze WAS'
ms.date: 03/30/2017
ms.assetid: 9e3e213e-2dce-4f98-81a3-f62f44caeb54
ms.openlocfilehash: 7050d866233b248c7c8f9f41337ce451b5510c30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-host-a-wcf-service-in-was"></a>Instrukcje: Hostowanie usługi WCF w usłudze WAS
W tym temacie wymieniono podstawowe kroki wymagane do utworzenia usługi aktywacji procesów systemu Windows (znanej także jako Usługa WAS) hostowanej usługi Windows Communication Foundation (WCF). ZOSTAŁO to nowa usługa aktywacji procesów, która jest generalizacji funkcji Internet Information Services (IIS), które współpracują z protokołów innych niż HTTP. Usługi WCF używa interfejsu adapter odbiornika do komunikowania się żądania aktywacji, które są otrzymywane za pośrednictwem protokołów innych niż HTTP obsługiwane przez usługi WCF, takich jak TCP i nazwane potoki i usługę kolejkowania komunikatów.  
  
 Ta opcja hostingu wymaga składników aktywacji WAS są prawidłowo zainstalowane i skonfigurowane, ale nie wymaga żadnego kodu macierzystego do zapisania jako części aplikacji. Aby uzyskać więcej informacji o instalowaniu i konfigurowaniu WAS, zobacz [porady: Instalowanie i konfigurowanie składników aktywacji programu WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).  
  
> [!WARNING]
>  BYŁA aktywacji nie jest obsługiwane, jeśli ustawiono potoku przetwarzania żądań serwera sieci web do trybu klasycznego. Potoku przetwarzania żądań serwera sieci web musi mieć ustawioną trybu zintegrowanego, jeśli ma być używany przez aktywację usługi WAS.  
  
 Gdy usługa WCF jest hostowana w WAS, standardowe powiązania są używane w zwykły sposób. Jednak przy użyciu <xref:System.ServiceModel.NetTcpBinding> i <xref:System.ServiceModel.NetNamedPipeBinding> skonfigurowanie usługi hostowanej WAS, muszą być spełnione ograniczenia. Korzystając z różnych punktów końcowych tego samego transportu, ustawienia powiązania musi odpowiadać na siedem następujące właściwości:  
  
-   connectionBufferSize  
  
-   limitu czasu channelInitializationTimeout  
  
-   maxPendingConnections  
  
-   maxOutputDelay  
  
-   maxPendingAccepts  
  
-   ConnectionPoolSettings.IdleTimeout  
  
-   ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint  
  
 W przeciwnym razie wartość punktu końcowego, który został zainicjowany najpierw zawsze określa wartości tych właściwości, a punkty końcowe można dodać później throw <xref:System.ServiceModel.ServiceActivationException> Jeśli nie spełniają tych ustawień.  
  
 Dla źródła kopię w tym przykładzie [Aktywacja TCP](../../../../docs/framework/wcf/samples/tcp-activation.md).  
  
### <a name="to-create-a-basic-service-hosted-by-was"></a>Aby utworzyć podstawowej usługi hostowanej przez usługę WAS  
  
1.  Definiowanie kontraktu usługi dla typu usługi.  
  
     [!code-csharp[C_HowTo_HostInWAS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1121)]  
  
2.  Implementowanie kontraktu usługi w klasie usługi. Należy pamiętać, że wewnątrz implementacji usługi nie określono informacji o adresie lub powiązanie. Ponadto kodu nie ma do zapisania do pobierania informacji z pliku konfiguracji.  
  
     [!code-csharp[C_HowTo_HostInWAS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1122)]  
  
3.  Utwórz plik Web.config, aby zdefiniować <xref:System.ServiceModel.NetTcpBinding> powiązania, które mają być używane przez `CalculatorService` punktów końcowych.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <bindings>  
          <netTcpBinding>  
            <binding portSharingEnabled="true">  
              <security mode="None" />  
            </binding>  
          </netTcpBinding>  
        </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4.  Utwórz plik Service.svc zawierający następujący kod.  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  Umieść plik Service.svc w katalogu wirtualnego usług IIS.  
  
### <a name="to-create-a-client-to-use-the-service"></a>Aby utworzyć klienta do korzystania z usługi  
  
1.  Użyj [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) z poziomu wiersza polecenia, aby wygenerować kod na podstawie metadanych usługi.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  Klient, który jest generowany zawiera `ICalculator` Interfejs definiujący kontrakt usługi, które muszą spełniać implementacja klienta.  
  
     [!code-csharp[C_HowTo_HostInWAS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1221)]  
  
3.  Aplikacja wygenerowanego klienta zawiera również implementacja `ClientCalculator`. Należy pamiętać, że informacji adres i powiązanie nie określono dowolnym wewnątrz implementacji usługi. Ponadto kodu nie ma do zapisania do pobierania informacji z pliku konfiguracji.  
  
     [!code-csharp[C_HowTo_HostInWAS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1222)]  
  
4.  Konfiguracja klienta, który używa <xref:System.ServiceModel.NetTcpBinding> również jest generowany przez Svcutil.exe. Ten plik powinien być o nazwie w pliku App.config, przy użyciu programu Visual Studio.  
  
     [!code-xml[C_HowTo_HostInWAS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/common/app.config#2211)]   
  
5.  Utwórz wystąpienie `ClientCalculator` w aplikacji, a następnie wywołać operacji usługi.  
  
     [!code-csharp[C_HowTo_HostInWAS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1223)]  
  
6.  Kompilowanie i uruchamianie klienta.  
  
## <a name="see-also"></a>Zobacz też  
 [Aktywacja TCP](../../../../docs/framework/wcf/samples/tcp-activation.md)  
 [Windows Server AppFabric funkcje hostingu](http://go.microsoft.com/fwlink/?LinkId=201276)
