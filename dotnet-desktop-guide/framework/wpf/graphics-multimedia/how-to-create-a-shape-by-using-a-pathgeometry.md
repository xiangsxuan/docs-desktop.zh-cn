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
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>如何：使用 PathGeometry 创建形状
此示例演示如何使用类创建形状 <xref:System.Windows.Media.PathGeometry> 。 <xref:System.Windows.Media.PathGeometry> 对象由一个或多个 <xref:System.Windows.Media.PathFigure> 对象组成，每个对象 <xref:System.Windows.Media.PathFigure> 表示不同的 "图形" 或形状。 每个 <xref:System.Windows.Media.PathFigure> 对象都由一个或多个 <xref:System.Windows.Media.PathSegment> 对象组成，每个对象表示图形或形状的连接部分。 段类型包括 <xref:System.Windows.Media.LineSegment> 、 <xref:System.Windows.Media.ArcSegment> 和 <xref:System.Windows.Media.BezierSegment> 。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.PathGeometry> 创建一个三角形。 <xref:System.Windows.Media.PathGeometry>使用 <xref:System.Windows.Shapes.Path> 元素显示。  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 下图显示在上一个示例中创建的形状。  
  
 ![一个 PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
使用 System.windows.media.pathgeometry> 创建的三角形  
  
 前面的示例演示了如何创建一个相对简单的形状，即一个三角形。 <xref:System.Windows.Media.PathGeometry>还可以用来创建更复杂的形状，包括弧线和曲线。 有关示例，请参阅 [创建椭圆弧](how-to-create-an-elliptical-arc.md)、 [创建三次方贝塞尔曲线](how-to-create-a-cubic-bezier-curve.md)和 [创建二次贝塞尔曲线](how-to-create-a-quadratic-bezier-curve.md)。  
  
 此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Geometry 概述](geometry-overview.md)
- [几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
