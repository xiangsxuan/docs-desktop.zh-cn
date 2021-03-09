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
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="cff96-102">如何：创建椭圆弧</span><span class="sxs-lookup"><span data-stu-id="cff96-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="cff96-103">此示例演示如何绘制椭圆弧。若要创建椭圆弧，请使用 <xref:System.Windows.Media.PathGeometry> 、 <xref:System.Windows.Media.PathFigure> 和 <xref:System.Windows.Media.ArcSegment> 类。</span><span class="sxs-lookup"><span data-stu-id="cff96-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cff96-104">示例</span><span class="sxs-lookup"><span data-stu-id="cff96-104">Example</span></span>  
 <span data-ttu-id="cff96-105">在下面的示例中，将从 (10100) 到 (200100) 绘制一个椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="cff96-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="cff96-106">圆弧具有 <xref:System.Windows.Media.ArcSegment.Size%2A> 100 x 50 与设备无关的像素、 <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 度的、的 <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> 设置 `true` 和 <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> 的 <xref:System.Windows.Media.SweepDirection.Counterclockwise> 。</span><span class="sxs-lookup"><span data-stu-id="cff96-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  

 <span data-ttu-id="cff96-107">在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，可以使用属性语法来描述路径。</span><span class="sxs-lookup"><span data-stu-id="cff96-107">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  

 <span data-ttu-id="cff96-108"> (请注意，此特性语法实际上会创建一个 <xref:System.Windows.Media.StreamGeometry> 较轻量版本的 <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="cff96-108">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="cff96-109">有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="cff96-109">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="cff96-110">在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，还可以通过显式使用对象标记来绘制椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="cff96-110">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="cff96-111">以下与前面的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 标记等效。</span><span class="sxs-lookup"><span data-stu-id="cff96-111">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="cff96-112">此示例摘自一个更大的示例。</span><span class="sxs-lookup"><span data-stu-id="cff96-112">This example is part of a larger sample.</span></span> <span data-ttu-id="cff96-113">有关完整示例，请参阅 [几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。</span><span class="sxs-lookup"><span data-stu-id="cff96-113">For the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff96-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cff96-114">See also</span></span>

- [<span data-ttu-id="cff96-115">创建二次贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="cff96-115">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="cff96-116">创建三次方贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="cff96-116">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
