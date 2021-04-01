---
title: 如何：在重复循环过程中累积动画值
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: bccdc9b7bf2d5a0ea476e39e8d54107854db7ae3
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973581"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="3dfe4-102">如何：在重复循环过程中累积动画值</span><span class="sxs-lookup"><span data-stu-id="3dfe4-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="3dfe4-103">此示例演示如何使用 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 属性在重复循环之间累积动画值。</span><span class="sxs-lookup"><span data-stu-id="3dfe4-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dfe4-104">示例</span><span class="sxs-lookup"><span data-stu-id="3dfe4-104">Example</span></span>  
 <span data-ttu-id="3dfe4-105">使用 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 属性可在重复循环之间累计动画的基值。</span><span class="sxs-lookup"><span data-stu-id="3dfe4-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="3dfe4-106">例如，如果你将动画设置为重复 (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 为 "9x" 的9倍 ) 并且将属性设置为在10到15之间进行动画处理 (从 = 10 到 = 15) ），则在第一个周期（从15到20）期间，此属性将在第一个周期（从15到20，在第三个周期中为20到25）进行动画</span><span class="sxs-lookup"><span data-stu-id="3dfe4-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="3dfe4-107">因此，每个动画周期都使用上一动画周期中的结束动画值作为其基值。</span><span class="sxs-lookup"><span data-stu-id="3dfe4-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="3dfe4-108">可以将 `IsCumulative` 属性与大多数基本动画和大多数关键帧动画一起使用。</span><span class="sxs-lookup"><span data-stu-id="3dfe4-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="3dfe4-109">有关详细信息，请参阅 [动画概述](animation-overview.md) 和 [关键帧动画概述](key-frame-animations-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3dfe4-109">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="3dfe4-110">下面的示例通过对四个矩形的宽度进行动画处理来显示此行为。</span><span class="sxs-lookup"><span data-stu-id="3dfe4-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="3dfe4-111">示例：</span><span class="sxs-lookup"><span data-stu-id="3dfe4-111">The example:</span></span>  
  
- <span data-ttu-id="3dfe4-112">对第一个矩形进行动画处理 <xref:System.Windows.Media.Animation.DoubleAnimation> ，并将 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="3dfe4-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="3dfe4-113">对第二个矩形进行动画处理 <xref:System.Windows.Media.Animation.DoubleAnimation> ，并将 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 属性设置为的默认值 `false` 。</span><span class="sxs-lookup"><span data-stu-id="3dfe4-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
- <span data-ttu-id="3dfe4-114">对第三个矩形进行动画处理 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> ，并将 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="3dfe4-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="3dfe4-115">对最后一个矩形进行动画处理 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> ，并将 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> 属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="3dfe4-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3dfe4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dfe4-116">See also</span></span>

- [<span data-ttu-id="3dfe4-117">向动画起始值添加动画输出值</span><span class="sxs-lookup"><span data-stu-id="3dfe4-117">Add an Animation Output Value to an Animation Starting Value</span></span>](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [<span data-ttu-id="3dfe4-118">重复动画</span><span class="sxs-lookup"><span data-stu-id="3dfe4-118">Repeat an Animation</span></span>](how-to-repeat-an-animation.md)
- [<span data-ttu-id="3dfe4-119">动画概述</span><span class="sxs-lookup"><span data-stu-id="3dfe4-119">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="3dfe4-120">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="3dfe4-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="3dfe4-121">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="3dfe4-121">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
