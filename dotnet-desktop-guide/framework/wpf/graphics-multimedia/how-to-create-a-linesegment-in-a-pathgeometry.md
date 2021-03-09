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
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a>如何：在 PathGeometry 中创建 LineSegment

此示例演示如何创建一条线段。 若要创建线段，请使用 <xref:System.Windows.Media.PathGeometry> 、 <xref:System.Windows.Media.PathFigure> 和 <xref:System.Windows.Media.LineSegment> 类。

## <a name="example"></a>示例

下面的示例 <xref:System.Windows.Media.LineSegment> 从 (10，50) 绘制到 (200，70) 。 下图显示了所生成的 <xref:System.Windows.Media.LineSegment> ; 添加了网格背景以显示坐标系统。

![System.windows.media.pathfigure> 中的 system.windows.media.linesegment>](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") 从 (10，50) 绘制到 (200，70) 

在 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 中，可以使用属性语法来描述路径。

```xaml
<Path Stroke="Black" StrokeThickness="1"
  Data="M 10,50 L 200,70" />
```

 (请注意，此特性语法实际上会创建一个 <xref:System.Windows.Media.StreamGeometry> 较轻量版本的 <xref:System.Windows.Media.PathGeometry> 。 有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）

在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中，还可以使用对象元素语法来绘制线段。 以下内容等效于之前的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 示例。

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

此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [Geometry 概述](geometry-overview.md)
