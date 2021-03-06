---
title: Jak ustawić położenie ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 218d8814cf75cd80a63c94397ed00e92c6a9a8fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-position-a-tooltip"></a>Jak ustawić położenie ToolTip
W tym przykładzie przedstawiono sposób określić położenie etykietka narzędzia na ekranie.  
  
## <a name="example"></a>Przykład  
 Etykietka narzędzia można umieścić przy użyciu zestawu pięciu właściwości, które są zdefiniowane w obu <xref:System.Windows.Controls.ToolTip> i <xref:System.Windows.Controls.ToolTipService> klasy. Poniższa tabela przedstawia te dwa zestawy pięciu właściwości oraz zawiera łącza do ich dokumentacji zgodnie z klasy.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Odpowiednie właściwości etykietka narzędzia, zgodnie z klasy  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> Właściwości klasy|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> Właściwości klasy|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Można zdefiniować zawartość etykietka narzędzia przy użyciu <xref:System.Windows.Controls.ToolTip> obiektu, można użyć właściwości każdej klasy, ale <xref:System.Windows.Controls.ToolTipService> właściwości mają pierwszeństwo. Użyj <xref:System.Windows.Controls.ToolTipService> właściwości etykietki narzędzi, które nie są zdefiniowane jako <xref:System.Windows.Controls.ToolTip> obiektów.  
  
 Na poniższych ilustracjach przedstawiono położenie etykietka narzędzia, za pomocą tych właściwości. Mimo że, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] przykłady w tym ilustracjom przedstawiają sposób ustawiania właściwości, które są definiowane przez <xref:System.Windows.Controls.ToolTip> klasy odpowiednich właściwościach <xref:System.Windows.Controls.ToolTipService> klasy są zgodne z regułami układu. Aby uzyskać więcej informacji na temat możliwych wartości dla właściwości umieszczania, zobacz [zachowanie przy umieszczaniu podręcznego](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  
  
 ![Etykietka narzędzia umieszczania](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
Etykietka narzędzia umieszczania przy użyciu właściwości umieszczania  
  
 ![Umieszczanie obiektu ToolTip przy użyciu prostokąta umieszczania](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
Etykietka narzędzia umieszczania przy użyciu właściwości umieszczania i PlacementRectangle  
  
 ![Etykietka narzędzia umieszczania diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
Etykietka narzędzia umieszczania przy użyciu właściwości Placement, PlacementRectangle i przesunięcie  
  
 Poniższy przykład przedstawia użycie <xref:System.Windows.Controls.ToolTip> właściwości, aby określić położenie etykietka narzędzia, których zawartość znajduje się <xref:System.Windows.Controls.ToolTip> obiektu.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 Poniższy przykład przedstawia użycie <xref:System.Windows.Controls.ToolTipService> właściwości, aby określić położenie etykietka narzędzia, którego zawartość nie jest <xref:System.Windows.Controls.ToolTip> obiektu.  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [Tematy z instrukcjami](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [ToolTip — omówienie](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [Użyj ContextMenuService i ToolTipService](http://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
