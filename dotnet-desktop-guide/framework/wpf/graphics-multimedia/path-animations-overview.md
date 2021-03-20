---
title: 路径动画概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], paths
- path animations [WPF]
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
ms.openlocfilehash: 2235dd7eaa95adf69a4dc5026b2a3cbf78aa71b1
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667728"
---
# <a name="path-animations-overview"></a>路径动画概述
<a name="introduction"></a>本主题介绍了路径动画，使你能够使用几何路径来生成输出值。 路径动画可用于沿着复杂路径移动和旋转对象。  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>必备条件  
 若要了解本主题，应熟悉 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 动画功能。 有关动画功能的简介，请参阅 [动画概述](animation-overview.md)。  
  
 由于使用 <xref:System.Windows.Media.PathGeometry> 对象定义路径动画，因此还应熟悉 <xref:System.Windows.Media.PathGeometry> 和不同类型的 <xref:System.Windows.Media.PathSegment> 对象。 有关详细信息，请参阅 [几何概述](geometry-overview.md)。  
  
<a name="what_is_a_path_animation"></a>
## <a name="what-is-a-path-animation"></a>什么是路径动画？  
 路径动画是 <xref:System.Windows.Media.Animation.AnimationTimeline> 使用作为其输入的的类型 <xref:System.Windows.Media.PathGeometry> 。 不是像对 From/To/By 动画一样设置 From、To 或 By 属性 () 或者使用关键帧 (用于关键帧动画) 时，可定义几何路径并使用它来设置 `PathGeometry` 路径动画的属性。 路径动画运行时，会从路径中读取 x、y 和角度信息并使用该信息生成其输出。  
  
 路径动画对沿着复杂路径的对象进行动画处理非常有用。 沿着路径移动对象的一种方法是使用 <xref:System.Windows.Media.MatrixTransform> 和 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 来沿复杂路径转换对象。 下面的示例通过使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 对象对的属性进行动画处理，演示了此方法 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> <xref:System.Windows.Media.MatrixTransform> 。 <xref:System.Windows.Media.MatrixTransform>应用于按钮并使其沿着曲线路径移动。 由于 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 属性设置为，因此 `true` 矩形沿路径的切线旋转。  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 有关此示例中使用的路径语法的详细信息 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，请参阅 [路径标记语法](path-markup-syntax.md) 概述。 有关完整示例，请参阅 [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。  
  
 可以通过 <xref:System.Windows.Media.Animation.Storyboard> 在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 和代码中使用，或在代码中使用方法，将路径动画应用到属性 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 。 你还可以使用路径动画来创建 <xref:System.Windows.Media.Animation.AnimationClock> ，并将其应用于一个或多个属性。 有关应用动画的不同方法的详细信息，请参阅 [属性动画技术概述](property-animation-techniques-overview.md)。  
  
<a name="animation_types"></a>
## <a name="path-animation-types"></a>路径动画类型  
 由于动画会生成属性值，因此不同的属性类型具有不同的动画类型。 若要对采用 (的属性 <xref:System.Double> （如) 的 <xref:System.Windows.Media.TranslateTransform.X%2A> 属性）进行动画处理 <xref:System.Windows.Media.TranslateTransform> ，请使用生成值的动画 <xref:System.Double> 。 若要对采用的属性进行动画处理 <xref:System.Windows.Point> ，请使用动画生成 <xref:System.Windows.Point> 值，依此类推。  
  
 路径动画类属于 <xref:System.Windows.Media.Animation> 命名空间，并使用以下命名约定：  
  
 *\<Type>* `AnimationUsingPath`  
  
 其中 *\<Type>* 是类动画处理的值的类型。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供以下路径动画类。  
  
|属性类型|相应的路径动画类|示例|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[沿着路径针对对象进行动画处理（双精度动画）](how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[沿着路径针对对象进行动画处理（矩阵动画）](how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[沿着路径针对对象进行动画处理（点动画）](how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> <xref:System.Windows.Media.Matrix> 从其生成值 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A> 。 当与一起使用时 <xref:System.Windows.Media.MatrixTransform> ， <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 可以沿着路径移动对象。 如果将 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 的属性设置 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 为 `true` ，则它还会沿路径的曲线旋转对象。  
  
 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> <xref:System.Windows.Point> 从其的 x 和 y 坐标生成值 <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A> 。 通过使用 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 对采用值的属性进行动画处理 <xref:System.Windows.Point> ，可以沿着路径移动对象。 <xref:System.Windows.Media.Animation.PointAnimationUsingPath>无法旋转对象。  
  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> <xref:System.Double> 从其生成值 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A> 。 通过设置 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> 属性，您可以指定是否 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 使用路径的 x 坐标、y 坐标或角度作为其输出。 您可以使用 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 来旋转对象或沿 x 轴或 y 轴移动对象。  
  
<a name="pathanimationinput"></a>
## <a name="path-animation-input"></a>路径动画输入  
 每个路径动画类提供 <xref:System.Windows.Media.PathGeometry> 指定其输入的属性。 路径动画使用 <xref:System.Windows.Media.PathGeometry> 来生成其输出值。 <xref:System.Windows.Media.PathGeometry>类可用于描述由弧线、曲线和线条组成的多个复杂图形。  
  
 的核心 <xref:System.Windows.Media.PathGeometry> 是对象的集合， <xref:System.Windows.Media.PathFigure> 这些对象是如此命名的，因为每个图形都描述了中的离散形状 <xref:System.Windows.Media.PathGeometry> 。 每个 <xref:System.Windows.Media.PathFigure> 对象都包含一个或多个 <xref:System.Windows.Media.PathSegment> 对象，每个对象都描述了一个图形段。  
  
 有多种类型的线段。  
  
|线段类型|说明|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|在两点之间创建一条椭圆弧。|  
|<xref:System.Windows.Media.BezierSegment>|在两点之间创建一个三次方贝塞尔曲线。|  
|<xref:System.Windows.Media.LineSegment>|创建两个点之间的直线。|  
|<xref:System.Windows.Media.PolyBezierSegment>|创建一系列三次方贝塞尔曲线。|  
|<xref:System.Windows.Media.PolyLineSegment>|创建一系列直线。|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|创建一系列二次贝塞尔曲线。|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|创建二次贝塞尔曲线。|  
  
 中的段 <xref:System.Windows.Media.PathFigure> 合并为单个几何形状，该形状使用线段的终点作为下一段的起点。 的 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 属性 <xref:System.Windows.Media.PathFigure> 指定绘制第一段的起点。 每个后续段都从上一段的终点开始。 例如， `10,50` `10,150` 可以通过将 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 属性设置为 `10,50` 并创建 <xref:System.Windows.Media.LineSegment> 具有 <xref:System.Windows.Media.LineSegment.Point%2A> 属性设置的 `10,150` 来定义中的垂直线。  
  
 有关对象的详细信息 <xref:System.Windows.Media.PathGeometry> ，请参阅 [几何概述](geometry-overview.md)。  
  
 在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，还可以使用特殊的缩写语法来设置的 <xref:System.Windows.Media.PathGeometry.Figures%2A> 属性 <xref:System.Windows.Media.PathGeometry> 。 有关详细信息，请参阅 [路径标记语法](path-markup-syntax.md) 概述。  
  
 有关此示例中使用的路径语法的详细信息 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，请参阅 [路径标记语法](path-markup-syntax.md) 概述。  
  
## <a name="see-also"></a>请参阅

- [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [路径标记语法](path-markup-syntax.md)
- [路径动画帮助主题](path-animation-how-to-topics.md)
- [动画概述](animation-overview.md)
- [属性动画技术概述](property-animation-techniques-overview.md)
