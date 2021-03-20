---
title: 计时行为概述
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 7eced16269c21abf3021ac09f52cf54db95aaea7
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668638"
---
# <a name="timing-behaviors-overview"></a>计时行为概述
本主题介绍动画和其他对象的计时行为 <xref:System.Windows.Media.Animation.Timeline> 。  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>必备条件  
 若要了解本主题，应熟悉基本动画功能。 有关详细信息，请参阅 [动画概述](animation-overview.md)。  
  
<a name="timelinetypes"></a>
## <a name="timeline-types"></a>时间线类型  
 <xref:System.Windows.Media.Animation.Timeline>表示时间段。 它提供的属性让你可以指定该时间段的长度、开始时间、重复次数、该时间段内时间进度的快慢等。  
  
 从时间线类继承的类可提供附加功能，例如动画和媒体播放。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供以下 <xref:System.Windows.Media.Animation.Timeline> 类型。  
  
|时间线类型|说明|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|<xref:System.Windows.Media.Animation.Timeline>生成用于对属性进行动画处理的输出值的对象的抽象基类。|  
|<xref:System.Windows.Media.MediaTimeline>|从媒体文件生成输出。|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.TimelineGroup>用于对子对象进行分组和控制的一种类型 <xref:System.Windows.Media.Animation.Timeline> 。|  
|<xref:System.Windows.Media.Animation.Storyboard>|的一种类型，它为 <xref:System.Windows.Media.Animation.ParallelTimeline> 其包含的时间线对象提供目标信息。|  
|<xref:System.Windows.Media.Animation.Timeline>|定义计时行为的抽象基类。|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|<xref:System.Windows.Media.Animation.Timeline>可包含其他对象的对象的抽象类 <xref:System.Windows.Media.Animation.Timeline> 。|  
  
<a name="propertiesthatcontroltimelinelength"></a>
## <a name="properties-that-control-the-length-of-a-timeline"></a>用于控制时间线长度的属性  
 <xref:System.Windows.Media.Animation.Timeline>表示时间段，并且可以通过不同的方式描述时间线的长度。 下表定义了几个用于描述时间线长度的术语。  
  
|术语|说明|属性||||  
|----------|-----------------|----------------|-|-|-|  
|简单持续时间|时间线向前迭代一次所需的时间长度。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|一次重复|时间线向前播放一次所花的时间长度，如果该 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 属性为 true，则向后播放一次。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|活动期|时间线完成其属性所指定的所有重复的时间长度 <xref:System.Windows.Media.Animation.RepeatBehavior> 。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>
### <a name="the-duration-property"></a>Duration 属性  
 如前文所述，时间线表示时间段。 该时间段的长度由时间线的确定 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 。 当时间线到达其持续时间的终点时，就会停止播放。 如果时间线具有子时间线，这些子时间线也会停止播放。 对于动画， <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 指定动画从其起始值过渡到其结束值需要多长时间。 时间线的持续时间有时称为 *简单持续时间*，用于区分单个迭代的持续时间和动画播放的总时间（包括重复）。 您可以使用有限时间值或特殊值或来指定持续时间 <xref:System.Windows.Duration.Automatic%2A> <xref:System.Windows.Duration.Forever%2A> 。 动画的持续时间应该解析为一个 <xref:System.Windows.Duration.TimeSpan%2A> 值，因此它可以在值之间过渡。  
  
 下面的示例演示了 <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 秒的。  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 容器时间线（如 <xref:System.Windows.Media.Animation.Storyboard> 和 <xref:System.Windows.Media.Animation.ParallelTimeline> ）的默认持续时间为 <xref:System.Windows.Duration.Automatic%2A> ，这意味着在其最后一个子级停止播放时，它们会自动结束。 下面的示例显示了 <xref:System.Windows.Media.Animation.Storyboard> 一个 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> ，其解析为5秒，这是其所有子对象完成所用的时间长度 <xref:System.Windows.Media.Animation.DoubleAnimation> 。  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 通过将 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 容器时间线的设置为 <xref:System.Windows.Duration.TimeSpan%2A> 值，你可以强制播放比它的子对象更长或更短的时间 <xref:System.Windows.Media.Animation.Timeline> 。 如果将设置 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 为一个小于容器时间线的子对象长度的值 <xref:System.Windows.Media.Animation.Timeline> ，则 <xref:System.Windows.Media.Animation.Timeline> 当容器时间线完成时，子对象将停止播放。 下面的示例将 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.Storyboard> 从前面的示例中设置为三秒。 因此，当首次在 <xref:System.Windows.Media.Animation.DoubleAnimation> 三秒后开始播放时，它会将目标矩形的宽度设定为60。  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>
### <a name="the-repeatbehavior-property"></a>RepeatBehavior 属性  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>控件的属性， <xref:System.Windows.Media.Animation.Timeline> 它重复其简单持续时间。 通过使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性，您可以指定时间线 (迭代) 的次数，或指定在 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 重复)  (应播放的总时间长度 <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A> 。 无论是哪一种情况，动画都将从头到尾运行很多次，直到完成要求的次数或经历完所需的一段时间。 默认情况下，时间线的迭代次数为 `1.0` ，这意味着它们只播放一次，根本不重复。  
  
 下面的示例 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> 通过指定迭代次数，使用属性将播放时间设置为其简单持续时间的两倍。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 下一个示例使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性，使 <xref:System.Windows.Media.Animation.DoubleAnimation> 播放的简单持续时间减半。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 如果将的 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性设置 <xref:System.Windows.Media.Animation.Timeline> 为 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> ，则会重复执行， <xref:System.Windows.Media.Animation.Timeline> 直到以交互方式或通过计时系统停止。 下面的示例使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性来 <xref:System.Windows.Media.Animation.DoubleAnimation> 无限期地播放。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 有关其他示例，请参阅 [重复使用动画](how-to-repeat-an-animation.md)。  
  
<a name="autoreverseproperty"></a>
### <a name="the-autoreverse-property"></a>AutoReverse 属性  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性指定是否 <xref:System.Windows.Media.Animation.Timeline> 将在每次向前迭代结束时向后播放。 下面的示例将的属性设置为 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> `true` ; 因此，它在从零到100，然后从100到零进行动画处理。 它的总播放时长为 10 秒。  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 当你使用 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 值指定的， <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 并且的 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 属性 <xref:System.Windows.Media.Animation.Timeline> 为时 `true` ，单个重复由一个向前迭代后跟一个向后迭代。  下面的示例将 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> 从前面的示例中的的设置为 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 二的。 因此， <xref:System.Windows.Media.Animation.DoubleAnimation> 播放时间为20秒：前进5秒，反向5秒，再前进5秒，然后向后翻5秒。  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 如果容器时间线具有子 <xref:System.Windows.Media.Animation.Timeline> 对象，则当容器时间线执行时，它们会反转。 有关其他示例，请参阅 [指定时间线是否自动反转](how-to-specify-whether-a-timeline-automatically-reverses.md)。  
  
<a name="timelinebegin"></a>
## <a name="the-begintime-property"></a>BeginTime 属性  
 使用 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 属性可以指定时间线的开始时间。  时间线的开始时间相对于其父时间线。 如果开始时间为零秒，则表示其父时间线开始后，该时间线立即开始；如果开始时间为其他值，会在父时间线和子时间线的开始播放时间之间产生时间偏差。 例如，如果开始时间为两秒，则表示在其父时间线到达两秒后，该时间线才开始播放。 默认情况下，所有时间线的开始时间都为零秒。 您还可以将时间线的开始时间设置为 `null` ，这会阻止时间线启动。 在中 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，可以使用 [X:Null 标记扩展](/dotnet/desktop-wpf/xaml-services/xnull-markup-extension)来指定 null。  
  
 请注意，每当时间线因为其设置而重复时，就不会应用开始时间 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 。 如果创建的动画的 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 时间为10秒，且为，则 <xref:System.Windows.Media.Animation.RepeatBehavior> 在 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> 动画第一次播放之前会出现10秒的延迟，但对于每个连续的重复，则不会出现延迟。 但是，如果动画的父时间线重新开始或重复，则会延迟 10 秒。  
  
 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>属性对于错开时间线非常有用。 下面的示例创建一个 <xref:System.Windows.Media.Animation.Storyboard> 具有两个子 <xref:System.Windows.Media.Animation.DoubleAnimation> 对象的。 第一个动画的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 时间为5秒，第二个动画的时间为 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 3 秒。 该示例将秒的设置 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> 为5秒，使其在第一次结束后开始播放 <xref:System.Windows.Media.Animation.DoubleAnimation> 。  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>
## <a name="the-fillbehavior-property"></a>FillBehavior 属性  
 当 <xref:System.Windows.Media.Animation.Timeline> 达到其活动总持续时间的结束时间时，该 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性指定它是停止还是保留其最后一个值。 具有 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "保存" 其输出值的动画：要进行动画处理的属性将保留动画的最后一个值。 的值 <xref:System.Windows.Media.Animation.FillBehavior.Stop> 导致动画在结束后停止影响其目标属性。  
  
 下面的示例创建一个 <xref:System.Windows.Media.Animation.Storyboard> 具有两个子 <xref:System.Windows.Media.Animation.DoubleAnimation> 对象的。 这两个 <xref:System.Windows.Media.Animation.DoubleAnimation> 对象都将 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> 从0到100的进行了动画处理。 <xref:System.Windows.Shapes.Rectangle>元素的非动画 <xref:System.Windows.FrameworkElement.Width%2A> 值为 500 [与设备无关的像素]。  
  
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>第一个的属性 <xref:System.Windows.Media.Animation.DoubleAnimation> 设置为 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> ，默认值为。 因此，矩形的宽度在结束后保持为 100 <xref:System.Windows.Media.Animation.DoubleAnimation> 。  
  
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>第二个的属性 <xref:System.Windows.Media.Animation.DoubleAnimation> 设置为 <xref:System.Windows.Media.Animation.FillBehavior.Stop> 。 因此， <xref:System.Windows.FrameworkElement.Width%2A> 第二个在 <xref:System.Windows.Shapes.Rectangle> 结束后恢复为 500 <xref:System.Windows.Media.Animation.DoubleAnimation> 。  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>
## <a name="properties-that-control-the-speed-of-a-timeline"></a>用于控制时间线速度的属性  
 <xref:System.Windows.Media.Animation.Timeline>类提供了三个用于指定其速度的属性：  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> –指定相对于其父级的速率，此时对的时间进行 <xref:System.Windows.Media.Animation.Timeline> 。 大于1的值将提高 <xref:System.Windows.Media.Animation.Timeline> 及其子对象的速度 <xref:System.Windows.Media.Animation.Timeline> ; 0 和1之间的值将减慢。 值为1指示以与 <xref:System.Windows.Media.Animation.Timeline> 父项相同的速率进行进度。 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>容器时间线的设置也会影响其所有子 <xref:System.Windows.Media.Animation.Timeline> 对象。  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> –指定 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 时间线的加速所用的百分比。 有关示例，请参阅 [如何：加速或减速动画](how-to-accelerate-or-decelerate-an-animation.md)。
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> -指定 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 用于减速的时间线的百分比。 有关示例，请参阅 [如何：加速或减速动画](how-to-accelerate-or-decelerate-an-animation.md)。  
  
## <a name="see-also"></a>请参阅

- [动画概述](animation-overview.md)
- [动画和计时系统概述](animation-and-timing-system-overview.md)
- [计时事件概述](timing-events-overview.md)
- [操作指南主题](animation-and-timing-how-to-topics.md)
- [动画计时行为示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
