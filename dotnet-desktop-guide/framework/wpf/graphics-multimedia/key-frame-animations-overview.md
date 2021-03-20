---
title: 关键帧动画概述
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], key-frame
- key frames [WPF], about key-frame animations
- multiple animation target values [WPF]
ms.assetid: 10028f97-bb63-41fc-b8ad-663dac7ea203
ms.openlocfilehash: 66609f2ac5161f6e9e1a0b6373adf72b384889ee
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668420"
---
# <a name="key-frame-animations-overview"></a>关键帧动画概述
本主题介绍关键帧动画。 通过关键帧动画，可以使用两个以上的目标值进行动画处理，并控制动画的内插方法。  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>必备条件  
 若要理解本概述，用户应熟悉 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 动画和时间线。 有关动画的简介，请参阅[动画概述](animation-overview.md)。 它还有助于熟悉 From/To/By 动画。 有关详细信息，请参阅“From/To/By 动画概述”。  
  
<a name="whatisakeyframeanimation"></a>
## <a name="what-is-a-key-frame-animation"></a>什么是关键帧动画？  
 与 From/To/By 动画类似，关键帧动画对目标属性的值进行动画处理。 它在其的目标值之间创建转换 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 。 但是，From/To/By 动画可以在两个值之间创建过渡，而单个关键帧动画可以在任意数量的目标值之间创建过渡。 不同于 From/To/By 动画，关键帧动画没有设置其目标值所需的 From、To 或 By 属性。 关键帧动画的目标值使用关键帧对象进行描述，因此称作“关键帧动画”。 若要指定动画的目标值，请创建关键帧对象并将其添加到动画的 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> 集合中。 动画运行时，将在指定的帧之间过渡。  
  
 某些关键帧方法除支持多个目标值外，甚至还支持多个内插方法。 动画的内插方法定义了从一个值过渡到下一个值的方式。 有三种内插类型：离散、线性和曲线。  
  
 若要使用关键帧动画进行动画处理，需要完成下列步骤。  
  
- 声明动画并指定其 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> ，就像对 from/to/by 动画执行此动画。  
  
- 对于每个目标值，创建适当类型的关键帧，设置其值和 <xref:System.Windows.Media.Animation.KeyTime> ，然后将其添加到动画的 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> 集合中。  
  
- 以针对 From/To/By 动画的方式将该动画与属性相关联。 有关使用演示图板将动画应用到属性的详细信息，请参阅[演示图板概述](storyboards-overview.md)。  
  
 下面的示例使用将 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 元素动画处理 <xref:System.Windows.Shapes.Rectangle> 到四个不同的位置。  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
 与 From/To/By 动画一样，可以通过 <xref:System.Windows.Media.Animation.Storyboard> 在标记和代码中使用，或在代码中使用方法，将关键帧动画应用到属性 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 。 你还可以使用关键帧动画来创建 <xref:System.Windows.Media.Animation.AnimationClock> ，并将其应用于一个或多个属性。 有关应用动画的不同方法的详细信息，请参阅 [属性动画技术概述](property-animation-techniques-overview.md)。  
  
<a name="animation_types"></a>
## <a name="key-frame-animation-types"></a>关键帧动画类型  
 由于动画会生成属性值，因此不同的属性类型具有不同的动画类型。 若要对采用 <xref:System.Double> (（如元素的属性) ）的属性进行动画处理 <xref:System.Windows.FrameworkElement.Width%2A> ，请使用生成值的动画 <xref:System.Double> 。 若要对采用的属性进行动画处理 <xref:System.Windows.Point> ，请使用动画生成 <xref:System.Windows.Point> 值，依此类推。  
  
 关键帧动画类属于 <xref:System.Windows.Media.Animation> 命名空间，遵循以下命名约定：  
  
 *\<Type>* `AnimationUsingKeyFrames`  
  
 其中 *\<Type>* 是类动画处理的值的类型。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供了以下关键帧动画类。  
  
|属性类型|对应的 From/To/By 动画类|支持的内插方法|  
|-------------------|------------------------------------------------|-------------------------------------|  
|<xref:System.Boolean>|<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>|离散|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16AnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32AnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64AnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>|离散|  
|<xref:System.Object>|<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>|离散|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.String>|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|离散|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>|离散、线性、曲线|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimationUsingKeyFrames>|离散、线性、曲线|  
  
<a name="animation_target_values"></a>
## <a name="target-values-key-frames-and-key-times"></a>目标值（关键帧）和关键时间  
 就像在对不同属性类型进行动画处理时有不同类型的关键帧动画一样，关键帧对象的类型也各不相同：对于每种进行动画处理的值和所支持的内插方法，都有一个对象类型。 关键帧类型遵循以下命名约定：  
  
 *\<InterpolationMethod>\<Type>* `KeyFrame`  
  
 其中 *\<InterpolationMethod>* 是关键帧使用的内插方法， *\<Type>* 是类对其进行动画处理的值的类型。 支持所有三种内插方法的关键帧动画有三种关键帧类型可供使用。 例如，可以将三个关键帧类型与一起使用 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> ： <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> 、 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> 和 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> 。 （后面部分将对内插方法进行详细说明。）  
  
 关键帧的主要目的是指定 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 和 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 。 每个关键帧类型都可提供这两种属性。  
  
- <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>属性指定关键帧的目标值。  
  
- <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>属性指定 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 到达动画)  (关键帧的时间 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 。  
  
 关键帧动画开始时，按其属性定义的顺序循环访问其关键帧 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 。  
  
- 如果时间0处没有关键帧，动画将在目标属性的当前值与 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 第一个关键帧的之间创建过渡; 否则，动画的输出值将成为第一个关键帧的值。  
  
- 动画会 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 使用第二个关键帧指定的内插方法，在第一个和第二个关键帧之间创建过渡。 转换从第一个关键帧开始 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> ，到第二个关键帧的结束时结束 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 。  
  
- 动画将继续，这会创建每个后续关键帧和其前面的关键帧之间的过渡。  
  
- 最后，动画会转换为关键帧的值，该关键帧的关键时间等于或小于动画的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 。  
  
 如果动画的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 为 <xref:System.Windows.Duration.Automatic%2A> 或其 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 等于最后一个关键帧的时间，则动画结束。 否则，如果动画 <xref:System.Windows.Duration> 大于最后一个关键帧的关键时间，则动画将保持关键帧值，直到到达其末尾 <xref:System.Windows.Duration> 。 与所有动画类似，关键帧动画使用其 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性来确定它在到达其活动期结束时是否持有最终值。 有关详细信息，请参阅[计时行为概述](timing-behaviors-overview.md)。  
  
 下面的示例使用 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 上一示例中定义的对象来演示 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 和属性的 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 工作方式。  
  
- 第一个关键帧立即将动画的输出值设置为 0。  
  
- 第二个关键帧在 0 和 350 之间进行动画处理。 它在第一个关键帧结束后开始（开始时间 = 0 秒），播放 2 秒钟，结束时间 = 0:0:2。  
  
- 第三个关键帧在 350 和 50 之间进行动画处理。 它在第二个关键帧结束时开始（开始时间 = 2 秒），播放 5 秒钟，结束时间 = 0:0:7。  
  
- 第四个关键帧在 50 和 200 之间进行动画处理。 它在第三个关键帧结束时开始（开始时间 = 7 秒），播放 1 秒钟，结束时间 = 0:0:8。  
  
- 由于 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 动画的属性设置为10秒，动画将在结束时间 = 0:0:10 前的两秒内保留其最终值。  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
<a name="interpolationmethods"></a>
## <a name="interpolation-methods"></a>内插方法  
 前面部分提到了某些关键帧动画支持多种内插方法。 动画的内插对动画在其持续时间内在值之间进行过渡的方式进行了描述。 通过选择动画要使用哪种关键帧类型，可以定义该关键帧段的内插方法。 有三种不同类型的内插方法：线性、离散和曲线。  
  
### <a name="linear-interpolation"></a>线性内插  
 使用线性内插，动画将以段持续时间的固定速度进行播放。 例如，如果关键帧段从 0 过渡到 10，持续时间为 5 秒，则动画会在指定时间输出以下值：  
  
|时间|输出值|  
|----------|------------------|  
|0|0|  
|1|2|  
|2|4|  
|3|6|  
|4|8|  
|4.25|8.5|  
|4.5|9|  
|5|10|  
  
### <a name="discrete-interpolation"></a>离散内插  
 使用离散内插，动画函数将从一个值跳到下一个值，没有内插。 如果关键帧段从 0 过渡到 10，持续时间为 5 秒，则动画会在指定时间输出以下值：  
  
|时间|输出值|  
|----------|------------------|  
|0|0|  
|1|0|  
|2|0|  
|3|0|  
|4|0|  
|4.25|0|  
|4.5|0|  
|5|10|  
  
 注意动画在段持续时间恰好结束之前不会更改其输出值的方式。  
  
 曲线内插更为复杂。 相关内容将在下一节介绍。  
  
<a name="anim_spline"></a>
### <a name="splined-interpolation"></a>曲线内插  
 曲线内插可用于达到更现实的计时效果。 由于动画通常用于模拟现实世界中出现的效果，因此开发人员可能需要精确地控制对象的加速和减速，并需要严格地对计时段进行操作。 通过自由绘制曲线关键帧，可以使用曲线内插进行动画处理。 使用其他关键帧，可以指定 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 和 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 。 使用样条关键帧，还可以指定 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> 。 下面的示例演示了单个样条关键帧 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 。 请注意 <xref:System.Windows.Media.Animation.KeySpline> 属性; 这就是使样条关键帧与其他类型的关键帧不同的。  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 一条三次方贝塞尔曲线由一个起点、一个终点和两个控制点定义。 <xref:System.Windows.Media.Animation.KeySpline>样条关键帧的属性定义贝塞尔曲线的两个控制点，该曲线从 (0，0) 延伸到 (1，1) 。 第一个控制点控制贝塞尔曲线前半部分的曲线因子，第二个控制点控制贝塞尔线段后半部分的曲线因子。 生成的曲线描述了该自由绘制曲线关键帧的变化率。 曲线陡度越大，关键帧更改其值的速度越快。 曲线趋于平缓时，关键帧更改其值的速度也趋于缓慢。  
  
 您可以使用 <xref:System.Windows.Media.Animation.KeySpline> 模拟落水或跳动球等物理轨迹，或将其他 "缓入" 和 "渐出" 效果应用于动作动画。 对于用户交互效果（例如背景淡入/淡出或控制按钮弹跳等），可能要应用曲线内插，以便以特定方式提高或降低动画的变化率。  
  
 下面的示例指定一个 <xref:System.Windows.Media.Animation.KeySpline> 0，1 1，0，它创建以下贝塞尔曲线。  
  
 ![贝塞尔曲线](./media/graphicsmm-keyspline-0-1-1-0.png "graphicsmm_keyspline_0_1_1_0")  
控制点为 (0.0, 1.0) 和 (1.0, 0.0) 的主曲线  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 此关键帧的动画处理在开始时快速进行，减速，然后再次加速，直到结束。  
  
 下面的示例指定 <xref:System.Windows.Media.Animation.KeySpline> 0.5，0.25 0.75，1.0，这将创建以下贝塞尔曲线。  
  
 ![贝塞尔曲线](./media/graphicsmm-keyspline-025-050-075-10.png "graphicsmm_keyspline_025_050_075_10")  
控制点为 (0.25, 0.5) 和 (0.75, 1.0) 的主曲线  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  
  
 由于贝塞尔曲线的曲度变化幅度很小，因此该关键帧的动画处理速率几乎固定不变；只在接近结束时才开始减速。  
  
 下面的示例使用 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 对矩形的位置进行动画处理。 由于 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 使用 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> 对象，因此，每个关键帧值之间的转换均使用样条内插。  
  
 [!code-xaml[keyframes_ovw_snippet#SplinedInterpolationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  
  
 曲线内插可能很难理解；使用不同的设置进行体验有助于理解。 通过[主曲线动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/KeySplineAnimations)，可以更改主曲线值，并查看由此所产生的动画结果。  
  
<a name="combininginterpolationmethods"></a>
### <a name="combining-interpolation-methods"></a>组合内插方法  
 可在一个关键帧动画中使用具有不同内插类型的关键帧。 如果两个具有不同内插的关键帧动画彼此跟随，第二个关键帧的内插方法将用于创建从第一个值到第二个值的过渡。  
  
 在下面的示例中， <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 创建了一个使用线性、样条和离散内插的。  
  
 [!code-xaml[keyframes_ovw_snippet#ComboInterpolationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#combointerpolationexample)]  
  
<a name="keytimes"></a>
## <a name="more-about-duration-and-key-times"></a>有关持续时间和关键时间的更多信息  
 与其他动画类似，关键帧动画具有 <xref:System.Windows.Duration> 属性。 除了指定动画的之外 <xref:System.Windows.Duration> ，您还需要指定为每个关键帧提供的持续时间部分。 为此，可以   <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 对动画的每个关键帧进行说明。 每个关键帧 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 指定关键帧结束的时间。  
  
 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>属性不指定关键时间的播放时间。 关键帧的播放时长由关键帧的结束时间、前一个关键帧的结束时间以及动画的持续时间确定。 关键时间可指定为时间值、百分比或特殊值 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 或 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 。  
  
 下表描述了指定关键时间的不同方式。  
  
### <a name="timespan-values"></a>TimeSpan 值  
 您可以使用 <xref:System.TimeSpan> 值指定 <xref:System.Windows.Media.Animation.KeyTime> 。 该值应大于或等于 0 并且小于或等于动画的持续时间。 以下示例演示一个持续时间为 10 秒钟、有四个关键帧（这些关键帧的关键时间指定为时间值）的动画。  
  
- 在前 3 秒钟内，第一个关键帧在基值和 100 之间进行动画处理，结束时间 = 0:0:03。  
  
- 第二个关键帧在 100 和 200 之间进行动画处理。 它在第一个关键帧结束后开始（开始时间 = 3 秒），播放 5 秒钟，结束时间 = 0:0:8。  
  
- 第三个关键帧在 200 和 500 之间进行动画处理。 它在第二个关键帧结束时开始（开始时间 = 8 秒），播放 1 秒钟，结束时间 = 0:0:9。  
  
- 第四个关键帧在 500 和 600 之间进行动画处理。 它在第三个关键帧结束时开始（开始时间 = 9 秒），播放 1 秒钟，结束时间 = 0:0:10。  
  
 [!code-xaml[keyframes_ovw_snippet#TimeSpanKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#timespankeytimeexample)]  
  
### <a name="percentage-values"></a>百分比值  
 百分比值指定关键帧以某些百分比的动画结束 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 。 在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中，指定百分比作为 `%` 符号后的数字。 在代码中，使用 <xref:System.Windows.Media.Animation.KeyTime.FromPercent%2A> 方法并向其传递 <xref:System.Double> 指示百分比的。 该值必须大于或等于 0 并且小于或等于 100%。 以下示例演示一个持续时间为 10 秒钟、有四个关键帧（这些关键帧的关键时间指定为百分比）的动画。  
  
- 在前 3 秒钟内，第一个关键帧将在基值和 100 之间进行动画处理，结束时间 = 0:0:3。  
  
- 第二个关键帧在 100 和 200 之间进行动画处理。 它在第一个关键帧结束后开始（开始时间 = 3 秒），播放 5 秒钟，结束时间 = 0:0:8 (0.8 * 10 = 8)。  
  
- 第三个关键帧在 200 和 500 之间进行动画处理。 它在第二个关键帧结束时开始（开始时间 = 8 秒），播放 1 秒钟，结束时间 = 0:0:9 (0.9 * 10 = 9)。  
  
- 第四个关键帧在 500 和 600 之间进行动画处理。 它在第三个关键帧结束时开始（开始时间 = 9 秒），播放 1 秒钟，结束时间 = 0:0:10 (1 * 10 = 10)。  
  
 [!code-xaml[keyframes_ovw_snippet#PercentageKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#percentagekeytimeexample)]  
  
### <a name="special-value-uniform"></a>特殊值 Uniform  
 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>如果希望每个关键帧需要相同的时间，请使用计时。  
  
 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>关键时间将可用时间平均除以关键帧数，以确定每个关键帧的结束时间。 下面的示例演示一个持续时间为10秒的动画和四个关键帧（其关键时间指定为） <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 。  
  
- 在前 2.5 秒钟内，第一个关键帧在基值和 100 之间进行动画处理，结束时间 = 0:0:2.5。  
  
- 第二个关键帧在 100 和 200 之间进行动画处理。 它在第一个关键帧结束后开始（开始时间 = 2.5 秒），播放大约 2.5 秒钟，结束时间 = 0:0:5。  
  
- 第三个关键帧在 200 和 500 之间进行动画处理。 它在第二个关键帧结束时开始（开始时间 = 5 秒），播放 2.5 秒钟，结束时间 = 0:0:7.5。  
  
- 第四个关键帧在 500 和 600 之间进行动画处理。 它在第二个关键帧结束时开始（开始时间 = 7.5 秒），播放 2.5 秒钟，结束时间 = 0:0:1。  
  
 [!code-xaml[keyframes_ovw_snippet#UniformKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#uniformkeytimeexample)]  
  
### <a name="special-value-paced"></a>特殊值 Paced  
 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>如果要以恒定速率进行动画处理，请使用计时。  
  
 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>关键时间根据每个关键帧的长度分配可用时间，以确定每个帧的持续时间。  这样，动画的速度或速率将保持不变。  下面的示例演示一个持续时间为10秒的动画和三个关键帧（其关键时间指定为） <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 。  
  
 [!code-xaml[keyframes_ovw_snippet#PacedKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#pacedkeytimeexample)]  
  
 请注意，如果最后一个关键帧的关键时间为 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 或 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> ，其解析的关键时间将设置为100%。 如果多帧动画中的第一个关键帧为固定速度，其解析的关键时间将设置为 0。 （如果关键帧集合仅包含一个关键帧，并且是一个固定速度的关键帧，其解析的关键时间将设置为 100%。）  
  
 一个关键帧动画中的不同关键帧可使用不同的关键时间类型。  
  
<a name="combiningkeytimes"></a>
## <a name="combining-key-times-out-of-order-key-frames"></a>组合关键时间，顺序紊乱的关键帧  
 您可以 <xref:System.Windows.Media.Animation.KeyTime> 在同一动画中使用具有不同值类型的关键帧。 尽管建议以关键帧的实际播放顺序来添加关键帧，但此操作不是必需的。 动画和计时系统能够处理顺序紊乱的关键帧。 将忽略关键时间无效的关键帧。  
  
 下表描述了为关键帧动画的关键帧解析关键时间的过程。  
  
1. 解析 <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> 值。  
  
2. 确定动画的 *总内插时间*，即关键帧动画完成向前迭代所需的全部时间。  
  
    1. 如果动画的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 不是 <xref:System.Windows.Duration.Automatic%2A> 或 <xref:System.Windows.Duration.Forever%2A> ，则总内插时间是动画的属性的值 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 。  
  
    2. 否则，总内插时间是在 <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> 其关键帧（如果存在）中指定的最大值。  
  
    3. 否则，总内插时间为 1 秒。  
  
3. 使用总内插时间值来解析 <xref:System.Windows.Media.Animation.KeyTimeType.Percent> <xref:System.Windows.Media.Animation.KeyTime> 值。  
  
4. 如果最后一个关键帧尚未在之前步骤中解析，则将解析该关键帧。 如果 <xref:System.Windows.Media.Animation.KeyTime> 最后一个关键帧的为 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 或，则 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 其解析时间将等于总内插时间。  
  
     如果 <xref:System.Windows.Media.Animation.KeyTime> 第一个关键帧的为 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> ，且此动画在关键帧上具有多个，则将其值解析为 <xref:System.Windows.Media.Animation.KeyTime> 零; 如果只有一个关键帧，并且它的 <xref:System.Windows.Media.Animation.KeyTime> 值为 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> ，则会将其解析为总内插时间，如前一步骤中所述。  
  
5. 解析其余 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> 值：每个值都给定了可用时间的相等份额。  在此过程中，未解析的 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> 值将暂时作为 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> 值处理，并获得临时解析的时间。  
  
6. <xref:System.Windows.Media.Animation.KeyTime>使用未指定关键时间的关键帧来解析关键帧的值 <xref:System.Windows.Media.Animation.KeyTime> 。  
  
7. 解析其余 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> 值。 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A><xref:System.Windows.Media.Animation.KeyTime>使用 <xref:System.Windows.Media.Animation.KeyTime> 相邻关键帧的值来确定其解决时间。  目的是确保动画速度在此关键帧的解析时间内保持固定不变。  
  
8. 按解析时间顺序对关键帧进行排序 (主键) ，并 () 辅助键的顺序，即，根据解析的关键帧值使用稳定排序 <xref:System.Windows.Media.Animation.KeyTime> 。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.KeyTime>
- <xref:System.Windows.Media.Animation.KeySpline>
- <xref:System.Windows.Media.Animation.Timeline>
- [主曲线动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/KeySplineAnimations)
- [关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)
- [动画概述](animation-overview.md)
- [演示图板概述](storyboards-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
- [计时行为概述](timing-behaviors-overview.md)
