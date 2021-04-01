---
title: 如何：使用 Polyline 元素来绘制折线
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 4871d357d81ec80b63e69e6af133ae10b4e08b15
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974099"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>如何：使用 Polyline 元素来绘制折线
此示例演示如何使用元素绘制折线，这是一系列连接的直线 <xref:System.Windows.Shapes.Polyline> 。  
  
 若要绘制折线，请创建一个 <xref:System.Windows.Shapes.Polyline> 元素，并使用其 <xref:System.Windows.Shapes.Polyline.Points%2A> 属性指定形状顶点。 最后，使用 <xref:System.Windows.Shapes.Shape.Stroke%2A> 和 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 属性来描述折线轮廓，因为没有描边的线条是不可见的。  
  
> [!NOTE]
> 由于该 <xref:System.Windows.Shapes.Polyline> 元素不是闭合的形状，因此 <xref:System.Windows.Shapes.Shape.Fill%2A> 即使您特意关闭了形状轮廓，此属性也不起作用。 若要使用创建闭合形状 <xref:System.Windows.Shapes.Shape.Fill%2A> ，请使用 <xref:System.Windows.Shapes.Polygon> 元素。  
  
 下面的示例在内绘制两个 <xref:System.Windows.Shapes.Polyline> 元素 <xref:System.Windows.Controls.Canvas> 。  
  
## <a name="example"></a>示例  
 在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，点的有效语法是以空格分隔的、以逗号分隔的 x 和 y 坐标对的列表。  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 虽然此示例使用 <xref:System.Windows.Controls.Canvas> 来包含折线，但你可以使用折线元素 (和所有其他形状元素) <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.Control> 支持非文本内容的任何或。  
  
 此示例摘自一个更大的示例;有关完整示例，请参阅 [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [WPF 中的形状和基本图形概述](shapes-and-basic-drawing-in-wpf-overview.md)
