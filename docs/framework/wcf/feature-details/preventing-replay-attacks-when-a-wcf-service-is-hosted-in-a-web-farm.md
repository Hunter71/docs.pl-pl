---
title: Zapobieganie atakom polegającym na odtwarzaniu, gdy usługa WCF jest hostowana na farmie sieci Web
ms.date: 03/30/2017
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
ms.openlocfilehash: 8b49b46e56d07dcd2f1eaf6afca964ddfe7dd740
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="preventing-replay-attacks-when-a-wcf-service-is-hosted-in-a-web-farm"></a>Zapobieganie atakom polegającym na odtwarzaniu, gdy usługa WCF jest hostowana na farmie sieci Web
Gdy korzystanie z zabezpieczeń komunikatów usługi WCF zapobiega atakom metodą powtórzeń, tworząc NONCE poza komunikatu przychodzącego i sprawdzanie wewnętrznej `InMemoryNonceCache` czy wygenerowany identyfikator JEDNORAZOWY jest obecny. Jeśli tak jest, komunikat zostanie odrzucony jako powtarzania. Gdy usługa WCF jest obsługiwana w kolektywie serwerów sieci web, ponieważ `InMemoryNonceCache` nie jest udostępniana między węzłami w farmie sieci web, usługa jest narażony na ataki.  Aby ograniczyć ten scenariusz WCF 4.5 udostępnia punkt rozszerzalności umożliwiający implementowanie własne współużytkowanej pamięci podręcznej identyfikator JEDNORAZOWY przez wyprowadzanie klasy z klasy abstrakcyjnej <xref:System.ServiceModel.Security.NonceCache>.  
  
## <a name="noncecache-implementation"></a>Implementacja NonceCache  
 Aby wdrożyć własny współużytkowanej pamięci podręcznej identyfikator JEDNORAZOWY, klasa wyprowadzona z <xref:System.ServiceModel.Security.NonceCache> i zastąpić <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> i <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> metody. <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> sprawdza, czy określony identyfikator JEDNORAZOWY istnieje w pamięci podręcznej. <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> spróbuje dodać identyfikatora JEDNORAZOWEGO do pamięci podręcznej. Po zaimplementowaniu tej klasy można dołączenie go instancji i przypisywania go do <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.NonceCache%2A> po stronie klienta wykrywania powtarzania i <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NonceCache%2A> po stronie serwera wykrywania powtarzania. Nie ma żadnych poza okno obsługi konfiguracji tej funkcji.  
  
## <a name="see-also"></a>Zobacz też  
 [Zabezpieczenia komunikatów](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [SymmetricSecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)
