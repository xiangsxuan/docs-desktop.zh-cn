---
title: 如何：对渐变停止点的位置或颜色进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970866"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="ed961-102">如何：对渐变停止点的位置或颜色进行动画处理</span><span class="sxs-lookup"><span data-stu-id="ed961-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="ed961-103">此示例演示如何对对象的和进行动画处理 <xref:System.Windows.Media.GradientStop.Color%2A> <xref:System.Windows.Media.GradientStop.Offset%2A> <xref:System.Windows.Media.GradientStop> 。</span><span class="sxs-lookup"><span data-stu-id="ed961-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed961-104">示例</span><span class="sxs-lookup"><span data-stu-id="ed961-104">Example</span></span>  
 <span data-ttu-id="ed961-105">下面的示例在中对三个梯度停止点进行动画处理 <xref:System.Windows.Media.LinearGradientBrush> 。</span><span class="sxs-lookup"><span data-stu-id="ed961-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="ed961-106">该示例使用三个动画，其中每个动画对不同梯度停止点进行动画处理：</span><span class="sxs-lookup"><span data-stu-id="ed961-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
- <span data-ttu-id="ed961-107">第一个动画（a <xref:System.Windows.Media.Animation.DoubleAnimation> ）动画处理第一个梯度停止点（ <xref:System.Windows.Media.GradientStop.Offset%2A> 从0.0 到1.0，然后再回0.0）。</span><span class="sxs-lookup"><span data-stu-id="ed961-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="ed961-108">因此，渐变中的第一种颜色会从矩形的左侧向右移动，然后返回到左侧。</span><span class="sxs-lookup"><span data-stu-id="ed961-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
- <span data-ttu-id="ed961-109">第二个动画（a）动画处理 <xref:System.Windows.Media.Animation.ColorAnimation> 第二个梯度停止点， <xref:System.Windows.Media.GradientStop.Color%2A> <xref:System.Windows.Media.Colors.Purple%2A> <xref:System.Windows.Media.Colors.Yellow%2A> 然后返回到 <xref:System.Windows.Media.Colors.Purple%2A> 。</span><span class="sxs-lookup"><span data-stu-id="ed961-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="ed961-110">因此，渐变的中间颜色会从紫色变为黄色并返回到紫色。</span><span class="sxs-lookup"><span data-stu-id="ed961-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
- <span data-ttu-id="ed961-111">第三个动画，另一个动画会 <xref:System.Windows.Media.Animation.ColorAnimation> 将第三个梯度停止点的不透明度进行动画处理， <xref:System.Windows.Media.GradientStop.Color%2A> 然后返回。</span><span class="sxs-lookup"><span data-stu-id="ed961-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="ed961-112">因此，渐变中的第三种颜色淡出，然后再次变为不透明。</span><span class="sxs-lookup"><span data-stu-id="ed961-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="ed961-113">虽然此示例使用，但在中对 <xref:System.Windows.Media.LinearGradientBrush> 对象进行动画处理是相同的 <xref:System.Windows.Media.GradientStop> <xref:System.Windows.Media.RadialGradientBrush> 。</span><span class="sxs-lookup"><span data-stu-id="ed961-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="ed961-114">有关其他示例，请参阅 [画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。</span><span class="sxs-lookup"><span data-stu-id="ed961-114">For additional examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed961-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed961-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="ed961-116">动画概述</span><span class="sxs-lookup"><span data-stu-id="ed961-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="ed961-117">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="ed961-117">Storyboards Overview</span></span>](storyboards-overview.md)
