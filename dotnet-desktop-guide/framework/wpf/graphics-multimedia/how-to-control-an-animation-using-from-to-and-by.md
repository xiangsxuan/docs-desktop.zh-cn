---
title: 如何：使用 From、To 和 By 控制动画
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: b06df97dc57c58a01f30be2d70bfeebf104521ad
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973124"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a><span data-ttu-id="f9893-102">如何：使用 From、To 和 By 控制动画</span><span class="sxs-lookup"><span data-stu-id="f9893-102">How to: Control an Animation using From, To, and By</span></span>
<span data-ttu-id="f9893-103">"From/To/By" 或 "基本动画" 创建两个目标值之间的转换 (参阅 [动画概述](animation-overview.md) ，了解不同类型的动画) 的简介。</span><span class="sxs-lookup"><span data-stu-id="f9893-103">A "From/To/By" or "basic animation" creates a transition between two target values (see [Animation Overview](animation-overview.md) for an introduction to different types of animations).</span></span> <span data-ttu-id="f9893-104">若要设置基本动画的目标值，请使用其 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 、 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="f9893-104">To set the target values of a basic animation, use its <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties.</span></span>  <span data-ttu-id="f9893-105">下表总结了如何 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 结合使用、和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性，以确定动画的目标值。</span><span class="sxs-lookup"><span data-stu-id="f9893-105">The following table summarizes how the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties may be used together or separately to determine an animation's target values.</span></span>  
  
|<span data-ttu-id="f9893-106">指定的属性</span><span class="sxs-lookup"><span data-stu-id="f9893-106">Properties specified</span></span>|<span data-ttu-id="f9893-107">产生的行为</span><span class="sxs-lookup"><span data-stu-id="f9893-107">Resulting behavior</span></span>|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|<span data-ttu-id="f9893-108">动画从属性指定的值前进到要 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 进行动画处理的属性的基值或前一个动画的输出值，具体取决于以前的动画的配置方式。</span><span class="sxs-lookup"><span data-stu-id="f9893-108">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the base value of the property being animated or to a previous animation's output value, depending on how the previous animation is configured.</span></span>|  
|<span data-ttu-id="f9893-109"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A></span><span class="sxs-lookup"><span data-stu-id="f9893-109"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A></span></span>|<span data-ttu-id="f9893-110">动画从属性指定的值前进 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 到属性指定的值 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f9893-110">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property.</span></span>|  
|<span data-ttu-id="f9893-111"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A></span><span class="sxs-lookup"><span data-stu-id="f9893-111"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A></span></span>|<span data-ttu-id="f9893-112">动画从属性指定的值前进 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 到和属性的和所指定的值 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f9893-112">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the value specified by the sum of the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties.</span></span>|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|<span data-ttu-id="f9893-113">动画从经过动画处理的属性的基值或前一个动画的输出值前进到属性指定的值 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f9893-113">The animation progresses from the animated property's base value or a previous animation's output value to the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property.</span></span>|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|<span data-ttu-id="f9893-114">动画从要进行动画处理的属性的基值或前一个动画的输出值前进到该值与属性指定的值的和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f9893-114">The animation progresses from the base value of the property being animated or a previous animation's output value to the sum of that value and the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> property.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f9893-115">不要 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 在同一动画上设置属性和属性。</span><span class="sxs-lookup"><span data-stu-id="f9893-115">Do not set both the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property and the <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> property on the same animation.</span></span>  
  
 <span data-ttu-id="f9893-116">若要在两个以上的目标值之间使用内插方法或进行动画处理，请使用关键帧动画。</span><span class="sxs-lookup"><span data-stu-id="f9893-116">To use other interpolation methods or animate between more than two target values, use a key frame animation.</span></span> <span data-ttu-id="f9893-117">有关详细信息，请参阅 [关键帧动画概述](key-frame-animations-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="f9893-117">See [Key-Frame Animations Overview](key-frame-animations-overview.md) for more information.</span></span>  
  
 <span data-ttu-id="f9893-118">有关将多个动画应用于单个属性的信息，请参阅 [关键帧动画概述](key-frame-animations-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f9893-118">For information about applying multiple animations to a single property, see [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="f9893-119">下面的示例显示了 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 在动画上设置、和属性的不同效果。</span><span class="sxs-lookup"><span data-stu-id="f9893-119">The example below shows the different effects of setting <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> properties on animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9893-120">示例</span><span class="sxs-lookup"><span data-stu-id="f9893-120">Example</span></span>  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f9893-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9893-121">See also</span></span>

- [<span data-ttu-id="f9893-122">动画概述</span><span class="sxs-lookup"><span data-stu-id="f9893-122">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f9893-123">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="f9893-123">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="f9893-124">From、To 和 By 动画目标值示例</span><span class="sxs-lookup"><span data-stu-id="f9893-124">From, To, and By Animation Target Values Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)