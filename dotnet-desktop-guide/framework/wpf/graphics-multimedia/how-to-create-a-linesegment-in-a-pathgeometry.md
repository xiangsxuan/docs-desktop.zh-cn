---
title: 如何：在 PathGeometry 中创建 LineSegment
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
ms.openlocfilehash: c76772402bd54d2b835247352155150cdd443351
ms.sourcegitcommit: 754c22d76466a56133dd9a8006ad685fc1cd3d0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511655"
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="95ca7-102">如何：在 PathGeometry 中创建 LineSegment</span><span class="sxs-lookup"><span data-stu-id="95ca7-102">How to: Create a LineSegment in a PathGeometry</span></span>

<span data-ttu-id="95ca7-103">此示例演示如何创建一条线段。</span><span class="sxs-lookup"><span data-stu-id="95ca7-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="95ca7-104">若要创建线段，请使用 <xref:System.Windows.Media.PathGeometry> 、 <xref:System.Windows.Media.PathFigure> 和 <xref:System.Windows.Media.LineSegment> 类。</span><span class="sxs-lookup"><span data-stu-id="95ca7-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>

## <a name="example"></a><span data-ttu-id="95ca7-105">示例</span><span class="sxs-lookup"><span data-stu-id="95ca7-105">Example</span></span>

<span data-ttu-id="95ca7-106">下面的示例 <xref:System.Windows.Media.LineSegment> 从 (10，50) 绘制到 (200，70) 。</span><span class="sxs-lookup"><span data-stu-id="95ca7-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="95ca7-107">下图显示了所生成的 <xref:System.Windows.Media.LineSegment> ; 添加了网格背景以显示坐标系统。</span><span class="sxs-lookup"><span data-stu-id="95ca7-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>

<span data-ttu-id="95ca7-108">![System.windows.media.pathfigure> 中的 system.windows.media.linesegment>](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") 从 (10，50) 绘制到 (200，70) </span><span class="sxs-lookup"><span data-stu-id="95ca7-108">![A LineSegment in a PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") A LineSegment drawn from (10,50) to (200,70)</span></span>

<span data-ttu-id="95ca7-109">在 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 中，可以使用属性语法来描述路径。</span><span class="sxs-lookup"><span data-stu-id="95ca7-109">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1"
  Data="M 10,50 L 200,70" />
```

<span data-ttu-id="95ca7-110"> (请注意，此特性语法实际上会创建一个 <xref:System.Windows.Media.StreamGeometry> 较轻量版本的 <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="95ca7-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="95ca7-111">有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="95ca7-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>

<span data-ttu-id="95ca7-112">在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中，还可以使用对象元素语法来绘制线段。</span><span class="sxs-lookup"><span data-stu-id="95ca7-112">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="95ca7-113">以下内容等效于之前的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="95ca7-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1">
  <Path.Data>
    <PathGeometry>
      <PathFigure StartPoint="10,50">
        <LineSegment Point="200,70" />
      </PathFigure>
    </PathGeometry>
  </Path.Data>
</Path>
```

```csharp
PathFigure myPathFigure = new PathFigure();
myPathFigure.StartPoint = new Point(10, 50);

LineSegment myLineSegment = new LineSegment();
myLineSegment.Point = new Point(200, 70);

PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();
myPathSegmentCollection.Add(myLineSegment);

myPathFigure.Segments = myPathSegmentCollection;

PathFigureCollection myPathFigureCollection = new PathFigureCollection();
myPathFigureCollection.Add(myPathFigure);

PathGeometry myPathGeometry = new PathGeometry();
myPathGeometry.Figures = myPathFigureCollection;

Path myPath = new Path();
myPath.Stroke = Brushes.Black;
myPath.StrokeThickness = 1;
myPath.Data = myPathGeometry;
```

```vb
Dim myPathFigure As New PathFigure()
myPathFigure.StartPoint = New Point(10, 50)

Dim myLineSegment As New LineSegment()
myLineSegment.Point = New Point(200, 70)

Dim myPathSegmentCollection As New PathSegmentCollection()
myPathSegmentCollection.Add(myLineSegment)

myPathFigure.Segments = myPathSegmentCollection

Dim myPathFigureCollection As New PathFigureCollection()
myPathFigureCollection.Add(myPathFigure)

Dim myPathGeometry As New PathGeometry()
myPathGeometry.Figures = myPathFigureCollection

Dim myPath As New Path()
myPath.Stroke = Brushes.Black
myPath.StrokeThickness = 1
myPath.Data = myPathGeometry
```

<span data-ttu-id="95ca7-114">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。</span><span class="sxs-lookup"><span data-stu-id="95ca7-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

## <a name="see-also"></a><span data-ttu-id="95ca7-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95ca7-115">See also</span></span>

- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [<span data-ttu-id="95ca7-116">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="95ca7-116">Geometry Overview</span></span>](geometry-overview.md)
