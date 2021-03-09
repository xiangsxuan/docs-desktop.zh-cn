---
title: 如何：创建椭圆弧
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: 4963b671e07255053aef3661a0f7675ef6c5b69f
ms.sourcegitcommit: 754c22d76466a56133dd9a8006ad685fc1cd3d0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511640"
---
# <a name="how-to-create-an-elliptical-arc"></a>如何：创建椭圆弧
此示例演示如何绘制椭圆弧。若要创建椭圆弧，请使用 <xref:System.Windows.Media.PathGeometry> 、 <xref:System.Windows.Media.PathFigure> 和 <xref:System.Windows.Media.ArcSegment> 类。  
  
## <a name="example"></a>示例  
 在下面的示例中，将从 (10100) 到 (200100) 绘制一个椭圆弧。 圆弧具有 <xref:System.Windows.Media.ArcSegment.Size%2A> 100 x 50 与设备无关的像素、 <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 度的、的 <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> 设置 `true` 和 <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> 的 <xref:System.Windows.Media.SweepDirection.Counterclockwise> 。  

 在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，可以使用属性语法来描述路径。  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  

  (请注意，此特性语法实际上会创建一个 <xref:System.Windows.Media.StreamGeometry> 较轻量版本的 <xref:System.Windows.Media.PathGeometry> 。 有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）  
  
 在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，还可以通过显式使用对象标记来绘制椭圆弧。 以下与前面的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 标记等效。  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 此示例摘自一个更大的示例。 有关完整示例，请参阅 [几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。  
  
## <a name="see-also"></a>另请参阅

- [创建二次贝塞尔曲线](how-to-create-a-quadratic-bezier-curve.md)
- [创建三次方贝塞尔曲线](how-to-create-a-cubic-bezier-curve.md)
