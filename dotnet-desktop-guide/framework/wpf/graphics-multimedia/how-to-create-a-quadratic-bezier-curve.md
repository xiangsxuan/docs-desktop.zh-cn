---
title: 如何：创建二次贝塞尔曲线
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: c74963069f45666798d2201533591745f3c0f7b2
ms.sourcegitcommit: 754c22d76466a56133dd9a8006ad685fc1cd3d0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511627"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a>如何：创建二次贝塞尔曲线
此示例演示如何创建二次贝塞尔曲线。  若要创建二次贝塞尔曲线，请使用 <xref:System.Windows.Media.PathGeometry> 、 <xref:System.Windows.Media.PathFigure> 和 <xref:System.Windows.Media.QuadraticBezierSegment> 类。  
  
## <a name="example"></a>示例  
 在下面的示例中，二次贝塞尔曲线从 (10100) 绘制到 (300100) 。 曲线的控制点为 (200200) 。  

 在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，可以使用属性语法来描述路径。  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  

  (请注意，此特性语法实际上会创建一个 <xref:System.Windows.Media.StreamGeometry> 较轻量版本的 <xref:System.Windows.Media.PathGeometry> 。 有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）  
  
 在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，还可以使用对象元素语法绘制二次贝塞尔曲线。 以下内容等效于之前的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 示例。  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。  
  
## <a name="see-also"></a>另请参阅

- [创建椭圆弧](how-to-create-an-elliptical-arc.md)
- [创建三次方贝塞尔曲线](how-to-create-a-cubic-bezier-curve.md)
