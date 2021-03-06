---
title: 'Porady: zarejestrować i skonfigurować krótkiej nazwy'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: 1d245327c1e7d53de9a88c93ff0399d8e231a1df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-register-and-configure-a-service-moniker"></a>Porady: zarejestrować i skonfigurować krótkiej nazwy
Przed użyciem moniker usługi Windows Communication Foundation (WCF) w aplikacji modelu COM z typu kontraktu, musisz zarejestrować wymagane typy oparte na atrybutach w modelu COM i skonfigurować aplikacji modelu COM i krótka nazwa wymaganego powiązania Konfiguracja.  
  
### <a name="to-register-the-required-attributed-types-with-com"></a>Aby zarejestrować wymagane typy oparte na atrybutach w modelu COM  
  
1.  Użyj [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) narzędzia do pobierania metadanych kontraktu usługi WCF. Spowoduje to wygenerowanie kodu źródłowego dla zestawu klienta WCF i pliku konfiguracji aplikacji klienta.  
  
2.  Upewnij się, że typy w zestawie są oznaczone jako `ComVisible`. Aby to zrobić, Dodaj następujący atrybut w pliku AssemblyInfo.cs w projektu programu Visual Studio.  
  
    ```  
    [assembly: ComVisible(true)]  
    ```  
  
3.  Kompiluj zarządzanego klienta WCF jako zestawu o silnej nazwie. Wymaga podpisywania za pomocą klucza kryptograficznego. Aby uzyskać więcej informacji, zobacz [podpisywanie zestawu o silnej nazwie](http://go.microsoft.com/fwlink/?LinkId=94874) w Podręczniku dewelopera programu .NET.  
  
4.  Użyj narzędzia do rejestrowania zestawów (Regasm.exe) z `/tlb` możliwość zarejestrowania typów w zestawie z modelu COM.  
  
5.  Narzędzie Global Assembly Cache (Gacutil.exe) można dodać zestawu do globalnej pamięci podręcznej zestawów.  
  
    > [!NOTE]
    >  Podpisywanie zestawu i dodanie go do globalnej pamięci podręcznej zestawów są opcjonalne kroki, ale ich uprościć proces ładowania zestawu we właściwej lokalizacji w czasie wykonywania.  
  
### <a name="to-configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a>Aby skonfigurować za pomocą konfiguracji powiązania wymaganych aplikacji modelu COM i krótka nazwa  
  
-   Umieść definicje powiązania (generowane przez [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) w pliku konfiguracyjnym aplikacji wygenerowanego klienta) w pliku konfiguracyjnym aplikacji klienta. Na przykład dla programu Visual Basic 6.0 pliku wykonywalnego o nazwie CallCenterClient.exe, Konfiguracja powinna zostać umieszczona w pliku o nazwie CallCenterConfig.exe.config w tym samym katalogu co plik wykonywalny. Aplikacja kliencka można teraz używać krótkiej nazwy. Należy pamiętać, że konfiguracja powiązania nie jest wymagane, jeśli przy użyciu jednej ze standardowych powiązanie typów dostarczanych przez usługę WCF.  
  
     Następujący typ jest zarejestrowany.  
  
    ```  
    using System.ServiceModel;  
  
    ...  
  
    [ServiceContract]   
    public interface IMathService   
    {  
    [OperationContract]  
    public int Add(int x, int y);  
    [OperationContract]  
    public int Subtract(int x, int y);  
    }  
    ```  
  
     Aplikacja jest uwidaczniany za pomocą `wsHttpBinding` powiązania. Dla danego typu i konfiguracji aplikacji są używane następujące ciągi przykład krótkiej nazwy.  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1  
    ```  
  
     `or`  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}  
    ```  
  
     Możesz użyć dowolnej z tych ciągów krótkiej nazwy z aplikacji Visual Basic 6.0, po dodaniu odwołanie do zestawu, który zawiera `IMathService` typy, jak pokazano w poniższym kodzie próbki.  
  
    ```  
    Dim MathProxy As IMathService  
    Dim result As Integer  
  
    Set MathProxy = GetObject( _  
            "service4:address=http://localhost/MathService, _  
            binding=wsHttpBinding, _  
            bindingConfiguration=Binding1")  
  
    result = MathProxy.Add(3, 5)  
    ```  
  
     W tym przykładzie definicji konfiguracji powiązania `Binding1` są przechowywane w pliku konfiguracji nazwanych odpowiednio do aplikacji klienckiej, takich jak vb6appname.exe.config.  
  
    > [!NOTE]
    >  Można użyć podobny kod w C#, C++ lub innych aplikacji języka .NET.  
  
    > [!NOTE]
    >  : Jeśli krótka nazwa jest nieprawidłowo sformułowany lub usługa jest niedostępna, wywołanie `GetObject` błędu "Nieprawidłowa składnia". Jeśli zostanie wyświetlony ten błąd, upewnij się, krótkiej nazwy, którego używasz, jest poprawny i usługa jest dostępna.  
  
     Chociaż ten temat koncentruje się na korzystanie z kodu VB 6.0 moniker usługi, możesz użyć krótkiej nazwy z innych języków. Gdy przy użyciu krótkiej nazwy z C++ kod Svcutil.exe wygenerowany zestawu należy zaimportować z "no_namespace — named_guids — raw_interfaces_only —", jak pokazano w poniższym kodzie.  
  
    ```  
    #import "ComTestProxy.tlb" no_namespace named_guids  
    ```  
  
     Modyfikuje definicje interfejsu importowane, tak, aby zwrócić wszystkie metody `HResult`. Wszelkie inne wartości są konwertowane na parametrów wyjściowych. Ogólny wykonywanie metod jest taka sama. Dzięki temu można ustalić przyczynę Wystąpił wyjątek podczas wywoływania metody na serwerze proxy. Ta funkcja jest dostępna tylko z kodu C++.  
  
## <a name="see-also"></a>Zobacz też  
 [Narzędzie do obsługi metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
