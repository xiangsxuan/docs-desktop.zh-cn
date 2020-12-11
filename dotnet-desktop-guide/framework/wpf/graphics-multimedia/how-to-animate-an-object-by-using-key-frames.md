---
title: 如何：使用关键帧针对对象进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973178"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="baa45-102">如何：使用关键帧针对对象进行动画处理</span><span class="sxs-lookup"><span data-stu-id="baa45-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="baa45-103">此示例演示如何使用关键帧对对象（在此示例中为 <xref:System.Windows.Controls.Page.Background%2A> 控件的属性）进行动画处理 <xref:System.Windows.Controls.Page> 。</span><span class="sxs-lookup"><span data-stu-id="baa45-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="baa45-104">示例</span><span class="sxs-lookup"><span data-stu-id="baa45-104">Example</span></span>  
 <span data-ttu-id="baa45-105">下面的示例使用 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 类对控件的属性的颜色更改进行动画处理 <xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page> 。</span><span class="sxs-lookup"><span data-stu-id="baa45-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="baa45-106">该示例动画会按固定的时间间隔更改为不同的背景画笔。</span><span class="sxs-lookup"><span data-stu-id="baa45-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="baa45-107">此动画使用 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 类创建三个不同的关键帧。</span><span class="sxs-lookup"><span data-stu-id="baa45-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="baa45-108">动画按以下方式使用关键帧：</span><span class="sxs-lookup"><span data-stu-id="baa45-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="baa45-109">在第一秒结束时，对类的实例进行动画处理 <xref:System.Windows.Media.LinearGradientBrush> 。</span><span class="sxs-lookup"><span data-stu-id="baa45-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="baa45-110">此部分示例对背景色应用线性渐变，使颜色从黄色转换为橙色。</span><span class="sxs-lookup"><span data-stu-id="baa45-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="baa45-111">在下一秒结束时，对类的实例进行动画处理 <xref:System.Windows.Media.RadialGradientBrush> 。</span><span class="sxs-lookup"><span data-stu-id="baa45-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="baa45-112">此部分示例对背景色应用径向渐变，使颜色从白色过渡到蓝色。</span><span class="sxs-lookup"><span data-stu-id="baa45-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="baa45-113">在第三秒结束时，对类的实例进行动画处理 <xref:System.Windows.Media.DrawingBrush> 。</span><span class="sxs-lookup"><span data-stu-id="baa45-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="baa45-114">此部分示例将棋盘模式应用于背景。</span><span class="sxs-lookup"><span data-stu-id="baa45-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="baa45-115">动画将再次开始，并无限期地重复。</span><span class="sxs-lookup"><span data-stu-id="baa45-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="baa45-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 是唯一可与类一起使用的关键帧类型 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 。</span><span class="sxs-lookup"><span data-stu-id="baa45-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="baa45-117">关键帧（如 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 创建值的突然变化）即，此示例中的颜色更改突然发生。</span><span class="sxs-lookup"><span data-stu-id="baa45-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="baa45-118">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="baa45-118">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa45-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="baa45-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="baa45-120">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="baa45-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="baa45-121">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="baa45-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
