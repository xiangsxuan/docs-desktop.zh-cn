---
title: 如何：重复动画
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973920"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="9ad29-102">如何：重复动画</span><span class="sxs-lookup"><span data-stu-id="9ad29-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="9ad29-103">此示例演示如何使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 的属性 <xref:System.Windows.Media.Animation.Timeline> 来控制动画的重复行为。</span><span class="sxs-lookup"><span data-stu-id="9ad29-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ad29-104">示例</span><span class="sxs-lookup"><span data-stu-id="9ad29-104">Example</span></span>  
 <span data-ttu-id="9ad29-105">的 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性 <xref:System.Windows.Media.Animation.Timeline> 控制动画重复其简单持续时间的次数。</span><span class="sxs-lookup"><span data-stu-id="9ad29-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="9ad29-106">通过使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> ，您可以指定重复一 <xref:System.Windows.Media.Animation.Timeline> 次 (迭代计数) 或指定的时间段。</span><span class="sxs-lookup"><span data-stu-id="9ad29-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="9ad29-107">无论是哪种情况，动画都会经历任意数量的开始到端运行，以便填充请求的计数或持续时间。</span><span class="sxs-lookup"><span data-stu-id="9ad29-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="9ad29-108">默认情况下，时间线的重复次数为1.0，这意味着它们播放一次并且不重复。</span><span class="sxs-lookup"><span data-stu-id="9ad29-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="9ad29-109">但是，如果将的 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性设置 <xref:System.Windows.Media.Animation.Timeline> 为 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> ，则时间线会无限期地重复。</span><span class="sxs-lookup"><span data-stu-id="9ad29-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="9ad29-110">下面的示例演示如何使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性来控制动画的重复行为。</span><span class="sxs-lookup"><span data-stu-id="9ad29-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="9ad29-111">该示例 <xref:System.Windows.FrameworkElement.Width%2A> 使用不同类型的重复行为，对每个矩形的五个矩形的属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="9ad29-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="9ad29-112">有关完整示例，请参阅 [动画计时行为示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)。</span><span class="sxs-lookup"><span data-stu-id="9ad29-112">For the complete sample, see [Animation Timing Behavior Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ad29-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ad29-113">See also</span></span>

- [<span data-ttu-id="9ad29-114">在重复循环过程中累积动画值</span><span class="sxs-lookup"><span data-stu-id="9ad29-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="9ad29-115">指定时间线是否自动反转</span><span class="sxs-lookup"><span data-stu-id="9ad29-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="9ad29-116">动画和计时帮助主题</span><span class="sxs-lookup"><span data-stu-id="9ad29-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="9ad29-117">动画概述</span><span class="sxs-lookup"><span data-stu-id="9ad29-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="9ad29-118">动画计时行为示例</span><span class="sxs-lookup"><span data-stu-id="9ad29-118">Animation Timing Behavior Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
