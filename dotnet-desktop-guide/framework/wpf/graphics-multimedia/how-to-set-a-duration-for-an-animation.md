---
title: 如何：设置动画的持续时间
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: bdae1689ffeb8c54d756b9debbd26d57a052892d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973843"
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="05b56-102">如何：设置动画的持续时间</span><span class="sxs-lookup"><span data-stu-id="05b56-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="05b56-103"><xref:System.Windows.Media.Animation.Timeline>表示时间段，并且该时间段的长度由时间线的确定 <xref:System.Windows.Duration> 。</span><span class="sxs-lookup"><span data-stu-id="05b56-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="05b56-104">当 <xref:System.Windows.Media.Animation.Timeline> 到达其持续时间的终点时，它将停止播放。</span><span class="sxs-lookup"><span data-stu-id="05b56-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="05b56-105">如果 <xref:System.Windows.Media.Animation.Timeline> 有子时间线，它们也会停止播放。</span><span class="sxs-lookup"><span data-stu-id="05b56-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="05b56-106">对于动画， <xref:System.Windows.Duration> 指定动画从其起始值过渡到其结束值需要多长时间。</span><span class="sxs-lookup"><span data-stu-id="05b56-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="05b56-107">您可以 <xref:System.Windows.Duration> 使用特定的、有限的时间或特殊值或来 <xref:System.Windows.Duration.Automatic%2A> 指定 <xref:System.Windows.Duration.Forever%2A> 。</span><span class="sxs-lookup"><span data-stu-id="05b56-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="05b56-108">动画的持续时间必须始终为时间值，因为动画必须始终具有定义的有限长度，否则，动画将不知道如何在其目标值之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="05b56-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="05b56-109">)  (对象（例如和）的容器时间线 <xref:System.Windows.Media.Animation.TimelineGroup> <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.ParallelTimeline> 的默认持续时间为 <xref:System.Windows.Duration.Automatic%2A> ，这意味着在其最后一个子级停止播放时，它们会自动结束。</span><span class="sxs-lookup"><span data-stu-id="05b56-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="05b56-110">在下面的示例中，的宽度、高度和填充颜色 <xref:System.Windows.Shapes.Rectangle> 都进行了动画处理。</span><span class="sxs-lookup"><span data-stu-id="05b56-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="05b56-111">持续时间在动画和容器时间线上设置，产生动画效果，包括控制动画的感知速度，并将子时间线的持续时间替换为容器时间线的持续时间。</span><span class="sxs-lookup"><span data-stu-id="05b56-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05b56-112">示例</span><span class="sxs-lookup"><span data-stu-id="05b56-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="05b56-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05b56-113">See also</span></span>

- <xref:System.Windows.Duration>
- [<span data-ttu-id="05b56-114">动画概述</span><span class="sxs-lookup"><span data-stu-id="05b56-114">Animation Overview</span></span>](animation-overview.md)
