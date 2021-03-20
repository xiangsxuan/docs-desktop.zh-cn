---
title: 动画和计时系统概述
ms.date: 03/30/2017
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
ms.openlocfilehash: 4a873a562d64b93867c77d5997dafead2fd7bb74
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666551"
---
# <a name="animation-and-timing-system-overview"></a>动画和计时系统概述
本主题介绍计时系统如何使用动画、 <xref:System.Windows.Media.Animation.Timeline> 和 <xref:System.Windows.Media.Animation.Clock> 类对属性进行动画处理。  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>必备条件  
 为了了解本主题，应该能够使用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 动画来对属性进行动画处理，如[动画概述](animation-overview.md)中所述。 本主题还有助于熟悉依赖属性；有关详细信息，请参阅[依赖属性概述](../advanced/dependency-properties-overview.md)。  
  
<a name="timelinesandclocks"></a>
## <a name="timelines-and-clocks"></a>时间线和时钟  
 [动画概述](animation-overview.md)介绍了如何 <xref:System.Windows.Media.Animation.Timeline> 表示时间段，动画是 <xref:System.Windows.Media.Animation.Timeline> 产生输出值的类型。 本身 <xref:System.Windows.Media.Animation.Timeline> 不会执行任何操作，只是描述一段时间。 它是执行实际工作的时间线的 <xref:System.Windows.Media.Animation.Clock> 对象。 同样，动画实际上并不会对属性进行动画处理：动画类描述应如何计算输出值，但它是 <xref:System.Windows.Media.Animation.Clock> 为用于驱动动画输出并将其应用于属性的动画创建的。  
  
 <xref:System.Windows.Media.Animation.Clock>是一种特殊类型的对象，用于维护的与计时相关的运行时状态 <xref:System.Windows.Media.Animation.Timeline> 。 它提供三个对动画和计时系统至关重要的信息： <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A> 、 <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A> 和 <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> 。 <xref:System.Windows.Media.Animation.Clock>通过使用由其 <xref:System.Windows.Media.Animation.Timeline> ： <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 、 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 、等描述的计时行为，确定其当前时间、进度和状态 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 。  
  
 大多数情况下，会 <xref:System.Windows.Media.Animation.Clock> 自动为时间线创建。 使用或方法对进行动画处理时 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> ，会自动为时间线和动画创建时钟，并将其应用于其目标属性。 你还可以使用的 <xref:System.Windows.Media.Animation.Clock> 方法显式创建 <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> <xref:System.Windows.Media.Animation.Timeline> 。 <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType>方法为在其上调用该方法的提供适当类型的时钟 <xref:System.Windows.Media.Animation.Timeline> 。 如果 <xref:System.Windows.Media.Animation.Timeline> 包含子时间线，则还会为 <xref:System.Windows.Media.Animation.Clock> 其创建对象。 生成的 <xref:System.Windows.Media.Animation.Clock> 对象排列在树中，与创建它们的对象树的结构相匹配 <xref:System.Windows.Media.Animation.Timeline> 。  
  
 不同类型的时间线具有不同类型的时钟。 下表显示了 <xref:System.Windows.Media.Animation.Clock> 与某些不同类型对应的类型 <xref:System.Windows.Media.Animation.Timeline> 。  
  
|时间线类型|时钟类型|时钟用途|  
|-------------------|----------------|-------------------|  
|动画 (继承自 <xref:System.Windows.Media.Animation.AnimationTimeline>) |<xref:System.Windows.Media.Animation.AnimationClock>|为依赖属性生成输出值。|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|处理媒体文件。|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|分组和控制其子 <xref:System.Windows.Media.Animation.Clock> 对象|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|分组和控制其子 <xref:System.Windows.Media.Animation.Clock> 对象|  
  
 您可以 <xref:System.Windows.Media.Animation.AnimationClock> 通过使用方法，将您创建的任何对象应用于兼容的依赖项属性 <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> 。  
  
 在性能密集型方案（如对大量类似对象进行动画处理）中，管理自己的 <xref:System.Windows.Media.Animation.Clock> 使用可以提供性能优势。  
  
<a name="timemanager"></a>
## <a name="clocks-and-the-time-manager"></a>时钟和时间管理器  
 对中的对象进行动画处理时 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，时间管理器会管理 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 为时间线创建的对象。 时间管理器是 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 对象树的根，并控制该树中的时间流。  将自动为每个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序创建时间管理器，它对于应用程序开发人员不可见。 时间管理器每秒钟“滴答”多次；每秒发生的实际滴答次数取决于可用的系统资源。 在上述每个滴答期间，时间管理器会计算 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> 计时树中所有对象的状态。  
  
 下图显示时间管理器、和之间的关系， <xref:System.Windows.Media.Animation.AnimationClock> 以及一个动画依赖属性。  
  
 ![计时系统组件](./media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
对属性进行动画处理  
  
 当时间管理器计时周期时，它会更新 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> 应用程序中每个的时间。 如果 <xref:System.Windows.Media.Animation.Clock> 为 <xref:System.Windows.Media.Animation.AnimationClock> ，则它将使用 <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> 从中创建该方法的方法 <xref:System.Windows.Media.Animation.AnimationTimeline> 来计算其当前输出值。 <xref:System.Windows.Media.Animation.AnimationClock> <xref:System.Windows.Media.Animation.AnimationTimeline> 使用当前的本地时间、输入值（通常是属性的基值和默认目标值）提供。 使用方法或其 CLR 访问器检索已进行动画处理的属性的值时 <xref:System.Windows.DependencyObject.GetValue%2A> ，将获得其的输出 <xref:System.Windows.Media.Animation.AnimationClock> 。  
  
#### <a name="clock-groups"></a>时钟组  
 前面部分介绍了不同类型的时间线的不同类型的 <xref:System.Windows.Media.Animation.Clock> 对象。 下图显示时间管理器、 <xref:System.Windows.Media.Animation.ClockGroup> 、、 <xref:System.Windows.Media.Animation.AnimationClock> 和动画依赖属性之间的关系。 为 <xref:System.Windows.Media.Animation.ClockGroup> 对其他时间线进行分组的时间线（如 <xref:System.Windows.Media.Animation.Storyboard> 类）创建，它对动画和其他时间线进行分组。  
  
 ![计时系统组件](./media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
ClockGroup  
  
#### <a name="composition"></a>撰写  
 可以将多个时钟与一个属性相关联，在这种情况下，每个时钟都将上一个时钟的输出值用作其基值。 下图显示了 <xref:System.Windows.Media.Animation.AnimationClock> 应用于同一属性的三个对象。 时钟1 将经过动画处理的属性的基值用作其输入，并使用该值生成输出。 时钟2 将时钟1 的输出用作其输入，并使用该值生成输出。 时钟3 将时钟2 的输出用作其输入，并使用该值生成输出。 如果多个时钟同时影响同一个属性，则认为这些时钟位于一个组合链中。  
  
 ![计时系统组件](./media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
组合链  
  
 请注意，尽管关系是在组合链中对象的输入和输出之间创建的 <xref:System.Windows.Media.Animation.AnimationClock> ，但它们的计时行为不受影响; <xref:System.Windows.Media.Animation.Clock> 对象 (包括 <xref:System.Windows.Media.Animation.AnimationClock> 对象) 对其父对象具有层次结构依赖关系 <xref:System.Windows.Media.Animation.Clock> 。  
  
 若要将多个时钟应用到同一个属性，请 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> 在应用 <xref:System.Windows.Media.Animation.Storyboard> 、动画或时使用 <xref:System.Windows.Media.Animation.AnimationClock> 。  
  
#### <a name="ticks-and-event-consolidation"></a>滴答和事件合并  
 除了计算输出值以外，时间管理器还会在它每滴答一次时执行其他工作：它会确定每个时钟的状态并根据需要引发事件。  
  
 尽管滴答频率很高，但是在两次滴答之间还是有可能会发生许多事情。 例如， <xref:System.Windows.Media.Animation.Clock> 可能会停止、启动和停止，在这种情况下，其 <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> 值将更改三次。 理论上， <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> 事件可能会在单个计时周期内多次引发; 但是，计时引擎会合并事件，以便 <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> 每个时钟周期最多引发一次事件。 这适用于所有计时事件：对于给定的对象，每个类型最多会引发一个事件 <xref:System.Windows.Media.Animation.Clock> 。  
  
 当 <xref:System.Windows.Media.Animation.Clock> 开关状态返回并返回到其在刻度间的原始状态时 (例如，从更改 <xref:System.Windows.Media.Animation.ClockState.Active> 为 <xref:System.Windows.Media.Animation.ClockState.Stopped> 和返回到 <xref:System.Windows.Media.Animation.ClockState.Active>) ，则关联的事件仍会发生。  
  
 有关计时事件的详细信息，请参阅[计时事件概述](timing-events-overview.md)。  
  
<a name="currentvaluesbasevaluesofproperties"></a>
## <a name="current-values-and-base-values-of-properties"></a>属性的当前值和基值  
 可进行动画处理的属性具有两个值：基值和当前值。 使用其 CLR 访问器或方法设置属性时 <xref:System.Windows.DependencyObject.SetValue%2A> ，将设置其基值。 对于尚未进行动画处理的属性，基值和当前值相同。  
  
 在对属性进行动画处理时，将 <xref:System.Windows.Media.Animation.AnimationClock> 设置属性的 *当前* 值。 <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.Media.Animation.AnimationClock> 当为或时，通过其 CLR 访问器或方法检索属性的值将返回的 <xref:System.Windows.Media.Animation.AnimationClock> 输出 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Filling> 。 您可以使用方法检索属性的基值 <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> 。  
  
## <a name="see-also"></a>请参阅

- [动画概述](animation-overview.md)
- [计时事件概述](timing-events-overview.md)
- [计时行为概述](timing-behaviors-overview.md)
