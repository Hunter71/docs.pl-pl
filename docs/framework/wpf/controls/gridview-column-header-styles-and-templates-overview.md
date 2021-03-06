---
title: Przegląd Style nagłówka kolumn i szablonów GridView
ms.date: 03/30/2017
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
ms.openlocfilehash: 28b4a64a6c79b226b1ff4b3bfcbf9a55b6d8df78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="gridview-column-header-styles-and-templates-overview"></a>Przegląd Style nagłówka kolumn i szablonów GridView
To omówienie omówiono kolejność pierwszeństwa dla właściwości, które służy do dostosowywania nagłówka kolumny w <xref:System.Windows.Controls.GridView> tryb widoku <xref:System.Windows.Controls.ListView> formantu.  
  
## <a name="customizing-a-column-header-in-a-gridview"></a>Dostosowywanie nagłówek kolumny w widoku GridView  
 Właściwości definiujące zawartość, układ i styl nagłówka kolumny w <xref:System.Windows.Controls.GridView> znajdują się na wielu klas pokrewnych. Niektóre z tych właściwości mają funkcjonalność podobną lub taka sama.  
  
 Wiersze w poniższej tabeli przedstawiono grup właściwości, które wykonują tę samą funkcję. Te właściwości można użyć do dostosowywania nagłówków kolumn w <xref:System.Windows.Controls.GridView>. Kolejność pierwszeństwa powiązane właściwości jest od prawej do lewej, gdy właściwość w najdalej z prawej kolumnie ma najwyższy priorytet. Na przykład jeśli <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> jest ustawiona na <xref:System.Windows.Controls.GridViewColumnHeader> obiektu i <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> jest ustawiony na skojarzonym <xref:System.Windows.Controls.GridViewColumn>, <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> ma pierwszeństwo. W tym scenariuszu <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> nie ma wpływu.  
  
 **Powiązane właściwości dla nagłówków kolumn w widoku GridView**  
  
|||||  
|-|-|-|-|  
|**Klasy**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Właściwości Menu kontekstowego**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|Nie dotyczy|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**Etykietka narzędzia**<br /><br /> **Właściwości**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|Nie dotyczy|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Szablon nagłówka**<br /><br /> **Właściwości**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Właściwości stylu**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>dla **właściwości szablonu nagłówka**, jeśli zostanie ustawiona, szablon i właściwości selektor szablonu, pierwszeństwo ma właściwości szablonu. Na przykład, jeśli wartość <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> i <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> właściwości <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> właściwości ma pierwszeństwo.  
  
## <a name="see-also"></a>Zobacz też  
 [Tematy z instrukcjami](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView — omówienie](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView — omówienie](../../../../docs/framework/wpf/controls/gridview-overview.md)
