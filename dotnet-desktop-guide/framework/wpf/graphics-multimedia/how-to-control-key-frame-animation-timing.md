---
title: 如何：控制关键帧动画的计时
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973535"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="d2116-102">如何：控制关键帧动画的计时</span><span class="sxs-lookup"><span data-stu-id="d2116-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="d2116-103">此示例演示如何控制关键帧动画内关键帧的时间。</span><span class="sxs-lookup"><span data-stu-id="d2116-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="d2116-104">与其他动画类似，关键帧动画具有 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="d2116-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="d2116-105">除了指定动画持续时间以外，还需要指定将该持续时间中的哪个部分分配给其每个关键帧。</span><span class="sxs-lookup"><span data-stu-id="d2116-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="d2116-106">若要分配时间，请 <xref:System.Windows.Media.Animation.KeyTime> 为动画中的每个关键帧指定。</span><span class="sxs-lookup"><span data-stu-id="d2116-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="d2116-107"><xref:System.Windows.Media.Animation.KeyTime>对于每个关键帧，指定关键帧结束的时间 (未指定关键帧) 的时间长度。</span><span class="sxs-lookup"><span data-stu-id="d2116-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="d2116-108">您可以指定 <xref:System.Windows.Media.Animation.KeyTime> 作为 <xref:System.TimeSpan> 值、百分比，或指定为 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 或 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 特殊值。</span><span class="sxs-lookup"><span data-stu-id="d2116-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="d2116-109">示例</span><span class="sxs-lookup"><span data-stu-id="d2116-109">Example</span></span>

<span data-ttu-id="d2116-110">下面的示例使用在 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 屏幕上对矩形进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="d2116-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="d2116-111">关键帧的关键时间设置为 <xref:System.TimeSpan> 值。</span><span class="sxs-lookup"><span data-stu-id="d2116-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="d2116-112">下图显示了何时到达每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="d2116-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="d2116-113">![在 3、4 和 10 秒时达到的关键值](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="d2116-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="d2116-114">下一个示例显示了相同的动画，只不过关键帧的关键时间是使用百分比值设置的。</span><span class="sxs-lookup"><span data-stu-id="d2116-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="d2116-115">下图显示了何时到达每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="d2116-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="d2116-116">![在 3、4 和 10 秒时达到的关键值](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="d2116-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="d2116-117">下一个示例使用 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time 值。</span><span class="sxs-lookup"><span data-stu-id="d2116-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="d2116-118">下图显示了何时到达每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="d2116-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="d2116-119">![在 3.3、6.6 和 9.9 秒时达到的关键值](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="d2116-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="d2116-120">最后一个示例使用 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 关键时间值。</span><span class="sxs-lookup"><span data-stu-id="d2116-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="d2116-121">下图显示了何时到达每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="d2116-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="d2116-122">![在 0、5 和 10 秒时达到的关键值](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="d2116-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="d2116-123">为简单起见，此示例的代码版本使用本地动画，而不是情节提要，因为只有单个动画应用于单个属性，但可以修改这些示例以改用情节提要。</span><span class="sxs-lookup"><span data-stu-id="d2116-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="d2116-124">有关演示如何在代码中声明情节提要的示例，请参阅 [使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="d2116-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="d2116-125">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="d2116-125">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span> <span data-ttu-id="d2116-126">有关关键帧动画的详细信息，请参阅 [关键帧动画概述](key-frame-animations-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d2116-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2116-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2116-127">See also</span></span>

- [<span data-ttu-id="d2116-128">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="d2116-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="d2116-129">动画概述</span><span class="sxs-lookup"><span data-stu-id="d2116-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="d2116-130">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="d2116-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
