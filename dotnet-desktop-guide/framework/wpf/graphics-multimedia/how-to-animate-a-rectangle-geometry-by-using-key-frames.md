---
title: 如何：使用关键帧对矩形几何形状进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970623"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="c5307-102">如何：使用关键帧对矩形几何形状进行动画处理</span><span class="sxs-lookup"><span data-stu-id="c5307-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="c5307-103">此示例演示如何 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 使用关键帧对的属性进行动画处理 <xref:System.Windows.Media.RectangleGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="c5307-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5307-104">示例</span><span class="sxs-lookup"><span data-stu-id="c5307-104">Example</span></span>  
 <span data-ttu-id="c5307-105">下面的示例使用 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> 类对的属性进行动画处理 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> <xref:System.Windows.Media.RectangleGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="c5307-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="c5307-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="c5307-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="c5307-107">在前两秒内，使用类的实例 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 对矩形的位置、宽度和高度的渐变变化进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="c5307-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="c5307-108">线性关键帧，如在 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 值之间创建平滑线性过渡。</span><span class="sxs-lookup"><span data-stu-id="c5307-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="c5307-109">在接下来的半秒结束时，使用类的实例 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 突然降低矩形的高度。</span><span class="sxs-lookup"><span data-stu-id="c5307-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="c5307-110">离散关键帧（如 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 创建值之间的突然更改，即，高度的减少速度快且不微妙）。</span><span class="sxs-lookup"><span data-stu-id="c5307-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="c5307-111">在最后两秒内，使用类的实例将 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 矩形更改回其原始大小和位置。</span><span class="sxs-lookup"><span data-stu-id="c5307-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="c5307-112">样条关键帧 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> ，如根据属性的值在值之间进行变量转换 <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c5307-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="c5307-113">在此示例中，变化开始时缓慢，然后以指数级加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="c5307-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="c5307-114">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="c5307-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5307-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5307-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="c5307-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="c5307-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="c5307-117">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="c5307-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
