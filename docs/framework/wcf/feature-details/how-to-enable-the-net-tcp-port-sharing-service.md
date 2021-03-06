---
title: 'Instrukcje: Włączanie usługi współużytkowania portów Net.TCP'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 4b5a18e11d9fc15f23b5353883a63d838face58a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Instrukcje: Włączanie usługi współużytkowania portów Net.TCP
Windows Communication Foundation (WCF) używa usługi systemu Windows o nazwie usługi udostępniania portów Net.TCP ułatwia udostępnianie portów TCP wielu procesom. Ta usługa jest instalowana jako część usługi WCF, ale usługa nie jest włączona domyślnie w celu zapewnienia bezpieczeństwa i dlatego muszą być włączone ręcznie przed pierwszym użyciem. W tym temacie opisano sposób konfigurowania sieci TCP Port do udostępniania usługi za pomocą przystawki Microsoft Management Console (MMC).  
  
 Po włączyć usługi udostępniania portów Net.TCP i uruchomić go ręcznie, zobacz [porady: Konfigurowanie usługi WCF na potrzeby współużytkowania portów użyj](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) informacji o sposobie konfigurowania usługi do tej usługi.  
  
 Dla przykładu korzystającego z Udostępnianie portów net.tcp://, zobacz [przykład współużytkowania portów Net.TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>Aby włączyć usługi udostępniania portów Net.TCP przy użyciu konsoli MMC  
  
1.  Z Start menu, otwórz konsolę zarządzania usług albo otwierając okno wiersza polecenia i wpisując `services.msc` lub przez otwarcie Uruchom i wprowadzając polecenie `services.msc` w polu Otwórz.  
  
2.  W **nazwa** kolumny na liście usług, kliknij prawym przyciskiem myszy **usługi udostępniania portów Net.Tcp**i wybierz **właściwości** z menu.  
  
3.  Aby włączyć ręcznego uruchamiania usługi, w **właściwości** wybierz okno **ogólne** kartę i w **typ uruchamiania** wybierz ręcznego, a następnie kliknij przycisk **Zastosuj**.  
  
4.  Aby uruchomić usługę, w obszarze stanu usługi, kliknij przycisk **Start** przycisku. Stan usługi powinien być teraz wyświetlany "Started".  
  
5.  Aby powrócić do listy usług, kliknij przycisk **OK**i zamknij konsolę MMC.  
  
## <a name="example"></a>Przykład  
  
## <a name="see-also"></a>Zobacz też  
 [Współużytkowanie portów w składniku Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [Konfigurowanie usługi współużytkowania portów Net.TCP](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
