---
title: 如何：使用关键帧对边框的粗细进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970862"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="c9a8c-102">如何：使用关键帧对边框的粗细进行动画处理</span><span class="sxs-lookup"><span data-stu-id="c9a8c-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="c9a8c-103">此示例演示如何对的属性进行动画处理 <xref:System.Windows.Controls.Control.BorderThickness%2A> <xref:System.Windows.Controls.Border> 。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9a8c-104">示例</span><span class="sxs-lookup"><span data-stu-id="c9a8c-104">Example</span></span>  
 <span data-ttu-id="c9a8c-105">下面的示例使用 <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> 类对的属性进行动画处理 <xref:System.Windows.Controls.Control.BorderThickness%2A> <xref:System.Windows.Controls.Border> 。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="c9a8c-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="c9a8c-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="c9a8c-107">在前半秒中，使用类的实例 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> 逐渐增加边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="c9a8c-108">该示例使用在 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> 值之间创建平滑线性增长。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2. <span data-ttu-id="c9a8c-109">在接下来的半秒结束时，使用类的实例 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 突然增加边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="c9a8c-110">分离型关键帧（如从 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 创建值之间的突然跳转），也就是说，动画的移动是不平稳的。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3. <span data-ttu-id="c9a8c-111">在最后两秒内，使用类的实例 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 来减小边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="c9a8c-112">样条关键帧（如从派生的帧） <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 根据属性的值在值之间进行转换 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="c9a8c-113">在此关键帧中，动画开始时缓慢，然后以指数方式加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="c9a8c-114">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="c9a8c-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a8c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9a8c-115">See also</span></span>

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="c9a8c-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="c9a8c-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="c9a8c-117">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="c9a8c-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="c9a8c-118">对 BorderThickness 值进行动画处理</span><span class="sxs-lookup"><span data-stu-id="c9a8c-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
