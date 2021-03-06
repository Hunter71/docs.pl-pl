---
title: '&lt;net.tcp&gt;'
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 9e44ddcc3a3e983abe6e36d4b6095c5c4a67529f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="ltnettcpgt"></a>&lt;net.tcp&gt;
Określa ustawienia konfiguracji sieci. TCP Port usługi udostępniania, dzięki czemu wielu procesom współużytkowanie tego samego portu TCP.  
  
 \<system.serviceModel.activation>  
\<net.tcp>  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a>Typ  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`listenBacklog`|Liczba całkowita określająca maksymalną liczbę oczekujących połączeń, które są akceptowane z udostępnionego połączenia, ale jeszcze nie są wysyłane do usługi Windows Communication Foundation (WCF). Wartość domyślna to 10.|  
|`maxPendingAccepts`|Liczba całkowita określająca maksymalną liczbę oczekujących współbieżnych wątków na punkcie końcowym nasłuchiwania dla usługi udostępniania. Wartość domyślna to 2.|  
|`MaxPendingConnections`|Maksymalna liczba połączeń odbiornika może mieć oczekuje na zatwierdzenie przez aplikację. Po przekroczeniu tej wartości limitu przydziału nowych połączeń przychodzących są usuwane, a nie oczekuje na zatwierdzenie. Połączenie funkcji, takich jak zabezpieczenia wiadomości może spowodować klienta otworzyć więcej niż jedno połączenie. Administratorzy usługi należy uwzględnić te dodatkowe połączenia podczas ustawiania tej wartości limitu przydziału. Wartość domyślna to 10.|  
|`receiveTimeout`|A `TimeSpan` , który określa limit czasu dla odczytu danych z ramek i wykonania przekazania połączenia z połączeń podkreślonych. Wartość domyślna to "00: 00:10".|  
|`teredoEnabled`|Wartość logiczna wskazująca, czy port udostępnianej usługi używa usługi Microsoft Teredo aby nasłuchiwać portów TCP w imieniu usług WCF. Wartość domyślna to `false`.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<allowAccounts>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Kolekcja elementów konfiguracji, które zawierają `securityIdentifier` atrybutu określ konta użytkowników dla procesów, które host usługi WCF i przyznano im dostęp do połączenia z usługą udostępniania.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Zawiera ustawienia konfiguracji dla procesu odbiornika SMSvcHost.exe.|  
  
## <a name="remarks"></a>Uwagi  
 Aby uzyskać więcej informacji na temat udostępniania portów, zobacz [udostępniania portów Net.TCP](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded). Aby poznać sposób konfigurowania usługi współużytkowania portów, zobacz [Konfigurowanie usługi udostępniania portów Net.TCP](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [Współużytkowanie portów w składniku Net.TCP](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [Konfigurowanie usługi współużytkowania portów Net.TCP](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
