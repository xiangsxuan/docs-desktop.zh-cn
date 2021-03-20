---
title: From To By 动画概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 3e1918c3ed75c77b5de0ccfd1525b3e8b313209f
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665349"
---
# <a name="fromtoby-animations-overview"></a>From/To/By 动画概述
本主题介绍如何使用 From/To/By 动画对依赖属性进行动画处理。 From/To/By 动画创建两个值之间的转换。  
  
<a name="prereq"></a>
## <a name="prerequisites"></a>必备条件  
 若要了解本主题，应熟悉 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 动画功能。 有关动画功能的简介，请参阅 [动画概述](animation-overview.md)。  
  
<a name="whatisanimation"></a>
## <a name="what-is-a-fromtoby-animation"></a>什么是 From/To/By 动画？  
 From/To/By 动画是的一种类型 <xref:System.Windows.Media.Animation.AnimationTimeline> ，它在起始值和结束值之间创建过渡。 完成转换所需的时间取决于 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 动画的。  
  
 可以通过 <xref:System.Windows.Media.Animation.Storyboard> 在标记和代码中使用，或在代码中使用方法，将 From/To/By 动画应用到属性 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 。 你还可以使用 From/To/By 动画来创建 <xref:System.Windows.Media.Animation.AnimationClock> ，并将其应用于一个或多个属性。 有关应用动画的不同方法的详细信息，请参阅 [属性动画技术概述](property-animation-techniques-overview.md)。  
  
 From/To/By 动画的目标值不能超过两个。 如果需要具有两个以上目标值的动画，请使用关键帧。 关键帧动画 [概述](key-frame-animations-overview.md)中介绍了关键帧动画。  
  
<a name="animation_types"></a>
## <a name="fromtoby-animation-types"></a>From/To/By 动画类型  
 由于动画会生成属性值，因此不同的属性类型具有不同的动画类型。 若要对采用的属性（如元素的属性）进行动画处理，请 <xref:System.Double> <xref:System.Windows.FrameworkElement.Width%2A> 使用生成值的动画 <xref:System.Double> 。 若要对采用的属性进行动画处理 <xref:System.Windows.Point> ，请使用生成 <xref:System.Windows.Point> 值的动画，依此类推。  
  
 From/To/By 动画类属于 <xref:System.Windows.Media.Animation> 命名空间，并使用以下命名约定：  
  
 *\<Type>* `Animation`  
  
 其中 *\<Type>* 是类动画处理的值的类型。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供以下 From/To/By 动画类。  
  
|属性类型|对应的 From/To/By 动画类|  
|-------------------|------------------------------------------------|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimation>|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimation>|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16Animation>|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32Animation>|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64Animation>|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimation>|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimation>|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimation>|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimation>|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimation>|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimation>|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimation>|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimation>|  
  
<a name="anim_values"></a>
## <a name="target-values"></a>目标值  
 From/To/By 动画创建两个目标值之间的转换。 通常指定起始值 (使用 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性) 和结束值设置该值， (使用 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性) 设置该值。 但是，还可以仅指定起始值、目标值或偏移值。 在这些类中，动画从要进行动画处理的属性中获取缺少的目标值。 以下列表描述了指定动画目标值的各种方法。  
  
- **起始值**  
  
     <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>如果要显式指定动画的起始值，请使用属性。 您可以单独使用该 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性，也可以使用 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 或 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性。 如果仅指定 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性，则动画将从该值转换为经过动画处理的属性的基值。  
  
- **终止值**  
  
     若要指定动画的结束值，请使用其 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性。 如果 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 单独使用属性，则动画从正在进行动画处理的属性或从应用于同一属性的另一个动画的输出获取其起始值。 可以将 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性与属性一起使用 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> ，以显式指定动画的起始值和结束值。  
  
- **偏移值**  
  
     <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性允许您为动画指定偏移量，而不是显式起始值或终止值。 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>动画的属性指定动画在其持续时间内更改值的程度。 可以单独使用该属性，也可以通过属性来使用 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 。 如果仅指定 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性，则动画会将偏移值添加到属性的基值或另一个动画的输出。  
  
<a name="examples"></a>
## <a name="using-fromtoby-values"></a>使用 From/To/By 值  
 以下各节介绍如何 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 一起使用、 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性。  
  
 本节中的示例每个都使用一个 <xref:System.Windows.Media.Animation.DoubleAnimation> （From/To/By 动画类型）对的属性进行动画处理， <xref:System.Windows.FrameworkElement.Width%2A> 该属性 <xref:System.Windows.Shapes.Rectangle> 为10个与设备无关的像素（高和100与设备无关的像素宽）。  
  
 虽然每个示例都使用 <xref:System.Windows.Media.Animation.DoubleAnimation> ，所有 from/To/by 动画的 from、To 和 by 属性的行为都是相同的。 尽管上述每个示例都使用 <xref:System.Windows.Media.Animation.Storyboard> ，但你可以通过其他方式使用 From/To/By 动画。 有关详细信息，请参阅 [属性动画技术概述](property-animation-techniques-overview.md)。  
  
### <a name="fromto"></a>从/到  
 当你同时设置 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 值时，动画将从属性指定的值前进 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 到属性指定的值 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 。  
  
 下面的示例将 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 的属性设置 <xref:System.Windows.Media.Animation.DoubleAnimation> 为50，并将其 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性设置为300。 因此，的将 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> 从50到300进行动画处理。  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>功能  
 当只设置属性时 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> ，动画将从已进行动画处理的属性的基值或从以前应用到同一个属性的组合动画的输出前进到由属性指定的值 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 。  
  
  ( "组合动画" 是指 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Filling> 以前应用到同一个属性的或动画，该属性在使用移交行为应用当前动画时仍有效 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 。 )   
  
 下面的示例仅将 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 的属性设置 <xref:System.Windows.Media.Animation.DoubleAnimation> 为300。 由于未指定起始值，因此将 <xref:System.Windows.Media.Animation.DoubleAnimation> 使用该属性的基值 (100) <xref:System.Windows.FrameworkElement.Width%2A> 作为其起始值。 的 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> 被动画处理从100到动画的目标值300。  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>通过  
 当只设置动画的 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性时，动画将从要进行动画处理的属性的基值开始，或者从组合动画的输出到该值的总和和属性指定的值 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 。  
  
 下面的示例仅将 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 的属性设置 <xref:System.Windows.Media.Animation.DoubleAnimation> 为300。 由于该示例未指定起始值，因此将 <xref:System.Windows.Media.Animation.DoubleAnimation> 使用属性的基值 <xref:System.Windows.FrameworkElement.Width%2A> 100 作为其起始值。 结束值通过将 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 动画的值300添加到其起始值100：400来确定。 因此，的将 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> 从100到400进行动画处理。  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 设置 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 动画的和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性时，动画将从属性所指定的值前进 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 到由和属性的和指定的值 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 。  
  
 下面的示例将 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 的属性设置 <xref:System.Windows.Media.Animation.DoubleAnimation> 为50，并将其 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性设置为300。 结束值通过将 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 动画的值300添加到其起始值50：350来确定。 因此，的将 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> 从50到350进行动画处理。  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>从  
 当只指定动画的 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 值时，动画将从属性指定的值前进到要进行 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 动画处理的属性的基值或组合动画的输出。  
  
 下面的示例仅将 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 的属性设置 <xref:System.Windows.Media.Animation.DoubleAnimation> 为50。 由于未指定终止值，因此将 <xref:System.Windows.Media.Animation.DoubleAnimation> 使用 <xref:System.Windows.FrameworkElement.Width%2A> 属性100的基值作为其结束值。 的将 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> 从50动画处理到属性的基数值 <xref:System.Windows.FrameworkElement.Width%2A> 100。  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 如果同时设置了 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 动画的和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性，则 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 忽略该属性。  
  
<a name="otheranimationtypes"></a>
## <a name="other-animation-types"></a>其他动画类型  
 From/To/By 动画并不是提供的唯一动画类型 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ：它还提供关键帧动画和路径动画。  
  
- 关键帧动画沿使用关键帧描述的任意数量的目标值进行动画处理。 有关详细信息，请参阅 [关键帧动画概述](key-frame-animations-overview.md)。  
  
- 路径动画从生成输出值 <xref:System.Windows.Media.PathGeometry> 。 有关详细信息，请参阅 [路径动画概述](path-animations-overview.md)。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 还支持创建自己的自定义动画类型。 有关详细信息，请参阅 [自定义动画概述](custom-animations-overview.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [动画概述](animation-overview.md)
- [演示图板概述](storyboards-overview.md)
- [关键帧动画概述](key-frame-animations-overview.md)
- [路径动画概述](path-animations-overview.md)
- [自定义动画概述](custom-animations-overview.md)
- [From、To 和 By 动画目标值示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
