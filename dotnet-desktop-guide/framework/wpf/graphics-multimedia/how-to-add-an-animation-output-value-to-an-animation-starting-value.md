---
title: 如何：向动画起始值添加动画输出值
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 945675d03a280e2394fdb0eab27c0978dc7cc320
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970869"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="fe8a6-102">如何：向动画起始值添加动画输出值</span><span class="sxs-lookup"><span data-stu-id="fe8a6-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="fe8a6-103">此示例演示如何向动画起始值添加动画输出值。</span><span class="sxs-lookup"><span data-stu-id="fe8a6-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe8a6-104">示例</span><span class="sxs-lookup"><span data-stu-id="fe8a6-104">Example</span></span>  
 <span data-ttu-id="fe8a6-105"><xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A>属性指定是否希望将动画的输出值添加到动画属性的起始值 (基值) 。</span><span class="sxs-lookup"><span data-stu-id="fe8a6-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="fe8a6-106">可以将 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> 属性与大多数基本动画和大多数关键帧动画一起使用。</span><span class="sxs-lookup"><span data-stu-id="fe8a6-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="fe8a6-107">有关详细信息，请参阅 [动画概述](animation-overview.md) 和 [关键帧动画概述](key-frame-animations-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fe8a6-107">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="fe8a6-108">下面的示例演示对使用 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> 属性 <xref:System.Windows.Media.Animation.DoubleAnimation> 并将 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> 属性与结合使用的效果 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 。</span><span class="sxs-lookup"><span data-stu-id="fe8a6-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="fe8a6-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe8a6-109">See also</span></span>

- [<span data-ttu-id="fe8a6-110">在重复循环过程中累积动画值</span><span class="sxs-lookup"><span data-stu-id="fe8a6-110">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="fe8a6-111">动画概述</span><span class="sxs-lookup"><span data-stu-id="fe8a6-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="fe8a6-112">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="fe8a6-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="fe8a6-113">动画和计时帮助主题</span><span class="sxs-lookup"><span data-stu-id="fe8a6-113">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
