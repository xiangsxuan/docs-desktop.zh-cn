---
title: 如何：使用关键帧对大小变化进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970949"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="7eb4f-102">如何：使用关键帧对大小变化进行动画处理</span><span class="sxs-lookup"><span data-stu-id="7eb4f-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="7eb4f-103">此示例演示如何使用关键帧对大小变化进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7eb4f-104">示例</span><span class="sxs-lookup"><span data-stu-id="7eb4f-104">Example</span></span>  
 <span data-ttu-id="7eb4f-105">下面的示例使用 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> 类对的属性进行动画处理 <xref:System.Windows.Media.ArcSegment.Size%2A> <xref:System.Windows.Media.ArcSegment> 。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="7eb4f-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="7eb4f-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="7eb4f-107">在动画的前半秒中，使用类的实例 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 逐渐增加弧的大小。线性关键帧，如在 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 值之间创建平滑线性过渡。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="7eb4f-108">在接下来的半秒结束时，使用类的实例 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> 突然增加弧的大小。离散关键帧（如 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create 突然跳转到值之间），也就是说，大小变化突然发生，并且不是微妙的。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3. <span data-ttu-id="7eb4f-109">在最后两秒内，使用类的实例 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> 来增加弧的大小。样条关键帧 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> ，如根据属性的值在值之间进行变量转换 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> 。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="7eb4f-110">在本例中，弧的大小开始时缓慢增加，然后以指数方式增加，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="7eb4f-111">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-111">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb4f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="7eb4f-112">See also</span></span>

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [<span data-ttu-id="7eb4f-113">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="7eb4f-113">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="7eb4f-114">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="7eb4f-114">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
