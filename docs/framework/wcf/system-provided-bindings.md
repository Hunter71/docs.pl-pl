---
title: Powiązania dostarczane przez system
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], system-provided
ms.assetid: 2c243746-45ce-4588-995e-c17126a579a6
ms.openlocfilehash: 97a8e9fd8f0e2c906f14556fcdccd7ef0d3c8033
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="system-provided-bindings"></a>Powiązania dostarczane przez system
Powiązania Określ mechanizm komunikacji po rozmowie z punktu końcowego i określić sposób nawiązywania połączenia z punktem końcowym. Powiązanie zawiera następujące elementy:  
  
-   Stos protokołu określa bezpieczeństwa, niezawodności i ustawienia przepływu kontekstu dla komunikatów wysyłanych do punktu końcowego.  
  
-   Transport określa podstawowy protokół transportu podczas wysyłania komunikatów do punktu końcowego, np. TCP lub HTTP.  
  
-   Kodowanie określa przewodowy kodowanie do użycia dla wiadomości, które są wysyłane do punktu końcowego, na przykład, text/XML, binarne lub mechanizmu optymalizacji transmisji wiadomości (MTOM).  
  
 W tym temacie przedstawiono wszystkie powiązania dostarczane przez system Windows Communication Foundation (WCF). Jeśli nie spełnia żadnego z tych dokładnych kryteriów dla aplikacji, można utworzyć niestandardowego powiązania. Aby uzyskać więcej informacji o tworzeniu niestandardowych powiązań, zobacz [niestandardowego powiązania](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 Bezpieczne i interoperacyjne powiązanie, który obsługuje protokół WS-Federation umożliwia organizacjom, które znajdują się w Federacji, aby wydajnie uwierzytelniania i autoryzacji użytkowników.  
  
> [!IMPORTANT]
>  Zawsze należy wybierać powiązania, które zawiera zabezpieczenia. Domyślnie wszystkie powiązania z wyjątkiem [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elementu mieć włączoną obsługą zabezpieczeń. Jeśli nie wybierz bezpiecznego powiązania lub wyłączyć zabezpieczeń, pamiętaj chronić dane w inny sposób, takie jak przechowywania w Centrum zabezpieczonych danych lub w sieci izolowanej.  
  
> [!IMPORTANT]
>  Nigdy nie używaj kontrakty dwukierunkowe z powiązaniami, które nie obsługują zabezpieczeń lub mają wyłączony do momentu zabezpieczania danych za pomocą innych środków zabezpieczeń.  
  
## <a name="system-provided-bindings"></a>Powiązania dostarczane przez system  
 Następujące powiązania składnikiem usługi WCF.  
  
|Powiązanie|Element konfiguracji|Opis|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Powiązanie, które jest odpowiednie dla komunikacji z profilu WS-Basic zgodność usług sieci Web, na przykład usługi sieci Web platformy ASP.NET (ASMX) — na podstawie usług. To powiązanie korzysta z protokołu HTTP jako transportu i tekstu/XML jako domyślne kodowanie komunikatu.|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Bezpieczne i interoperacyjne powiązanie odpowiednie dla kontraktów na usługę non-duplex.|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Bezpieczne i interoperacyjne powiązanie odpowiednie dla kontraktów usługi duplex lub komunikacji za pośrednictwem pośredników SOAP.|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Bezpieczne i interoperacyjne powiązanie obsługuje protokół WS-Federation, która umożliwia organizacjom, które znajdują się w Federacji, aby wydajnie uwierzytelniania i autoryzacji użytkowników.|  
|<xref:System.ServiceModel.NetHttpBinding>|\<netHttpBinding >|Powiązanie przeznaczony do używania protokołu HTTP lub protokołu WebSocket usług używającej kodowanie binarne domyślnie.|  
|<xref:System.ServiceModel.NetHttpsBinding>|\<netHttpsBinding >|Bezpiecznego powiązania przeznaczony do używania protokołu HTTP lub protokołu WebSocket usług używającej kodowanie binarne domyślnie.|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Bezpieczne i zoptymalizowane powiązanie odpowiednie dla komunikacji między komputerami między aplikacjami WCF.|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)|Bezpieczne, niezawodne i zoptymalizowane powiązanie odpowiednie dla komunikacji na komputerze między aplikacjami WCF.|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Zakolejkowane powiązanie, które jest odpowiednie dla komunikacji między komputerami między aplikacjami WCF.|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)|Powiązanie, które umożliwia bezpieczne, wiele komunikacji maszyny.|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding>](../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Powiązanie, które jest odpowiednie dla komunikacji między komputerami między aplikacja WCF i istniejących aplikacji z usługą MSMQ.|  
|<xref:System.ServiceModel.BasicHttpContextBinding>|[\<Obiekt basicHttpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpcontextbinding.md)|Powiązanie, które jest odpowiednie dla komunikacji z zgodność profilu WS-Basic usług sieci Web umożliwiającą plików cookie protokołu HTTP używanego do wymiany kontekstu.|  
|<xref:System.ServiceModel.NetTcpContextBinding>|[\<netTcpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpcontextbinding.md)|Bezpieczne i zoptymalizowane powiązanie odpowiednie dla komunikacji między komputerami między aplikacjami WCF, który umożliwia nagłówki SOAP używanego do wymiany kontekstu.|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Wiązanie używane do konfigurowania punktów końcowych dla usług sieci Web WCF, które są dostępne za pośrednictwem żądania HTTP zamiast na wiadomości SOAP.|  
|<xref:System.ServiceModel.WSHttpContextBinding>|[\<wsHttpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpcontextbinding.md)|Bezpieczny i |<xref:System.ServiceModel.UdpBinding>|\<udpBinding >|Wiązanie używane podczas wysyłania serii proste wiadomości do wielu klientów jednocześnie.|  
  
 W poniższej tabeli przedstawiono funkcje każdego powiązania dostarczane przez system. Powiązania znajdują się w kolumnach tabeli; funkcje są wyświetlane w wierszach i opisane w drugiej tabeli. Poniższa tabela zawiera klucz, skróty powiązanie użyte. Aby wybrać powiązanie, określić kolumnę, która spełnia wszystkie potrzebne funkcje wiersza.  
  
|Powiązanie|Współdziałanie|Zabezpieczenia (ustawienie domyślne)|Sesja<br /><br /> (Domyślnie)|Transakcje|Dupleks|Kodowania (ustawienie domyślne)|przesyłanie strumieniowe<br /><br /> (Domyślnie)|  
|-------------|----------------------|--------------------------|-----------------------------|------------------|------------|--------------------------|-------------------------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(Brak), Transport, wiadomości, mieszany|(Brak)|(Brak)|n/d|Tekst, (MTOM)|Tak<br /><br /> (buforowanej)|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|Mieszane transportu, (komunikat)|(Brak), niezawodnej sesji, sesja zabezpieczeń|Tak (Brak)|n/d|(Tekst), MTOM|Nie|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|(Komunikat), Brak|(Niezawodnej sesji), sesja zabezpieczeń|Tak (Brak)|Tak|(Tekst), MTOM|Nie|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|(Komunikat), mieszany, Brak|(Brak), niezawodnej sesji, sesja zabezpieczeń|Tak (Brak)|Nie|(Tekst), MTOM|Nie|  
|<xref:System.ServiceModel.NetHttpBinding>|.NET|(Brak), Transport, wiadomości, TransportWithMessageCredential, TransportCredentialOnly|Zobacz Uwaga poniżej|Brak|Zobacz Uwaga poniżej|(Binarnego), tekst, MTOM|Tak (buforowanej)|  
|<xref:System.ServiceModel.NetHttpsBinding>|.NET|(Transportu), TransportWithMessageCredential|Zobacz Uwaga poniżej|Brak|Zobacz Uwaga poniżej|(Binarnego), tekst, MTOM|Tak (buforowanej)|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|(Transportu), mieszanym wiadomości, None,|(Transportu), niezawodnej sesji, sesja zabezpieczeń|Tak (Brak)|Tak|plików binarnych|Tak<br /><br /> (buforowanej)|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|(Transportu), Brak|Brak (transportu)|Tak (Brak)|Tak|plików binarnych|Tak<br /><br /> (buforowanej)|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Komunikat (transportu), Brak|(Brak), transportu|Brak (tak)|Nie|plików binarnych|Nie|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|elementów równorzędnych|(Transportu)|(Brak)|(Brak)|Tak||Nie|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|Usługa MSMQ|(Transportu)|(Brak)|Brak (tak)|n/d|n/d|Nie|  
|<xref:System.ServiceModel.BasicHttpContextBinding>|Basic Profile 1.1|(Brak), Transport, wiadomości, mieszany|(Brak)|(Brak)|n/d|Tekst, (MTOM)|Tak<br /><br /> (buforowanej)|  
|<xref:System.ServiceModel.NetTcpContextBinding>|.NET|(Transportu), mieszanym wiadomości, None,|(Transportu), niezawodnej sesji, sesja zabezpieczeń|Tak (Brak)|Tak|plików binarnych|Tak<br /><br /> (buforowanej)|  
|<xref:System.ServiceModel.WSHttpContextBinding>|WS|Mieszane transportu, (komunikat)|(Brak), niezawodnej sesji, sesja zabezpieczeń|Tak (Brak)|n/d|Tekst, (MTOM)|Nie|  
|<xref:System.ServiceModel.UdpBinding>|.NET **Uwaga:** współdziałanie można osiągnąć poprzez wdrożenie standardowe specyfikacji SOAP-over-UDP, która implementuje tego powiązania.|(Brak)|(Brak)|(Brak)|n/d|(Tekst)|Nie|  
  
> [!IMPORTANT]
>  <xref:System.ServiceModel.NetHttpBinding> jest przeznaczony do używania protokołu HTTP lub protokołu WebSocket usług powiązania i używa kodowanie binarne domyślnie. <xref:System.ServiceModel.NetHttpBinding> wykryje, czy jest używana z kontraktu "żądanie-odpowiedź" lub kontraktu dwukierunkowego i zmianę jego zachowania, aby dopasować — zostanie użyty dla dupleks HTTP dla żądanie odpowiedź i technologia WebSockets. To zachowanie można przesłonić przy użyciu <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A>--> `System.ServiceModel.NetHttpBinding.WebSocketTransportUsage` powiązanie ustawienie: dozwolone — jest to wartość domyślna i działa zgodnie z powyższym opisem. NotAllowed — uniemożliwia to Websocket używana. Podjęto próbę użycia kontraktu dwukierunkowego tego ustawienia spowoduje Wystąpił wyjątek. Wymagana — wymusza Websocket do użycia nawet w przypadku kontraktów "żądanie-odpowiedź". NetHttpBinding obsługuje zarówno w trybie HTTP, jak i w trybie protokołu WebSocket niezawodnej sesji. W WebSocket tryb sesji są dostarczane przez transport.  
  
 W poniższej tabeli przedstawiono funkcje wymienione w powyższej tabeli.  
  
|Funkcja|Opis|  
|-------------|-----------------|  
|Typ współdziałanie|Nazwy protokołu lub technologii, z którym powiązania zapewnia współdziałanie.|  
|Zabezpieczenia|Określa, jak chronione są kanału:<br /><br /> -Brak: Wiadomości protokołu SOAP nie jest zabezpieczony, a klient nie jest uwierzytelniony.<br />-Transport: Spełnione są wymagania dotyczące zabezpieczeń w warstwie transportowej.<br />-Komunikat o błędzie: Spełnione są wymagania dotyczące zabezpieczeń w warstwie wiadomości.<br />-Mieszane: Oświadczeń odbywa się w komunikacie; wymagania dotyczące integralności i poufności informacji są spełnione przez warstwę transportu.|  
|Sesja|Określa, czy to powiązanie obsługuje kontrakty sesji.|  
|Transakcje|Określa, czy transakcje są włączone.|  
|Dupleks|Określa, czy kontrakty dwukierunkowe są obsługiwane. Należy pamiętać, ta funkcja wymaga obsługi dla sesji w powiązaniu.|  
|Kodowanie|Określa format przesyłania wiadomości. Dozwolone wartości:<br /><br /> -Tekst: na przykład UTF-8.<br />-Binarne<br />-Mechanizmu optymalizacji transmisji wiadomości (MTOM): Metoda efektywne kodowanie binarne elementów XML w kontekście koperty protokołu SOAP.|  
|przesyłanie strumieniowe|Określa, czy przesyłanie strumieniowe jest obsługiwane dla komunikatów przychodzących i wychodzących. Użyj `TransferMode` powiązania, które można ustawić wartości właściwości. Dozwolone wartości:<br /><br /> -   <xref:System.ServiceModel.TransferMode.Buffered>: Komunikaty żądań i odpowiedzi zarówno buforowana.<br />-   <xref:System.ServiceModel.TransferMode.Streamed>: Komunikaty żądań i odpowiedzi zarówno strumieniowo.<br />-   <xref:System.ServiceModel.TransferMode.StreamedRequest>: Komunikat żądania jest przesyłane strumieniowo i komunikat odpowiedzi są buforowane.<br />-   <xref:System.ServiceModel.TransferMode.StreamedResponse>: Komunikat żądania są buforowane, a komunikat odpowiedzi przesyłanej strumieniowo.|  
  
## <a name="see-also"></a>Zobacz też  
 [Przegląd tworzenia punktów końcowych](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Konfigurowanie usług i klientów za pomocą powiązań](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Podstawy programowania przy użyciu programu WCF](../../../docs/framework/wcf/basic-wcf-programming.md)
