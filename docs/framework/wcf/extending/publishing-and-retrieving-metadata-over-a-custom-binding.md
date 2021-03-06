---
title: Publikowanie i pobieranie metadanych za pośrednictwem powiązania niestandardowego
ms.date: 03/30/2017
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
ms.openlocfilehash: 528f7662ee3a1f956427e5e42f540816f55027f8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>Publikowanie i pobieranie metadanych za pośrednictwem powiązania niestandardowego
<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> Umożliwia dodawanie punktu końcowego metadanych do usługi. Te punkty końcowe metadanych może odpowiadać na żądania HTTP GET pod adresem URL, który ma `?wsdl` querystring i na żądanie GET usługi WS-Transfer zgodnie z definicją w specyfikacji WS-MetadataExchange (MEX). Punkty końcowe MEX zaimplementować <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType> kontraktu.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>Publikowanie metadanych za pośrednictwem powiązania niestandardowego  
 Punkty końcowe metadanych GET protokołu HTTP i HTTPS GET punkty końcowe metadanych są włączone przez ustawienie <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType> lub <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType> właściwości `true`. Nie można skonfigurować powiązania z tymi punktami końcowymi.  
  
 <xref:System.ServiceModel.Description.IMetadataExchange> Kontraktu, jednak może być używany z dowolnego punktu końcowego, w tym tych, które korzystają z niestandardowego powiązania, ponieważ <xref:System.ServiceModel.Description.IMetadataExchange> punkty końcowe są identyczne z innych punktów końcowych usługi Windows Communication Foundation (WCF). Jeśli wiesz, jak do modyfikacji konfiguracji powiązania dostarczane przez system, lub wiesz, jak skonfigurować <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>, a następnie można skonfigurować powiązania do użycia z <xref:System.ServiceModel.Description.IMetadataExchange> punktu końcowego.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>Pobieranie metadanych za pośrednictwem powiązania niestandardowego  
 Można pobrać metadanych od Get protokołu HTTP i HTTPS Get punkty końcowe metadanych przy użyciu standardowych żądań HTTP lub HTTPS GET.  
  
 Aby pobrać metadane z punktu końcowego MEX metadanych zazwyczaj można użyć jednej z standardowe powiązania MEX. obsługiwane przez usługę WCF. Aby uzyskać więcej informacji, zobacz <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> Typu i z narzędzia Svcutil.exe automatycznie wybierz jedną z tych standardowe powiązań MEX na podstawie adresu punktu końcowego określonych metadanych.  
  
 Jeśli punkt końcowy metadanych MEX używa inne powiązanie niż standardowe powiązania MEX., można skonfigurować powiązania, używany przez <xref:System.ServiceModel.Description.MetadataExchangeClient> przy użyciu kodu lub przez podanie <xref:System.ServiceModel.Description.IMetadataExchange> konfiguracji punktu końcowego klienta. Narzędzia Svcutil.exe automatycznie ładuje z plikiem konfiguracji <xref:System.ServiceModel.Description.IMetadataExchange> konfiguracji punktu końcowego klienta, który ma taką samą nazwę jak schemat identyfikatora URI dla adresu punktu końcowego metadanych.  
  
## <a name="security"></a>Zabezpieczenia  
 Podczas publikowania metadanych za pośrednictwem powiązania niestandardowego, upewnij się, że powiązanie zawiera obsługi zabezpieczeń, która wymaga metadanych. Na przykład, aby zapobiec ujawnieniu informacji i upewnij się, klient ma prawo do uzyskania metadanych, można wprowadzeniu metadanych i aplikacji bezpieczniejsze przez skonfigurowanie sieci <xref:System.ServiceModel.Description.IMetadataExchange> punktu końcowego, aby wymagać uwierzytelniania i szyfrowania. Przykład [punktu końcowego metadanych niestandardowy bezpieczny](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) pokazano, w tym scenariuszu.  
  
## <a name="see-also"></a>Zobacz też  
 [Zabezpieczanie usług](../../../../docs/framework/wcf/securing-services.md)  
 [Powiązania elementu WS-MetadataExchange](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)  
 [Instrukcje: konfigurowanie niestandardowego powiązania WS-Metadata Exchange](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [Instrukcje: pobieranie metadanych przez powiązanie inne niż wymiany metadanych](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
