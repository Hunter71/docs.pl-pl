---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: aa852ff82c44a3b5009dbc70e1067face44cbbe9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="clientcredentials"></a>ClientCredentials
ClientCredentials  
  
## <a name="syntax"></a>Składnia  
  
```  
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a>Metody  
 Klasa ClientCredentials nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  
 Klasa ClientCredentials ma następujące właściwości:  
  
### <a name="clientcertificate"></a>ClientCertificate  
 Typ danych: ciąg  
  
 Dostęp typu: tylko do odczytu  
  
 Certyfikat X.509 klient używa do uwierzytelnienia w usłudze.  
  
### <a name="httpdigest"></a>HttpDigest  
 Typ danych: ciąg  
  
 Dostęp typu: tylko do odczytu  
  
 Bieżące poświadczenie Http Digest.  
  
### <a name="issuedtoken"></a>IssuedToken  
 Typ danych: ciąg  
  
 Dostęp typu: tylko do odczytu  
  
 Adres punktu końcowego i powiązanie używane do kontaktu z usługą tokenu zabezpieczeń lokalnych.  
  
### <a name="peer"></a>elementów równorzędnych  
 Typ danych: ciąg  
  
 Dostęp typu: tylko do odczytu  
  
 Poświadczenia używane przez węzeł elementu równorzędnego do samodzielnego uwierzytelnienia w innych węzłach w sieci.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Typ danych: ciąg  
  
 Dostęp typu: tylko do odczytu  
  
 Certyfikat X.509 usługi.  
  
### <a name="supportinteractive"></a>SupportInteractive  
 Typ danych: wartość logiczna  
  
 Dostęp typu: tylko do odczytu  
  
 Wartość logiczna określająca, czy poświadczenie obsługuje interaktywną negocjację.  
  
### <a name="username"></a>UserName  
 Typ danych: ciąg  
  
 Dostęp typu: tylko do odczytu  
  
 Nazwa użytkownika i hasło, którego klient używa do samodzielnego uwierzytelnienia usługi.  
  
### <a name="windows"></a>Windows  
 Typ danych: ciąg  
  
 Dostęp typu: tylko do odczytu  
  
 Poświadczenia systemu windows używa klienta do samodzielnego uwierzytelnienia usługi.  
  
## <a name="requirements"></a>Wymagania  
  
|MOF|Zadeklarowany w Servicemodel.mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowany w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.Description.ClientCredentials>
