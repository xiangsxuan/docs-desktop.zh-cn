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
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="7a2f6-102">如何：使用 Polyline 元素来绘制折线</span><span class="sxs-lookup"><span data-stu-id="7a2f6-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="7a2f6-103">此示例演示如何使用元素绘制折线，这是一系列连接的直线 <xref:System.Windows.Shapes.Polyline> 。</span><span class="sxs-lookup"><span data-stu-id="7a2f6-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="7a2f6-104">若要绘制折线，请创建一个 <xref:System.Windows.Shapes.Polyline> 元素，并使用其 <xref:System.Windows.Shapes.Polyline.Points%2A> 属性指定形状顶点。</span><span class="sxs-lookup"><span data-stu-id="7a2f6-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="7a2f6-105">最后，使用 <xref:System.Windows.Shapes.Shape.Stroke%2A> 和 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 属性来描述折线轮廓，因为没有描边的线条是不可见的。</span><span class="sxs-lookup"><span data-stu-id="7a2f6-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a2f6-106">由于该 <xref:System.Windows.Shapes.Polyline> 元素不是闭合的形状，因此 <xref:System.Windows.Shapes.Shape.Fill%2A> 即使您特意关闭了形状轮廓，此属性也不起作用。</span><span class="sxs-lookup"><span data-stu-id="7a2f6-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="7a2f6-107">若要使用创建闭合形状 <xref:System.Windows.Shapes.Shape.Fill%2A> ，请使用 <xref:System.Windows.Shapes.Polygon> 元素。</span><span class="sxs-lookup"><span data-stu-id="7a2f6-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="7a2f6-108">下面的示例在内绘制两个 <xref:System.Windows.Shapes.Polyline> 元素 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="7a2f6-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a2f6-109">示例</span><span class="sxs-lookup"><span data-stu-id="7a2f6-109">Example</span></span>  
 <span data-ttu-id="7a2f6-110">在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，点的有效语法是以空格分隔的、以逗号分隔的 x 和 y 坐标对的列表。</span><span class="sxs-lookup"><span data-stu-id="7a2f6-110">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="7a2f6-111">虽然此示例使用 <xref:System.Windows.Controls.Canvas> 来包含折线，但你可以使用折线元素 (和所有其他形状元素) <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.Control> 支持非文本内容的任何或。</span><span class="sxs-lookup"><span data-stu-id="7a2f6-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="7a2f6-112">此示例摘自一个更大的示例;有关完整示例，请参阅 [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。</span><span class="sxs-lookup"><span data-stu-id="7a2f6-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a2f6-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a2f6-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="7a2f6-114">形状元素示例</span><span class="sxs-lookup"><span data-stu-id="7a2f6-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="7a2f6-115">WPF 中的形状和基本图形概述</span><span class="sxs-lookup"><span data-stu-id="7a2f6-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
