---
title: 如何：绘制线条
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970216"
---
# <a name="how-to-draw-a-line"></a>如何：绘制线条
此示例演示如何使用元素绘制线条 <xref:System.Windows.Shapes.Line> 。  
  
 若要绘制线条，请创建一个 <xref:System.Windows.Shapes.Line> 元素。 使用其 <xref:System.Windows.Shapes.Line.X1%2A> 和 <xref:System.Windows.Shapes.Line.Y1%2A> 属性设置其开始点，并使用其 <xref:System.Windows.Shapes.Line.X2%2A> 和 <xref:System.Windows.Shapes.Line.Y2%2A> 属性设置其终结点。 最后，设置其 <xref:System.Windows.Shapes.Shape.Stroke%2A> 和， <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 因为没有笔画的行不可见。  
  
 为 <xref:System.Windows.Shapes.Shape.Fill%2A> 直线设置元素不起作用，因为直线没有内部。  
  
 下面的示例在元素内绘制三行 <xref:System.Windows.Controls.Canvas> 。  
  
## <a name="example"></a>示例  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 此示例摘自一个更大的示例;有关完整示例，请参阅 [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Shapes.Line>
- [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
