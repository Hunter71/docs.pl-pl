---
title: ThemeDictionary — Rozszerzenie znaczników
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: ea7c630be3f6d208f5c62e8b9e24606ff0df8466
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="themedictionary-markup-extension"></a>ThemeDictionary — Rozszerzenie znaczników
Umożliwia autorom kontrolkę niestandardową lub aplikacje, które integracji formanty innych firm do załadowania słowniki zasobów specyficznych dla motywów do użycia w stylów formantu.  
  
## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Użycie elementu obiektu języka XAML  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a>Wartości XAML  
  
|||  
|-|-|  
|`assemblyUri`|[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] Zestawu, który zawiera informacje o motywu. Zazwyczaj jest to pakiet identyfikator URI, który odwołuje się do zestawu w pakiecie większy. Zestaw zasobów i identyfikatory URI pochodzące z uproszczenia problemów dotyczących wdrożenia. Aby uzyskać więcej informacji, zobacz [identyfikatorów URI pakietu na platformie WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).|  
  
## <a name="remarks"></a>Uwagi  
 To rozszerzenie jest przeznaczona do wypełnienia tylko jedna wartość określoną właściwość: wartość <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.  
  
 Za pomocą tego rozszerzenia, można określić jednym zestawie tylko do zasobów, który zawiera niektóre style, które mają być używane tylko wtedy, gdy [!INCLUDE[TLA#tla_aero](../../../../includes/tlasharptla-aero-md.md)] motyw jest stosowany do użytkownika systemu, inne style, gdy Luna motywu jest aktywna i tak dalej. Za pomocą tego rozszerzenia, zawartość słownika zasobów specyficznych dla formantu można automatycznie unieważniona i załadowania przeznaczone dla innej motywu, gdy jest to wymagane.  
  
 `assemblyUri` Ciąg (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> wartości właściwości) stanowi podstawę konwencji nazewnictwa, która identyfikuje słownik, który ma zastosowanie do wybranego motywu. <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> Logikę `ThemeDictionary` zakończeniu Konwencji, generując [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] wskazującego typ variant słownika wybranego motywu, zawarty w zestawie wstępnie skompilowanym zasobów. Opisujące, lub na podstawie motywu interakcji z stylów formantu ogólne i poziomu stylów strony aplikacji jako koncepcji, nie pasuje do pełni tutaj. Podstawowe scenariusz użycia `ThemeDictionary` jest określenie <xref:System.Windows.ResourceDictionary.Source%2A> właściwość `ResourceDictionary` zadeklarowane na poziomie aplikacji. Jeśli podasz [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] dla zestawu za pomocą `ThemeDictionary` rozszerzenia, a nie jako bezpośredniego [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], logiki rozszerzenia zapewni unieważniania logikę, która ma zastosowanie przy każdej zmianie motywu systemu.  
  
 Składnią atrybutu jest składnia najczęściej używana z tym rozszerzeniem znacznika. Token ciągu po `ThemeDictionary` przypisany jako identyfikator ciągu <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> wartości podstawowych <xref:System.Windows.ThemeDictionaryExtension> rozszerzenie klasy.  
  
 `ThemeDictionary` może być również w składni elementu obiekt. W takim przypadku określającą wartość <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> właściwość jest wymagana.  
  
 `ThemeDictionary` można również w Określa użycie atrybutu pełne <xref:System.Windows.Markup.StaticExtension.Member%2A> właściwości jako właściwość = pary wartości:  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 Szczegółowe definicje są często przydatne w rozszerzeniach zawierających więcej niż jedną konfigurowalną właściwość albo gdy niektóre właściwości są opcjonalne. Ponieważ `ThemeDictionary` ma tylko jedną można ustawić właściwości, która jest wymagana, to użycie Pełne nie są typowe.  
  
 W [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementacji procesora obsługę tego rozszerzenia znacznika jest definiowana za pomocą <xref:System.Windows.ThemeDictionaryExtension> klasy.  
  
 `ThemeDictionary` to rozszerzenie znacznika. Rozszerzenia znaczników są zazwyczaj implementowane w sytuacji, gdy istnieje wymóg, aby wartości atrybutów były wyprowadzane w postaci innej niż wartości literałów lub nazwy programów obsługi, a wymóg ma charakter bardziej globalny niż zwykłe umieszczenie konwerterów typów w niektórych typach lub właściwościach. Wszystkie rozszerzenia znaczników w [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Użyj {i} znaków w ich składni atrybutu Konwencji za pomocą którego [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesora rozpoznaje, że rozszerzenie znacznika musi przetworzyć atrybutu. Aby uzyskać więcej informacji, zobacz [rozszerzenia znaczników i WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Tworzenie szablonów i stylów](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Przegląd XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Rozszerzenia znaczników i WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Zasoby aplikacji WPF, zawartość i pliki danych](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)
