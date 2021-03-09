---
title: 如何：创建三次方贝塞尔曲线
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: b7a1ce63a4869d17eb1d34c486ab7a335d3528d1
ms.sourcegitcommit: 754c22d76466a56133dd9a8006ad685fc1cd3d0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511614"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="bb0c1-102">如何：创建三次方贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="bb0c1-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="bb0c1-103">此示例演示如何创建三次方贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="bb0c1-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="bb0c1-104">若要创建一条三次方贝塞尔曲线，请使用 <xref:System.Windows.Media.PathGeometry> 、 <xref:System.Windows.Media.PathFigure> 和 <xref:System.Windows.Media.BezierSegment> 类。</span><span class="sxs-lookup"><span data-stu-id="bb0c1-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="bb0c1-105">若要显示生成的几何图形，请使用 <xref:System.Windows.Shapes.Path> 元素，或将其与 <xref:System.Windows.Media.GeometryDrawing> 或一起使用 <xref:System.Windows.Media.DrawingContext> 。</span><span class="sxs-lookup"><span data-stu-id="bb0c1-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="bb0c1-106">在下面的示例中，一条三次方贝塞尔曲线从 (10，100) 绘制到 (300，100) 。</span><span class="sxs-lookup"><span data-stu-id="bb0c1-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="bb0c1-107">曲线的控制点为 (100、0)  (200、200) 。</span><span class="sxs-lookup"><span data-stu-id="bb0c1-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb0c1-108">示例</span><span class="sxs-lookup"><span data-stu-id="bb0c1-108">Example</span></span>  

 <span data-ttu-id="bb0c1-109">在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，可以使用缩写标记语法来描述路径。</span><span class="sxs-lookup"><span data-stu-id="bb0c1-109">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]
  
 <span data-ttu-id="bb0c1-110">在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，还可以使用对象标记绘制三次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="bb0c1-110">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="bb0c1-111">以下内容等效于之前的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="bb0c1-111">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="bb0c1-112">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。</span><span class="sxs-lookup"><span data-stu-id="bb0c1-112">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb0c1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb0c1-113">See also</span></span>

- [<span data-ttu-id="bb0c1-114">创建椭圆弧</span><span class="sxs-lookup"><span data-stu-id="bb0c1-114">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="bb0c1-115">在 PathGeometry 中创建 LineSegment</span><span class="sxs-lookup"><span data-stu-id="bb0c1-115">Create a LineSegment in a PathGeometry</span></span>](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [<span data-ttu-id="bb0c1-116">创建三次方贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="bb0c1-116">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
- [<span data-ttu-id="bb0c1-117">创建二次贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="bb0c1-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
