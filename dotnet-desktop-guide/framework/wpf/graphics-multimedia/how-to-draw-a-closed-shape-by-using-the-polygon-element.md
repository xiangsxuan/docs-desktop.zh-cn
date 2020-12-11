---
title: 如何：使用多边形元素来绘制闭合形状
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 53359d05555a572796961a82c7b5e95f14ebddc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974100"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>如何：使用多边形元素来绘制闭合形状
此示例演示如何使用元素绘制闭合形状 <xref:System.Windows.Shapes.Polygon> 。 若要绘制闭合形状，请创建一个 <xref:System.Windows.Shapes.Polygon> 元素，并使用其 <xref:System.Windows.Shapes.Polygon.Points%2A> 属性指定形状的顶点。 将自动绘制一条线，用于连接第一个点和最后一个点。 最后，指定 <xref:System.Windows.Shapes.Shape.Fill%2A> 、 <xref:System.Windows.Shapes.Shape.Stroke%2A> 或。  
  
## <a name="example"></a>示例  
 在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，点的有效语法是以空格分隔的、以逗号分隔的 x 和 y 坐标对的列表。  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 尽管该示例使用 <xref:System.Windows.Controls.Canvas> 来包含多边形，但您可以使用多边形元素 (和所有其他形状元素) <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.Control> 支持非文本内容的任何或。  
  
 此示例摘自一个更大的示例;有关完整示例，请参阅 [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。
