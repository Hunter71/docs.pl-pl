---
title: "Bezpieczeństwo i rejestr (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- security [Visual Basic], registry
- registry [Visual Basic], security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0961d21417cbb5efcd9f38112c4e8ecb393faccd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="security-and-the-registry-visual-basic"></a>Bezpieczeństwo i rejestr (Visual Basic)
Ta strona zawiera omówienie zabezpieczenia przechowywania danych w rejestrze.  
  
## <a name="permissions"></a>Uprawnienia  
 Nie jest bezpieczny do przechowywania kluczy tajnych, takie jak hasła, w rejestrze w postaci zwykłego tekstu, nawet jeśli klucz rejestru jest chroniony przez listy kontroli dostępu (listy kontroli dostępu).  
  
 Praca z rejestru może naruszyć bezpieczeństwo, zezwalając nieodpowiednie dostęp do zasobów systemowych lub chronionych informacji. Aby korzystać z tych właściwości, musi mieć uprawnienia z odczytu i zapisu <xref:System.Security.Permissions.RegistryPermissionAccess> wyliczenia, która kontroluje dostęp do zmiennych rejestru. Każdy kod uruchomiona z pełnym zaufaniem (w obszarze domyślnych zasad zabezpieczeń jest dowolny kod zainstalowana na lokalnym dysku twardym użytkownika) ma niezbędne uprawnienia dostępu do rejestru. Aby uzyskać więcej informacji, zobacz <xref:System.Security.Permissions.RegistryPermission> klasy.  
  
 Zmienne rejestru nie powinny być przechowywane w lokalizacji pamięci gdzie kodu bez <xref:System.Security.Permissions.RegistryPermission> mogą uzyskiwać do nich dostęp. Podobnie podczas udzielania uprawnień, należy przyznać minimalne uprawnienia, które trzeba wykonać zadanie.  
  
 Uprawnienia dostępu do wartości są definiowane przez <xref:System.Security.Permissions.RegistryPermissionAccess> wyliczenia. W poniższej tabeli przedstawiono jej elementów członkowskich.  
  
|Wartość|Dostęp do zmiennych rejestru|  
|-----------|----------------------------------|  
|`AllAccess`|Tworzenia, odczytu i zapisu|  
|`Create`|Create|  
|`NoAccess`|Brak dostępu|  
|`Read`|Odczyt|  
|`Write`|Write|  
  
## <a name="checking-values-in-registry-keys"></a>Sprawdzanie wartości kluczy rejestru  
 Po utworzeniu wartości rejestru należy zdecydować, co należy zrobić, jeśli ta wartość już istnieje. Inny proces, możliwe, że złośliwe jeden mogły już zostać utworzone wartość i jest do niego dostęp. Po umieszczeniu danych w wartości rejestru, dane są dostępne do innego procesu. Aby tego uniknąć, należy użyć `GetValue` metody. Zwraca `Nothing` Jeśli klucz jeszcze nie istnieje.  
  
> [!IMPORTANT]
>  Podczas odczytywania rejestru z aplikacji sieci Web, tożsamość bieżącego użytkownika zależy od uwierzytelniania i personifikacji wdrożone w aplikacji sieci Web.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 [Odczytywanie z oraz zapisywanie do rejestru](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)