---
title: ToggleButton — Style i szablony
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: b2f3593fbfd2d1fabe2034570813538013623b8b
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2018
---
# <a name="togglebutton-syles-and-templates"></a>ToggleButton — Style i szablony
W tym temacie opisano, style i szablonów dla <xref:System.Windows.Controls.Primitives.ToggleButton> formantu. Można zmodyfikować domyślne <xref:System.Windows.Controls.ControlTemplate> umożliwiają unikatowego wyglądu formantu. Aby uzyskać więcej informacji, zobacz [Dostosowywanie wyglądu formant tworząc ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="togglebutton-parts"></a>Części ToggleButton  
 <xref:System.Windows.Controls.Primitives.ToggleButton> Formant nie ma żadnych części o nazwie.  
  
## <a name="togglebutton-states"></a>Stany ToggleButton  
 W poniższej tabeli wymieniono stany wizualne dla <xref:System.Windows.Controls.Primitives.ToggleButton> formantu.  
  
|Nazwa stanu wizualnego|Nazwa VisualStateGroup|Opis|  
|-|-|-|  
|Normalny|CommonStates|Stan domyślny.|  
|Etykietka wskaźnika myszy|CommonStates|Wskaźnik myszy znajduje się nad formantem.|  
|Naciśnięto|CommonStates|Formant zostanie naciśnięty.|  
|Wyłączone|CommonStates|Kontrolka jest wyłączona.|  
|Fokus|FocusStates|Formant ma fokus.|  
|Bez fokusu|FocusStates|Formant nie ma fokusa.|  
|Zaznaczone|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> jest `true`.|  
|Unchecked|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> jest `false`.|  
|Nieokreślony|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> jest `true`, i <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> jest `null`.|  
|Prawidłowe|ValidationStates|Używa kontrolki <xref:System.Windows.Controls.Validation> klasy i <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> jest dołączona właściwość `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant ma fokus.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant nie ma fokusa.|  
  
> [!NOTE]
>  Jeśli nieokreślony stan wizualny nie istnieje w szablonie formantu, jako domyślny stan wizualny używany jest niezaznaczone stanu wizualnego.  
  
## <a name="togglebutton-controltemplate-example"></a>Przykład ControlTemplate ToggleButton  
 Poniższy przykład przedstawia sposób definiowania <xref:System.Windows.Controls.ControlTemplate> dla <xref:System.Windows.Controls.Primitives.ToggleButton> formantu.  
  
 [!code-xaml[ControlTemplateExamples#ToggleButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]  
  
 Powyższy przykład korzysta z co najmniej jeden z następujących zasobów.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Pełny przykład, zobacz [style próbki ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Style i szablony kontrolek](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Niestandardowe dostosowywanie kontrolki](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Tworzenie szablonów i stylów](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Dostosowywanie wyglądu istniejącej kontrolki przez tworzenie ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
