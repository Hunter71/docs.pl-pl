---
title: Jak animować geometrię prostokąta z wykorzystaniem klatek kluczowych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: 581dc89d21091ad0ce856d7a7ced84fd7bcea9d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Jak animować geometrię prostokąta z wykorzystaniem klatek kluczowych
W tym przykładzie pokazano, jak animować <xref:System.Windows.Media.RectangleGeometry.Rect%2A> właściwość <xref:System.Windows.Media.RectangleGeometry> przy użyciu klucza ramki.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> klasy do animowania <xref:System.Windows.Media.RectangleGeometry.Rect%2A> właściwość <xref:System.Windows.Media.RectangleGeometry>. Ta animacja używa trzech klatek kluczowych w następujący sposób:  
  
1.  Podczas pierwszego dwusekundowe używa wystąpienia <xref:System.Windows.Media.Animation.LinearRectKeyFrame> klasy do animowania stopniowego zmiany w pozycji, szerokość i wysokość prostokąta. Liniowy klatek kluczowych, takich jak <xref:System.Windows.Media.Animation.LinearRectKeyFrame> utworzyć liniowej przejścia między wartościami.  
  
2.  W końcu następnej pół sekundy używa wystąpienia <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> klasy nagle Zwiększ wysokość prostokąta. Odrębny klatek kluczowych, takich jak <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> utworzyć nagłym zmiany między wartościami, oznacza to, spadek wysokość odbywa się szybko i nie jest niewielkie.  
  
3.  Podczas końcowego dwusekundowe używa wystąpienia <xref:System.Windows.Media.Animation.SplineRectKeyFrame> klasę, aby zmienić przywracając jego oryginalny rozmiar i pozycja prostokąta. Ramek kluczowych krzywej składanej, takich jak <xref:System.Windows.Media.Animation.SplineRectKeyFrame> utworzyć zmiennej przejścia między wartościami zgodnie z wartościami <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> właściwości. W tym przykładzie zmiana rozpoczyna się powoli i przyspiesza wykładniczo do końca segmentu czasu.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Pełny przykład, zobacz [klatek kluczowych animacji próbki](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [Animacje kluczowych klatek — przegląd](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Klatki kluczowe — tematy z instrukcjami](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
