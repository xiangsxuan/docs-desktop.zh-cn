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
# <a name="how-to-draw-a-line"></a><span data-ttu-id="66dd0-102">如何：绘制线条</span><span class="sxs-lookup"><span data-stu-id="66dd0-102">How to: Draw a Line</span></span>
<span data-ttu-id="66dd0-103">此示例演示如何使用元素绘制线条 <xref:System.Windows.Shapes.Line> 。</span><span class="sxs-lookup"><span data-stu-id="66dd0-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="66dd0-104">若要绘制线条，请创建一个 <xref:System.Windows.Shapes.Line> 元素。</span><span class="sxs-lookup"><span data-stu-id="66dd0-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="66dd0-105">使用其 <xref:System.Windows.Shapes.Line.X1%2A> 和 <xref:System.Windows.Shapes.Line.Y1%2A> 属性设置其开始点，并使用其 <xref:System.Windows.Shapes.Line.X2%2A> 和 <xref:System.Windows.Shapes.Line.Y2%2A> 属性设置其终结点。</span><span class="sxs-lookup"><span data-stu-id="66dd0-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="66dd0-106">最后，设置其 <xref:System.Windows.Shapes.Shape.Stroke%2A> 和， <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 因为没有笔画的行不可见。</span><span class="sxs-lookup"><span data-stu-id="66dd0-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="66dd0-107">为 <xref:System.Windows.Shapes.Shape.Fill%2A> 直线设置元素不起作用，因为直线没有内部。</span><span class="sxs-lookup"><span data-stu-id="66dd0-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="66dd0-108">下面的示例在元素内绘制三行 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="66dd0-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66dd0-109">示例</span><span class="sxs-lookup"><span data-stu-id="66dd0-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="66dd0-110">此示例摘自一个更大的示例;有关完整示例，请参阅 [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。</span><span class="sxs-lookup"><span data-stu-id="66dd0-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66dd0-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="66dd0-111">See also</span></span>

- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="66dd0-112">形状元素示例</span><span class="sxs-lookup"><span data-stu-id="66dd0-112">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
