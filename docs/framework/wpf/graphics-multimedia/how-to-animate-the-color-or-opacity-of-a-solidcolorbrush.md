---
title: "Jak animować kolor lub nieprzezroczystość SolidColorBrush"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 03052cdf68a5a8564d5a24c91521749c10afa6cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Jak animować kolor lub nieprzezroczystość SolidColorBrush
W tym przykładzie pokazano, jak animować <xref:System.Windows.Media.SolidColorBrush.Color%2A> i <xref:System.Windows.Media.Brush.Opacity%2A> z <xref:System.Windows.Media.SolidColorBrush>.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto trzy animacje do animowania <xref:System.Windows.Media.SolidColorBrush.Color%2A> i <xref:System.Windows.Media.Brush.Opacity%2A> z <xref:System.Windows.Media.SolidColorBrush>.  
  
-   Pierwszy animacji <xref:System.Windows.Media.Animation.ColorAnimation>, zmienia kolor pędzla do <xref:System.Windows.Media.Colors.Gray%2A> gdy mysz przejdzie prostokąta.  
  
-   Animacja dalej innego <xref:System.Windows.Media.Animation.ColorAnimation>, zmienia kolor pędzla do <xref:System.Windows.Media.Colors.Orange%2A> gdy mysz opuści prostokąta.  
  
-   Końcowe animacji <xref:System.Windows.Media.Animation.DoubleAnimation>, zmiany przezroczystość pędzla 0,0 po naciśnięciu lewego przycisku myszy.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Aby uzyskać bardziej szczegółowy przykładzie pokazano, jak animować różnego rodzaju pędzle, zobacz [przykład pędzle](http://go.microsoft.com/fwlink/?LinkID=159973). Aby uzyskać więcej informacji na temat animacji, zobacz [omówienie animacja](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Spójności z innymi przykładami animacji, użyj wersji kodu w tym przykładzie <xref:System.Windows.Media.Animation.Storyboard> obiekt do zastosowania ich animacji. Jednak podczas stosowania pojedynczego animacji w kodzie, łatwiej jest użyć <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metody zamiast <xref:System.Windows.Media.Animation.Storyboard>. Na przykład zobacz [animowania właściwości bez Using scenorysu](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Animacja — omówienie](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Scenorys — omówienie](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Pędzle próbki](http://go.microsoft.com/fwlink/?LinkID=159973)