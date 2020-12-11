---
title: 如何：使用关键帧对点进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973217"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="36a07-102">如何：使用关键帧对点进行动画处理</span><span class="sxs-lookup"><span data-stu-id="36a07-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="36a07-103">此示例演示如何使用 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 类对进行动画处理 <xref:System.Windows.Point> 。</span><span class="sxs-lookup"><span data-stu-id="36a07-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36a07-104">示例</span><span class="sxs-lookup"><span data-stu-id="36a07-104">Example</span></span>  
 <span data-ttu-id="36a07-105">以下示例沿三角形路径移动椭圆形。</span><span class="sxs-lookup"><span data-stu-id="36a07-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="36a07-106">该示例使用 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 类对的属性进行动画处理 <xref:System.Windows.Media.EllipseGeometry.Center%2A> <xref:System.Windows.Media.EllipseGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="36a07-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="36a07-107">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="36a07-107">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="36a07-108">在前半秒中，使用类的实例，将 <xref:System.Windows.Media.Animation.LinearPointKeyFrame> 椭圆沿着路径以稳定的速率从其起始位置移动。</span><span class="sxs-lookup"><span data-stu-id="36a07-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="36a07-109">线性关键帧，如在 <xref:System.Windows.Media.Animation.LinearPointKeyFrame> 值之间创建平滑的线性内插。</span><span class="sxs-lookup"><span data-stu-id="36a07-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="36a07-110">在接下来的半秒结束时，使用类的实例 <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> 突然将椭圆沿路径移动到下一个位置。</span><span class="sxs-lookup"><span data-stu-id="36a07-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="36a07-111">离散关键帧（如 <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create 突然跨值）。</span><span class="sxs-lookup"><span data-stu-id="36a07-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3. <span data-ttu-id="36a07-112">在最后两秒内，使用类的实例 <xref:System.Windows.Media.Animation.SplinePointKeyFrame> 将椭圆移回其起始位置。</span><span class="sxs-lookup"><span data-stu-id="36a07-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="36a07-113">样条关键帧 <xref:System.Windows.Media.Animation.SplinePointKeyFrame> ，如根据属性的值在值之间进行变量转换 <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> 。</span><span class="sxs-lookup"><span data-stu-id="36a07-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="36a07-114">在此示例中，动画开始时较为缓慢，然后以指数方式加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="36a07-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="36a07-115">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="36a07-115">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
 <span data-ttu-id="36a07-116">为了与其他动画示例保持一致，此示例的代码版本使用 <xref:System.Windows.Media.Animation.Storyboard> 对象来应用 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 。</span><span class="sxs-lookup"><span data-stu-id="36a07-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="36a07-117">但是，在代码中应用单个动画时，使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法比使用方法更为简单 <xref:System.Windows.Media.Animation.Storyboard> 。</span><span class="sxs-lookup"><span data-stu-id="36a07-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="36a07-118">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="36a07-118">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a07-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36a07-119">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [<span data-ttu-id="36a07-120">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="36a07-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="36a07-121">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="36a07-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
