---
title: 动画提示和技巧
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting [WPF], animation
- animations [WPF], FillBehavior property
- troubleshooting animation [WPF]
- animating objects [WPF], troubleshooting
- animation tips and tricks [WPF]
- tips and tricks [WPF], animation
- performance troubleshooting [WPF], animation
- animations [WPF], use of system resources
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
ms.openlocfilehash: e0ff60e6119eec4838c98ed9e2e4081694285a8d
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973782"
---
# <a name="animation-tips-and-tricks"></a>动画提示和技巧

使用 WPF 中的动画时，有很多提示和技巧可使动画更好地执行，并为您节省不满。  
  
<a name="generalissuessection"></a>

## <a name="general-issues"></a>一般问题  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>对滚动条或滑块的位置进行动画处理将冻结它  

 如果使用具有 (默认值) 的动画对滚动条或滑块的位置进行动画处理 <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> ，则用户将无法再移动滚动条或滑块。 这是因为，即使动画已结束，它仍然在重写目标属性的基值。 若要停止动画的重写属性的当前值，请将其删除，或为其指定 <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.Stop> 。 有关详细信息和示例，请参阅 [使用情节提要对属性进行动画处理后设置该属性](how-to-set-a-property-after-animating-it-with-a-storyboard.md)。  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>对动画的输出进行动画处理没有效果  

 如果某个对象是另一个动画的输出，则无法对该对象进行动画处理。 例如，如果使用 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 将 <xref:System.Windows.Shapes.Shape.Fill%2A> 从的的动画动画处理 <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Media.RadialGradientBrush> 为 <xref:System.Windows.Media.SolidColorBrush> ，则无法对或的任何属性进行动画处理 <xref:System.Windows.Media.RadialGradientBrush> <xref:System.Windows.Media.SolidColorBrush> 。  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>在对属性进行动画处理后无法更改该属性的值  

 在某些情况下，在对属性进行动画处理后，即使在动画结束后，看起来仍无法更改该属性的值。 这是因为即使动画已结束，它仍然在重写该属性的基值。 若要停止动画的重写属性的当前值，请将其删除，或为其指定 <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.Stop> 。 有关详细信息和示例，请参阅 [使用情节提要对属性进行动画处理后设置该属性](how-to-set-a-property-after-animating-it-with-a-storyboard.md)。  
  
### <a name="changing-a-timeline-has-no-effect"></a>更改时间线没有效果  

 尽管大多数 <xref:System.Windows.Media.Animation.Timeline> 属性都是动画处理的，并且可以进行数据绑定，但更改活动的属性值 <xref:System.Windows.Media.Animation.Timeline> 似乎不起作用。 这是因为，在 <xref:System.Windows.Media.Animation.Timeline> 开始时，计时系统会生成的副本， <xref:System.Windows.Media.Animation.Timeline> 并使用它来创建 <xref:System.Windows.Media.Animation.Clock> 对象。 修改原件对系统的副本没有影响。  
  
 <xref:System.Windows.Media.Animation.Timeline>若要反映更改，必须重新生成时钟并使用它来替换以前创建的时钟。 时钟不会自动重新生成。 以下是应用时间线更改的几种方法：  
  
- 如果时间线是或属于 <xref:System.Windows.Media.Animation.Storyboard> ，则可以通过使用或方法重新应用它的情节提要，使其反映更改 <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 。 这还会产生重新启动动画的附带影响。 在代码中，可以使用 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 方法将演示图板前进到其之前的位置。  
  
- 如果使用方法将动画直接应用到属性 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> ，请 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 再次调用方法并向其传递已修改的动画。  
  
- 如果要直接在时钟级别上工作，请创建并应用一组新的时钟，然后用它们替换之前生成的一组时钟。  
  
 有关时间线和时钟的详细信息，请参阅 [动画和计时系统概述](animation-and-timing-system-overview.md)。  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop 不按预期方式工作  

 在某些情况 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 下，将属性设置为 <xref:System.Windows.Media.Animation.FillBehavior.Stop> 看起来不起作用，例如当某个动画的设置为时，会将其设置为 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> 。  
  
 下面的示例创建一个 <xref:System.Windows.Controls.Canvas> 、一个 <xref:System.Windows.Shapes.Rectangle> 和一个 <xref:System.Windows.Media.TranslateTransform> 。 <xref:System.Windows.Media.TranslateTransform>将进行动画处理，以移动 <xref:System.Windows.Shapes.Rectangle> 周围的 <xref:System.Windows.Controls.Canvas> 。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 本节中的示例使用前面的对象来说明 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性不会像预期那样工作的几种情况。  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>针对多个动画的 FillBehavior="Stop" 和 HandoffBehavior  

 有时，动画 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 会在替换为第二个动画时忽略其属性。 使用下面的示例，该示例创建两个 <xref:System.Windows.Media.Animation.Storyboard> 对象，并使用它们对 <xref:System.Windows.Media.TranslateTransform> 上一个示例中显示的相同的对象进行动画处理。  
  
 第一个是， <xref:System.Windows.Media.Animation.Storyboard> `B1` <xref:System.Windows.Media.TranslateTransform.X%2A> 将的属性 <xref:System.Windows.Media.TranslateTransform> 从0动画处理到350，这会将矩形350像素向右移动。 当动画到达其持续时间的末尾并停止播放时， <xref:System.Windows.Media.TranslateTransform.X%2A> 属性将恢复为其原始值0。 因此，矩形向右移动 350 像素，然后跳回其原始位置。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 第二个还将对 <xref:System.Windows.Media.Animation.Storyboard> `B2` 相同的属性进行动画处理 <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform> 。 由于仅 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 设置了此中动画的属性 <xref:System.Windows.Media.Animation.Storyboard> ，因此动画将使用其动画处理的属性的当前值作为其起始值。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 如果在第一次播放时单击第二个按钮 <xref:System.Windows.Media.Animation.Storyboard> ，可能会出现以下行为：  
  
1. 第一个情节提要结束并将该矩形发送回其原始位置，因为动画具有 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 的 <xref:System.Windows.Media.Animation.FillBehavior.Stop> 。  
  
2. 第二个情节提要生效，从当前位置（现在为 0）播放动画到 500。  
  
 **但情况并非如此。** 矩形没有跳回，而是继续向右移动。 这是因为第二个动画使用第一个动画的当前值作为其起始值，并从该值开始播放动画到 500。 当第二个动画替换第一个动画时 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> ，由于使用了，因此 <xref:System.Windows.Media.Animation.FillBehavior> 第一个动画的不重要。  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior 和 Completed 事件  

 下一个示例演示另一种 <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 看起来不起作用的情况。 同样，该示例使用情节提要将 <xref:System.Windows.Media.TranslateTransform.X%2A> 的属性从0动画处理为 <xref:System.Windows.Media.TranslateTransform> 350。 但这次，此示例将注册 <xref:System.Windows.Media.Animation.Timeline.Completed> 事件。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 此 <xref:System.Windows.Media.Animation.Timeline.Completed> 事件处理程序将 <xref:System.Windows.Media.Animation.Storyboard> 从其当前值到500的动画处理开始的另一个。  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 下面是将秒定义为资源的标记 <xref:System.Windows.Media.Animation.Storyboard> 。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 当您运行时 <xref:System.Windows.Media.Animation.Storyboard> ，您可能希望 <xref:System.Windows.Media.TranslateTransform.X%2A> 的属性 <xref:System.Windows.Media.TranslateTransform> 从0到350进行动画处理，然后在完成后恢复为 0 (因为它的 <xref:System.Windows.Media.Animation.FillBehavior> 设置为 <xref:System.Windows.Media.Animation.FillBehavior.Stop>) ，然后从0到500进行动画处理。 相反， <xref:System.Windows.Media.TranslateTransform> 动画从0到350，再到500。  
  
 这是因为 WPF 引发事件的顺序，并且因为属性值已缓存并且不会重新计算，除非属性无效。 <xref:System.Windows.Media.Animation.Timeline.Completed>首先处理该事件，因为它是由第一个)  (的根时间线触发的 <xref:System.Windows.Media.Animation.Storyboard> 。 此时， <xref:System.Windows.Media.TranslateTransform.X%2A> 属性仍返回其动画值，因为它尚未失效。 第二个 <xref:System.Windows.Media.Animation.Storyboard> 使用缓存的值作为其起始值并开始对其进行动画处理。  
  
<a name="performancesection"></a>

## <a name="performance"></a>性能  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>在导航离开页面后动画继续运行  

 当你离开 <xref:System.Windows.Controls.Page> 包含正在运行的动画的时，这些动画将继续播放，直到 <xref:System.Windows.Controls.Page> 经过垃圾回收。 根据正在使用的导航系统，导航离开的页面可能无限期地保留在内存中，在此期间始终通过动画消耗资源。 当页面包含不断运行的（“氛围”）动画时，这一点最明显。  
  
 出于此原因， <xref:System.Windows.FrameworkElement.Unloaded> 当您离开页面时，最好使用事件删除动画。  
  
 删除动画有多种不同的方法。 可以使用以下方法删除属于的动画 <xref:System.Windows.Media.Animation.Storyboard> 。  
  
- 若要删除 <xref:System.Windows.Media.Animation.Storyboard> 你开始使用事件触发器的，请参阅 [如何：删除情节提要](/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90))。  
  
- 若要使用代码删除 <xref:System.Windows.Media.Animation.Storyboard> ，请参见 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> 方法。  
  
 无论动画如何启动，都可以使用下一个技术。  
  
- 若要从特定属性中删除动画，请使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 方法。 将要进行动画处理的属性指定为第一个参数，并将指定 `null` 为第二个参数。 这将从该属性中删除所有动画时钟。  
  
 有关对属性进行动画处理的不同方法的详细信息，请参阅 [属性动画技术概述](property-animation-techniques-overview.md)。  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>使用组合 HandoffBehavior 会消耗系统资源  

 <xref:System.Windows.Media.Animation.Storyboard>使用将、或应用 <xref:System.Windows.Media.Animation.AnimationTimeline> <xref:System.Windows.Media.Animation.AnimationClock> 到属性时 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> ， <xref:System.Windows.Media.Animation.Clock> 以前与该属性关联的任何对象将继续使用系统资源; 计时系统不会自动删除这些时钟。  
  
 若要避免在使用应用大量时钟时出现性能问题 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> ，应在完成后从动画属性中删除组合时钟。 删除时钟有多种方法。  
  
- 若要从属性中删除所有时钟，请 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> 使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 动画对象的或方法。 将要进行动画处理的属性指定为第一个参数，并将指定 `null` 为第二个参数。 这将从该属性中删除所有动画时钟。  
  
- 若要从时钟列表中删除特定的 <xref:System.Windows.Media.Animation.AnimationClock> ，请使用 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 的属性 <xref:System.Windows.Media.Animation.AnimationClock> 来检索 <xref:System.Windows.Media.Animation.ClockController> ，然后调用的 <xref:System.Windows.Media.Animation.ClockController.Remove%2A> 方法 <xref:System.Windows.Media.Animation.ClockController> 。 通常在 <xref:System.Windows.Media.Animation.Clock.Completed> 时钟的事件处理程序中完成此操作。 请注意，只能通过控制根时钟， <xref:System.Windows.Media.Animation.ClockController> <xref:System.Windows.Media.Animation.Clock.Controller%2A> 子时钟的属性将返回 `null` 。 另请注意， <xref:System.Windows.Media.Animation.Clock.Completed> 如果时钟的有效持续时间是永久性的，则不会调用事件。  在这种情况下，用户将需要确定何时调用 <xref:System.Windows.Media.Animation.ClockController.Remove%2A> 。  
  
 此动画问题主要出现在生存期较长的对象上。  当对某个对象进行垃圾回收时，它的时钟也会断开连接并进行垃圾回收。  
  
 有关时钟对象的详细信息，请参阅 [动画和计时系统概述](animation-and-timing-system-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
