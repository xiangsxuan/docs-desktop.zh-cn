---
title: 如何：绘制矩形
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 95191e9d90bc2ac32902399125d9a51192e897bf
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970377"
---
# <a name="how-to-draw-a-rectangle"></a>如何：绘制矩形
此示例演示如何使用元素绘制矩形 <xref:System.Windows.Shapes.Rectangle> 。  
  
 若要绘制矩形，请创建一个 <xref:System.Windows.Shapes.Rectangle> 元素，并指定其 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 。 若要绘制矩形内部，请将其设置为 <xref:System.Windows.Shapes.Shape.Fill%2A> 。 若要为矩形指定轮廓，请使用其 <xref:System.Windows.Shapes.Shape.Stroke%2A> 和 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 属性。  
  
 若要为矩形指定圆角，请指定可选的 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 和 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 属性。 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>和 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 属性设置用于圆角化矩形角的椭圆的 x 轴半径和 y 轴半径。  
  
 在下面的示例中， <xref:System.Windows.Shapes.Rectangle> 在中绘制了两个元素 <xref:System.Windows.Controls.Canvas> 。 第一个矩形的 <xref:System.Windows.Media.Brushes.Blue%2A> 内部。 第二个矩形具有 <xref:System.Windows.Media.Brushes.Blue%2A> 内部、 <xref:System.Windows.Media.Brushes.Black%2A> 轮廓和圆角。  
  
## <a name="example"></a>示例  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 虽然此示例使用 <xref:System.Windows.Controls.Canvas> 来包含矩形，但你可以使用矩形元素 (和所有其他形状元素) <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.Control> 支持非文本内容的任何或。 事实上，矩形对于为面板的各个部分提供背景特别有用 <xref:System.Windows.Controls.Grid> 。 有关示例，请参阅 [表概述](../advanced/table-overview.md)。  
  
 此示例摘自一个更大的示例;有关完整示例，请参阅 [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Shapes.Rectangle>
- [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [WPF 中的形状和基本图形概述](shapes-and-basic-drawing-in-wpf-overview.md)
- [表概述](../advanced/table-overview.md)
