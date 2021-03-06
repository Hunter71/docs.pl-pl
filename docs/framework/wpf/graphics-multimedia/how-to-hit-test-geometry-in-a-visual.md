---
title: Jak przeprowadzić test trafienia geometrii w Visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 26e0119ee82646f466c3567881bf33350fe59d17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Jak przeprowadzić test trafienia geometrii w Visual
W tym przykładzie przedstawiono sposób wykonywania testu trafienia na obiekt wizualny, który składa się z co najmniej jeden <xref:System.Windows.Media.Geometry> obiektów.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia sposób pobrać <xref:System.Windows.Media.DrawingGroup> z obiektu visual, która używa <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> metody. Testu trafienia następnie odbywa się na renderowanej zawartości każdego rysunku w <xref:System.Windows.Media.DrawingGroup> do określenia, które geometrii został trafiony.  
  
> [!NOTE]
>  W większości przypadków należy użyć <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodę, aby określić, czy punkt przecina żadnego renderowanej zawartości obiektu visual.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <xref:System.Windows.Media.Geometry.FillContains%2A> Metody jest przeciążona metoda służy do testowania trafienia przy użyciu określonej <xref:System.Windows.Point> lub <xref:System.Windows.Media.Geometry>. Geometrię jest malowania, obrysu można rozszerzyć poza granicami wypełnienia. W takim przypadku można wywołać <xref:System.Windows.Media.Geometry.StrokeContains%2A> oprócz <xref:System.Windows.Media.Geometry.FillContains%2A>.  
  
 Można też podać <xref:System.Windows.Media.ToleranceType> używany na potrzeby spłaszczanie Beziera.  
  
> [!NOTE]
>  W tym przykładzie nie bierze pod uwagę transformacje lub wycinek, który może być stosowany do geometrii. Ponadto w tym przykładzie nie będzie działać z formantu, ponieważ nie ma rysunki bezpośrednio związane z nią.  
  
## <a name="see-also"></a>Zobacz też  
 [Test trafienia w warstwie wizualizacji](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Przeprowadzanie testu trafienia przy użyciu geometrii jako parametru](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)
