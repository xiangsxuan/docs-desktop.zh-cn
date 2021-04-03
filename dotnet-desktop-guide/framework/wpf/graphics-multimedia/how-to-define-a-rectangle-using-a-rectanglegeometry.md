---
title: 如何：使用 RectangleGeometry 定义矩形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 146ca7017ee38ad5c1065e59662ac441e7bfbfe2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973311"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>如何：使用 RectangleGeometry 定义矩形
此示例说明如何使用 <xref:System.Windows.Media.RectangleGeometry> 类来描述矩形。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建和呈现 <xref:System.Windows.Media.RectangleGeometry> 。  矩形的相对位置和尺寸由 <xref:System.Windows.Rect> 结构定义。 相对位置是 `50,50` ，高度和宽度均 `25` 创建正方形。 使用画笔绘制矩形的内部 <xref:System.Windows.Media.Brushes.LemonChiffon%2A> ，并使用粗细为的笔画绘制其轮廓 <xref:System.Windows.Media.Brushes.Black%2A> `1` 。  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![一个 RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 虽然此示例使用了一个 <xref:System.Windows.Shapes.Path> 元素来呈现 <xref:System.Windows.Media.RectangleGeometry> ，但有许多其他使用对象的方法 <xref:System.Windows.Media.RectangleGeometry> 。 例如， <xref:System.Windows.Media.RectangleGeometry> 可用于指定的 <xref:System.Windows.UIElement.Clip%2A> 或的 <xref:System.Windows.UIElement> <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> <xref:System.Windows.Media.GeometryDrawing> 。  
  
 其他简单的 geometry 类包括 <xref:System.Windows.Media.LineGeometry> 和 <xref:System.Windows.Media.EllipseGeometry> 。 还可以使用或创建这些几何图形以及更复杂的几何图形 <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> 。  
  
## <a name="see-also"></a>另请参阅

- [Geometry 概述](geometry-overview.md)
- [创建复合形状](how-to-create-a-composite-shape.md)
- [使用 PathGeometry 创建形状](how-to-create-a-shape-by-using-a-pathgeometry.md)
