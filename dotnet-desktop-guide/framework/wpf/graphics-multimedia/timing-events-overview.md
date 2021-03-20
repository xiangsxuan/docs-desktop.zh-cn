---
title: 计时事件概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
ms.openlocfilehash: 040fc5697bc52ee3d6acb4bd425f63c3e5781cbf
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667455"
---
# <a name="timing-events-overview"></a>计时事件概述
本主题介绍如何使用和对象上可用的五个计时事件 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> 。  
  
## <a name="prerequisites"></a>必备条件  
 若要了解本主题，应了解如何创建和使用动画。 若要开始处理动画，请参阅 [动画概述](animation-overview.md)。  
  
 可以通过多种方式在中对属性进行动画处理 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ：  
  
- **使用情节提要对象** (标记和代码) ：可以使用 <xref:System.Windows.Media.Animation.Storyboard> 对象排列动画并将其分配给一个或多个对象。 有关示例，请参阅 [使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)。  
  
- **使用本地动画** (仅) 代码：可以直接将 <xref:System.Windows.Media.Animation.AnimationTimeline> 对象应用于它们动画处理的属性。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。  
  
- **使用时钟**（仅代码）：可以显式管理时钟创建并自行分发动画时钟。  有关示例，请参阅 [使用 system.windows.media.animation.animationclock> 对属性进行动画处理](how-to-animate-a-property-by-using-an-animationclock.md)。  
  
 因为你可以在标记和代码中使用它们，所以本概述中的示例使用 <xref:System.Windows.Media.Animation.Storyboard> 对象。 但是，所介绍的概念适用于其他对属性进行动画处理的方法。  
  
### <a name="what-is-a-clock"></a>是什么时钟？  
 除了描述时间段外，时间线本身并无其他任何作用。 它是 <xref:System.Windows.Media.Animation.Clock> 执行实际工作的时间线对象：它为时间线维护与计时相关的运行时状态。 在大多数情况下，比如使用情节提要时，会自动为时间线创建时钟。 你还可以 <xref:System.Windows.Media.Animation.Clock> 使用方法显式创建 <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> 。 有关对象的详细信息 <xref:System.Windows.Media.Animation.Clock> ，请参阅 [动画和计时系统概述](animation-and-timing-system-overview.md)。  
  
## <a name="why-use-events"></a>为什么使用事件？  
 除了一个例外（对齐到上一时钟周期的查找操作），所有交互式计时操作均为异步操作。 无法准确知道它们何时执行。 当存在其他代码依赖于计时操作时，可能会产生问题。 假设你希望停止对矩形进行动画处理的时间线。 在时间线停止后，更改矩形的颜色。  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 在上一示例中，第二行代码可能会在情节提要停止前执行。 这是因为停止操作是异步操作。 告知时间线或时钟停止将创建各种“停止请求”，但它仅在计时引擎的下一时钟周期才会处理。  
  
 若要在时间线完成后执行命令，请使用计时事件。 在下面的示例中，事件处理程序用于在情节提要停止播放后更改矩形的颜色。  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 有关更完整的示例，请参阅 [在时钟状态发生更改时接收通知](how-to-receive-notification-when-clock-state-changes.md)。  
  
## <a name="public-events"></a>公共事件  
 <xref:System.Windows.Media.Animation.Timeline>和 <xref:System.Windows.Media.Animation.Clock> 类都提供了五个计时事件。 下表列出了这些事件及其触发条件。  
  
|事件|触发交互式操作|其他触发器|  
|-----------|--------------------------------------|--------------------|  
|**已完成**|跳过以填充|时钟完成。|  
|**CurrentGlobalSpeedInvalidated**|暂停、恢复、查找、设置速度比、跳过以填充、停止|时钟反转、加速、启动或停止。|  
|**CurrentStateInvalidated**|开始、跳过以填充、停止|时钟开始、停止或填充。|  
|**CurrentTimeInvalidated**|开始、查找、跳过以填充、停止|时钟前进。|  
|**RemoveRequested**|删除||  
  
## <a name="ticking-and-event-consolidation"></a>时钟周期和事件合并  
 对中的对象进行动画处理时 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，它是用于管理动画的计时引擎。 计时引擎跟踪时间进度，并计算每个动画的状态。 它一秒内进行多次计算。 这些计算过程称为“时钟周期”。  
  
 尽管滴答频率很高，但是在两次滴答之间还是有可能会发生许多事情。 例如，时间线可能会停止、启动、再次停止，在这种情况下其当前状态将更改三次。 从理论上讲，在一个时钟周期内，可以多次引发事件；但是，计时引擎会合并事件，因此每个事件在每个时钟周期内只能引发一次。  
  
## <a name="registering-for-events"></a>注册事件  
 可以通过两种方法注册计时事件：使用时间线或使用从时间线创建的时钟进行注册。 直接使用时钟注册事件相当简单，不过该方法只能在代码中执行。 可以在标记或代码中使用时间线注册事件。 下一节介绍如何使用时间线注册时钟事件。  
  
<a name="registeringforclockeventswithatimeline"></a>
## <a name="registering-for-clock-events-with-a-timeline"></a>使用时间线注册时钟事件  
 尽管时间线的 <xref:System.Windows.Media.Animation.Timeline.Completed> 、 <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated> 、 <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> 、 <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated> 和 <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> 事件似乎与时间线相关联，但注册这些事件实际上会将事件处理程序与 <xref:System.Windows.Media.Animation.Clock> 为时间线创建的进行关联。  
  
 <xref:System.Windows.Media.Animation.Timeline.Completed>例如，在时间线上注册事件时，实际上是告诉系统注册为 <xref:System.Windows.Media.Animation.Clock.Completed> 时间线创建的每个时钟的事件。 在代码中，你必须在为 <xref:System.Windows.Media.Animation.Clock> 此时间线创建之前注册此事件; 否则，你将不会收到通知。 这会在中自动发生 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ; 在创建之前，分析器会自动注册事件 <xref:System.Windows.Media.Animation.Clock> 。  
  
## <a name="see-also"></a>请参阅

- [动画和计时系统概述](animation-and-timing-system-overview.md)
- [动画概述](animation-overview.md)
- [计时行为概述](timing-behaviors-overview.md)
