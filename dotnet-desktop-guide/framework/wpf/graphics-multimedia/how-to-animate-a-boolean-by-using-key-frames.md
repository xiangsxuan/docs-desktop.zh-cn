---
title: 如何：使用关键帧对布尔属性值进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973220"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="cf593-102">如何：使用关键帧对布尔属性值进行动画处理</span><span class="sxs-lookup"><span data-stu-id="cf593-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="cf593-103">此示例演示如何使用关键帧对控件的布尔属性值进行动画处理 <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="cf593-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf593-104">示例</span><span class="sxs-lookup"><span data-stu-id="cf593-104">Example</span></span>  
 <span data-ttu-id="cf593-105">下面的示例使用 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> 类对控件的属性进行动画处理 <xref:System.Windows.UIElement.IsEnabled%2A> <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="cf593-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="cf593-106">此示例中的所有关键帧均使用类的实例 <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> 。</span><span class="sxs-lookup"><span data-stu-id="cf593-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="cf593-107">离散关键帧（如 <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create 突然跳转到值之间），也就是说，动画的移动是不平稳的。</span><span class="sxs-lookup"><span data-stu-id="cf593-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="cf593-108">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="cf593-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf593-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf593-109">See also</span></span>

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="cf593-110">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="cf593-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="cf593-111">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="cf593-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
