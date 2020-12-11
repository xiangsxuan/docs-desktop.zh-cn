---
title: 如何：为已经到达有效期末尾的时间线指定 FillBehavior
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972748"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="f32bc-102">如何：为已经到达有效期末尾的时间线指定 FillBehavior</span><span class="sxs-lookup"><span data-stu-id="f32bc-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="f32bc-103">此示例演示如何 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 为动画属性的非活动指定 <xref:System.Windows.Media.Animation.Timeline> 。</span><span class="sxs-lookup"><span data-stu-id="f32bc-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f32bc-104">示例</span><span class="sxs-lookup"><span data-stu-id="f32bc-104">Example</span></span>  
 <span data-ttu-id="f32bc-105">的 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性 <xref:System.Windows.Media.Animation.Timeline> 确定动画属性的值在未进行动画处理时所发生的情况，即，当 <xref:System.Windows.Media.Animation.Timeline> 处于非活动状态但其父级 <xref:System.Windows.Media.Animation.Timeline> 在其活动或保持期内时的行为。</span><span class="sxs-lookup"><span data-stu-id="f32bc-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="f32bc-106">例如，动画结束后动画属性是否保持其结束值，或者是否还原为开始动画前的值？</span><span class="sxs-lookup"><span data-stu-id="f32bc-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="f32bc-107">下面的示例使用 <xref:System.Windows.Media.Animation.DoubleAnimation> 对两个矩形的进行动画处理 <xref:System.Windows.FrameworkElement.Width%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f32bc-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="f32bc-108">每个矩形都使用不同的 <xref:System.Windows.Media.Animation.Timeline> 对象。</span><span class="sxs-lookup"><span data-stu-id="f32bc-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="f32bc-109">一个 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 设置为 <xref:System.Windows.Media.Animation.FillBehavior.Stop> ，它会使矩形的宽度在结束时恢复回其非动画值 <xref:System.Windows.Media.Animation.Timeline> 。</span><span class="sxs-lookup"><span data-stu-id="f32bc-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="f32bc-110">另 <xref:System.Windows.Media.Animation.Timeline> 一个具有 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 的 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> ，这会导致在结束时宽度保持其结束值 <xref:System.Windows.Media.Animation.Timeline> 。</span><span class="sxs-lookup"><span data-stu-id="f32bc-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="f32bc-111">有关完整示例，请参阅 [动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。</span><span class="sxs-lookup"><span data-stu-id="f32bc-111">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f32bc-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f32bc-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="f32bc-113">动画概述</span><span class="sxs-lookup"><span data-stu-id="f32bc-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f32bc-114">动画和计时帮助主题</span><span class="sxs-lookup"><span data-stu-id="f32bc-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
