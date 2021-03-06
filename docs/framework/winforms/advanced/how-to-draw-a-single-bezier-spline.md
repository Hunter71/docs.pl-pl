---
title: 'Porady: Rysowanie pojedynczego B&#233;zier krzywymi składanymi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 9e91b63275c37fc0cdde5721fddd114e1bf2264e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Porady: Rysowanie pojedynczego B&#233;zier krzywymi składanymi
Krzywej Beziera jest definiowana za pomocą czterech punktów: punkt początkowy, punkty kontrolne dwóch i punkt końcowy.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład rysuje krzywej Beziera, punkt początkowy (10, 100) i punktu końcowego (200, 100). Formant wskazuje, czy (100, 10) i (150, 150).  
  
 Na poniższej ilustracji przedstawiono wynikowy krzywej Beziera wraz z jego punkt początkowy, punkty kontrolne i punktu końcowego. Na ilustracji przedstawiono również krzywej składanej wypukłych powłoki, czyli wielokąta sformułowany, łącząc się z czterech punktów z proste.  
  
 ![Beziera krzywej składanej](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Poprzedni przykład jest przeznaczony do użytku z formularzy systemu Windows i wymaga <xref:System.Windows.Forms.PaintEventArgs> `e`, który jest parametrem <xref:System.Windows.Forms.Control.Paint> obsługi zdarzeń.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [Krzywe Beziera w GDI+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [Instrukcje: rysowanie sekwencji krzywych Beziera](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
