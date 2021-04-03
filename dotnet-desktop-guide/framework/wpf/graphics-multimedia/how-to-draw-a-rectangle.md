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
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="82526-102">如何：绘制矩形</span><span class="sxs-lookup"><span data-stu-id="82526-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="82526-103">此示例演示如何使用元素绘制矩形 <xref:System.Windows.Shapes.Rectangle> 。</span><span class="sxs-lookup"><span data-stu-id="82526-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="82526-104">若要绘制矩形，请创建一个 <xref:System.Windows.Shapes.Rectangle> 元素，并指定其 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 。</span><span class="sxs-lookup"><span data-stu-id="82526-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="82526-105">若要绘制矩形内部，请将其设置为 <xref:System.Windows.Shapes.Shape.Fill%2A> 。</span><span class="sxs-lookup"><span data-stu-id="82526-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="82526-106">若要为矩形指定轮廓，请使用其 <xref:System.Windows.Shapes.Shape.Stroke%2A> 和 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="82526-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="82526-107">若要为矩形指定圆角，请指定可选的 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 和 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="82526-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="82526-108"><xref:System.Windows.Shapes.Rectangle.RadiusX%2A>和 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 属性设置用于圆角化矩形角的椭圆的 x 轴半径和 y 轴半径。</span><span class="sxs-lookup"><span data-stu-id="82526-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="82526-109">在下面的示例中， <xref:System.Windows.Shapes.Rectangle> 在中绘制了两个元素 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="82526-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="82526-110">第一个矩形的 <xref:System.Windows.Media.Brushes.Blue%2A> 内部。</span><span class="sxs-lookup"><span data-stu-id="82526-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="82526-111">第二个矩形具有 <xref:System.Windows.Media.Brushes.Blue%2A> 内部、 <xref:System.Windows.Media.Brushes.Black%2A> 轮廓和圆角。</span><span class="sxs-lookup"><span data-stu-id="82526-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82526-112">示例</span><span class="sxs-lookup"><span data-stu-id="82526-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="82526-113">虽然此示例使用 <xref:System.Windows.Controls.Canvas> 来包含矩形，但你可以使用矩形元素 (和所有其他形状元素) <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.Control> 支持非文本内容的任何或。</span><span class="sxs-lookup"><span data-stu-id="82526-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="82526-114">事实上，矩形对于为面板的各个部分提供背景特别有用 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="82526-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="82526-115">有关示例，请参阅 [表概述](../advanced/table-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="82526-115">For an example, see the [Table Overview](../advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="82526-116">此示例摘自一个更大的示例;有关完整示例，请参阅 [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。</span><span class="sxs-lookup"><span data-stu-id="82526-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82526-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82526-117">See also</span></span>

- <xref:System.Windows.Shapes.Rectangle>
- [<span data-ttu-id="82526-118">形状元素示例</span><span class="sxs-lookup"><span data-stu-id="82526-118">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="82526-119">WPF 中的形状和基本图形概述</span><span class="sxs-lookup"><span data-stu-id="82526-119">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="82526-120">表概述</span><span class="sxs-lookup"><span data-stu-id="82526-120">Table Overview</span></span>](../advanced/table-overview.md)
