---
title: 如何：使用 PathGeometry 创建形状
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973419"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="b3bd5-102">如何：使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="b3bd5-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="b3bd5-103">此示例演示如何使用类创建形状 <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="b3bd5-104"><xref:System.Windows.Media.PathGeometry> 对象由一个或多个 <xref:System.Windows.Media.PathFigure> 对象组成，每个对象 <xref:System.Windows.Media.PathFigure> 表示不同的 "图形" 或形状。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="b3bd5-105">每个 <xref:System.Windows.Media.PathFigure> 对象都由一个或多个 <xref:System.Windows.Media.PathSegment> 对象组成，每个对象表示图形或形状的连接部分。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="b3bd5-106">段类型包括 <xref:System.Windows.Media.LineSegment> 、 <xref:System.Windows.Media.ArcSegment> 和 <xref:System.Windows.Media.BezierSegment> 。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3bd5-107">示例</span><span class="sxs-lookup"><span data-stu-id="b3bd5-107">Example</span></span>  
 <span data-ttu-id="b3bd5-108">下面的示例使用 <xref:System.Windows.Media.PathGeometry> 创建一个三角形。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="b3bd5-109"><xref:System.Windows.Media.PathGeometry>使用 <xref:System.Windows.Shapes.Path> 元素显示。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="b3bd5-110">下图显示在上一个示例中创建的形状。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="b3bd5-111">![一个 PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="b3bd5-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="b3bd5-112">使用 System.windows.media.pathgeometry> 创建的三角形</span><span class="sxs-lookup"><span data-stu-id="b3bd5-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="b3bd5-113">前面的示例演示了如何创建一个相对简单的形状，即一个三角形。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="b3bd5-114"><xref:System.Windows.Media.PathGeometry>还可以用来创建更复杂的形状，包括弧线和曲线。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="b3bd5-115">有关示例，请参阅 [创建椭圆弧](how-to-create-an-elliptical-arc.md)、 [创建三次方贝塞尔曲线](how-to-create-a-cubic-bezier-curve.md)和 [创建二次贝塞尔曲线](how-to-create-a-quadratic-bezier-curve.md)。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="b3bd5-116">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。</span><span class="sxs-lookup"><span data-stu-id="b3bd5-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3bd5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3bd5-117">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="b3bd5-118">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="b3bd5-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="b3bd5-119">几何图形示例</span><span class="sxs-lookup"><span data-stu-id="b3bd5-119">Geometries Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
