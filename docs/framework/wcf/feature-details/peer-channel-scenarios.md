---
title: Scenariusze obejmujące kanał elementu równorzędnego
ms.date: 03/30/2017
ms.assetid: dae6e0f7-900c-45ee-8be9-3647698382fb
ms.openlocfilehash: 42b16ea394b9375be14aed4b2792d306fcb62f2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="peer-channel-scenarios"></a>Scenariusze obejmujące kanał elementu równorzędnego
Interfejsy API kanał elementu równorzędnego obsługuje następujące scenariusze programowania.  
  
## <a name="publicationsubscription-messaging"></a>Obsługa wiadomości publikacji/subskrypcji  
 Tworzenie aplikacji publikacji/subskrypcji, (na przykład, giełdowych i wydawców nagłówki wiadomości sportowe wyniki, a następnie raportuje pogody) firmy umożliwia kanału równorzędnego aplikacji serwera. Na przykład użytkownicy mogą uzyskać najnowsze wyniki sportowych po dołączeniu do typowych siatki (lub grupy klientów) i Propaguj dużą ilość aktualne dane gry bez zwiększania obciążenia serwera. Dzięki temu dostawcy danych, aby zapewnić wyższej jakości usługi bez znaczne zwiększenie inwestycje w technologie na serwerze.  
  
## <a name="collaboration"></a>Współpraca  
 Niezależnym dostawcom oprogramowania (ISV) tworzyć aplikacje, które umożliwiają użytkownikom tworzenie grup ścisłej uczestnictwa w działaniach peer-to-peer. Na przykład może to obejmować zespoły pracuje zespołowych obraz udostępnianie między znajomych, planowanie strona działania i inne. Zazwyczaj te działania zawsze obejmują serwery; Kanał elementu równorzędnego zapewnia jednak jak to zrobić w sposób bardziej ekonomiczne, umożliwiając dostęp w trybie offline scenariusze, które nie są równie łatwo zaimplementowane w modelu tradycyjnych klienta serwera.  
  
## <a name="distributed-processing-and-compute-clusters"></a>Przetwarzanie rozproszone i klastrów obliczeniowych  
 Klastry obliczeniowe i przetwarzania rozproszonego zwykle są używane do obliczenia na dużą skalę, takich jak finansowych/pogody modelowania i dekodowania człowieka DNS. Zazwyczaj jest to realizowane dzięki użyciu serwerów osobno przypisywanie zadań do wszystkich klientów uczestniczących w danym klastrze obliczeniowym. Serwery te mogą także mieć dodatkowe wymagania; na przykład wszystkie zadania może być konieczne można wykonać w określonym przez określony czas, wymaga więcej niż jednej maszyny dla każdego zadania. Ponadto jeśli dowolny klient uruchamiania zadania ulegnie awarii, innego klienta musi być może przejąć zadania i wykonywania pracy na nim. Podobnie więcej niż jednego klienta może być konieczne uruchomienie tego samego zadania, aby zapewnić spójne wyniki. Mimo że serwery można uruchomić tego rodzaju koordynacji klienta, można utworzyć rozwiązanie peer-to-peer, gdy klienci odbieranie zadania niezależnie ustalić wymagania dotyczące serwera wokół zadania i użyj siatki obliczeń, aby określić sposób wykonania tego zadania.  
  
## <a name="gaming"></a>Gry  
 Przy użyciu kanału równorzędnego, deweloperzy aplikacji można utworzyć wersji serwera bez ich gry, w którym gier przenosi get przesyłane do i synchronizowane z innymi osobami przez mechanizm peer-to-peer, a nie za pomocą centralnego serwera. Dla małych ISV pomaga usunąć koszty operacyjne związane z wdrażania, obsługi i obsługi serwerów centralnej. W Internecie lub w sieci przewodowej lub bezprzewodowej sieci lokalnej, można odtwarzać gier napisanych przy użyciu architektury peer-to-peer. Mogą być opracowane dodatkowej gier działań, takich jak są nią i rozmów w grze przy użyciu sieci peer-to-peer.  
  
## <a name="see-also"></a>Zobacz też  
 [Pojęcia kanałów równorzędnych](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md)
