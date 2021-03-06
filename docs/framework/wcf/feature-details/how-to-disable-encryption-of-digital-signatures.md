---
title: 'Porady: wyłączanie szyfrowanie podpisów cyfrowych'
ms.date: 03/30/2017
ms.assetid: fd174313-ad81-4dca-898a-016ccaff8187
ms.openlocfilehash: 074a32f6a69f8353568e76c99f4b65aece813f55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-disable-encryption-of-digital-signatures"></a>Porady: wyłączanie szyfrowanie podpisów cyfrowych
Domyślnie komunikat jest podpisany i podpisu cyfrowego jest zaszyfrowany. Jest to kontrolowane przez utworzenie niestandardowego powiązania z wystąpieniem <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> lub <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> i ustawienie `MessageProtectionOrder` właściwości każdej klasy do <xref:System.ServiceModel.Security.MessageProtectionOrder> wartości wyliczenia. Wartość domyślna to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Ten proces wykorzystuje do 30% więcej czasu niż po prostu podpisywanie i szyfrowanie oparte na całkowity rozmiar wiadomości (mniejszych wiadomości, tym większy wpływ na wydajność). Wyłączenie szyfrowania podpisu, jednak osoba atakująca może mieć odgadnąć treści komunikatu. Jest to możliwe, ponieważ wartość skrótu zwykły tekst każdej części podpisanych wiadomości zawiera element podpisu. Na przykład chociaż treść komunikatu jest domyślnie szyfrowane, niezaszyfrowane podpis zawiera skrótu przed szyfrowania treści wiadomości. Jeśli zestaw możliwych wartości dla części podpisane i zaszyfrowane jest mały, osoba atakująca może mieć możliwość wywnioskować zawartość, sprawdzając wartość skrótu. Szyfrowanie podpis zmniejsza zagrożenie tego ataku.  
  
 Dlatego należy wyłączyć szyfrowanie podpisu, tylko wtedy, gdy wartość zawartość jest niska lub zestaw możliwych wartości zawartości jest duża i niedeterministyczne i bardziej wydajne ma większe znaczenie niż zmniejszenia ataku opisane powyżej.  
  
> [!NOTE]
>  Jeśli nie ma w wiadomości, która jest zaszyfrowany, element podpisu nie jest zaszyfrowany, nawet wtedy, gdy <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> lub <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> właściwość jest ustawiona na <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Dzieje się tak nawet w przypadku powiązania dostarczane przez system; wszystkie powiązania dostarczane przez system ma porządku ochrony wiadomości ustawioną `SignBeforeEncryptAndEncryptSignature`. Jednak Web Services Description Language (WSDL) WCF generuje będzie nadal zawierać `<sp:EncryptSignature>` potwierdzenia.  
  
### <a name="to-disable-digital-signing"></a>Aby wyłączyć podpisów cyfrowych  
  
1.  Utwórz <xref:System.ServiceModel.Channels.CustomBinding>. Aby uzyskać więcej informacji, zobacz [porady: Tworzenie niestandardowego powiązania przy użyciu elementu SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2.  Dodaj albo <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> lub <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> do kolekcji powiązania.  
  
3.  Ustaw <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> właściwości <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>, lub ustaw <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> właściwości <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.  
  
## <a name="see-also"></a>Zobacz też  
 [Możliwości zabezpieczeń powiązań niestandardowych](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
