---
title: 如何：使用 LineGeometry 创建线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: f8c334a54f78aec7af91064a447fd18f23dcfbdc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973312"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a>如何：使用 LineGeometry 创建线条
此示例演示如何使用 <xref:System.Windows.Media.LineGeometry> 类来描述线条。 <xref:System.Windows.Media.LineGeometry>由其起点和终点定义。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建和呈现 <xref:System.Windows.Media.LineGeometry> 。  <xref:System.Windows.Shapes.Path>元素用于呈现线条。  由于行没有区域，因此 <xref:System.Windows.Shapes.Path> 未指定对象的 <xref:System.Windows.Shapes.Shape.Fill%2A> ; 而是 <xref:System.Windows.Shapes.Shape.Stroke%2A> <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 使用和属性。  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![一个 LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
从 (10,20) 绘制到 (100,130) 的 LineGeometry  
  
 其他简单的 geometry 类包括 <xref:System.Windows.Media.LineGeometry> 和 <xref:System.Windows.Media.EllipseGeometry> 。 还可以使用或创建这些几何图形以及更复杂的几何图形 <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> 。 有关详细信息，请参阅 [几何概述](geometry-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- [Geometry 概述](geometry-overview.md)
- [创建复合形状](how-to-create-a-composite-shape.md)
- [使用 PathGeometry 创建形状](how-to-create-a-shape-by-using-a-pathgeometry.md)
