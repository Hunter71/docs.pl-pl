---
title: 100 - WorkflowInstanceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed4d1851-b378-489b-a22d-c1db09571fb4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e60b972c015bd7f3ec304c83e03812e2460b8ca3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2017
---
# <a name="100---workflowinstancerecord"></a>100 - WorkflowInstanceRecord
## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|Identyfikator|100|  
|Słowa kluczowe|EndToEndMonitoring rozwiązywania problemów, HealthMonitoring, WFTracking|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows aplikacji Server aplikacje/analityczne|  
  
## <a name="description"></a>Opis  
 To zdarzenie jest emitowane przez uczestnika śledzenia zdarzeń systemu Windows, gdy wystąpienia przepływu pracy emituje WorkflowInstanceRecord dla stanów przepływu pracy: rozpoczęto wznowione, utrwalone, w stanie bezczynności, usunięty, zakończona, anulowana, zwalnianie, Anulowano.  
  
## <a name="message"></a>Komunikat  
 TrackRecord = WorkflowInstanceRecord, identyfikator wystąpienia = %1, RecordNumber = %2, EventTime = %3, obiekt ActivityDefinitionId = %4, stan = %5, adnotacje = %6, ProfileName = %7  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Identyfikator wystąpienia|xs:GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|xs:Long|Numer sekwencyjny emitowany rekordu|  
|eventTime|xs: DateTime|Godzina w formacie UTC podczas zdarzenia zostały wyemitowane|  
|Obiekt ActivityDefinitionId|xs:String|Nazwa działania głównego w przepływie pracy|  
|Stan|xs:String|Bieżący stan przepływu pracy.|  
|Adnotacje|xs:String|Adnotacje, które zostały dodane do tego zdarzenia.  Wartości są przechowywane w elemencie xml w formacie \<elementy >\< nazwa elementu = "annotationName" type="System.String" > annotationValue\</elementu > \< /elementy >.  Jeśli nie określono bez adnotacji, a następnie ciąg zawiera \<elementów / >. Rozmiar zdarzenia ETW jest ograniczona przez rozmiar bufora ETW lub max ładunku zdarzenia ETW. Jeśli limity ETW przekracza rozmiar zdarzenia, a następnie zdarzenia został obcięty przez usunięcie adnotacje i zastąpienie wartości adnotacji z \<elementy >...  \< /elementy >.|  
|ProfileName|xs:String|Nazwa lub profilu śledzenia, które spowodowały to zdarzenie jest emitowany|  
|HostReference|xs:String|Dla usług sieci web hostowanych w tym polu unikatowo identyfikuje usługę w hierarchii sieci web.  Jego format jest zdefiniowany jako "Ścieżka wirtualna aplikacji Nazwa witryny sieci Web &#124; Ścieżka wirtualna usługi &#124; ServiceName "przykład:" Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService "|  
|Domeny aplikacji|xs:String|Długość ciągu zwróconego przez AppDomain.CurrentDomain.FriendlyName.|