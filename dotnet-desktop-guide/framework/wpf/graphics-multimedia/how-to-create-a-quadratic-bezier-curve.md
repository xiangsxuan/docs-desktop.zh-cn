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
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="23e9c-102">如何：创建二次贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="23e9c-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="23e9c-103">此示例演示如何创建二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="23e9c-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="23e9c-104">若要创建二次贝塞尔曲线，请使用 <xref:System.Windows.Media.PathGeometry> 、 <xref:System.Windows.Media.PathFigure> 和 <xref:System.Windows.Media.QuadraticBezierSegment> 类。</span><span class="sxs-lookup"><span data-stu-id="23e9c-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23e9c-105">示例</span><span class="sxs-lookup"><span data-stu-id="23e9c-105">Example</span></span>  
 <span data-ttu-id="23e9c-106">在下面的示例中，二次贝塞尔曲线从 (10100) 绘制到 (300100) 。</span><span class="sxs-lookup"><span data-stu-id="23e9c-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="23e9c-107">曲线的控制点为 (200200) 。</span><span class="sxs-lookup"><span data-stu-id="23e9c-107">The curve has a control point of (200,200).</span></span>  

 <span data-ttu-id="23e9c-108">在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，可以使用属性语法来描述路径。</span><span class="sxs-lookup"><span data-stu-id="23e9c-108">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  

 <span data-ttu-id="23e9c-109"> (请注意，此特性语法实际上会创建一个 <xref:System.Windows.Media.StreamGeometry> 较轻量版本的 <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="23e9c-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="23e9c-110">有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="23e9c-110">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="23e9c-111">在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，还可以使用对象元素语法绘制二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="23e9c-111">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="23e9c-112">以下内容等效于之前的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="23e9c-112">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="23e9c-113">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。</span><span class="sxs-lookup"><span data-stu-id="23e9c-113">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e9c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23e9c-114">See also</span></span>

- [<span data-ttu-id="23e9c-115">创建椭圆弧</span><span class="sxs-lookup"><span data-stu-id="23e9c-115">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="23e9c-116">创建三次方贝塞尔曲线</span><span class="sxs-lookup"><span data-stu-id="23e9c-116">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
