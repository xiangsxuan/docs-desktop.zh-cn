---
title: 如何：对 SolidColorBrush 的颜色或不透明度进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970946"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="fbc6a-102">如何：对 SolidColorBrush 的颜色或不透明度进行动画处理</span><span class="sxs-lookup"><span data-stu-id="fbc6a-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="fbc6a-103">此示例演示如何对的和进行动画处理 <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.SolidColorBrush> 。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbc6a-104">示例</span><span class="sxs-lookup"><span data-stu-id="fbc6a-104">Example</span></span>  
 <span data-ttu-id="fbc6a-105">下面的示例使用三个动画对的和进行动画处理 <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.SolidColorBrush> 。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
- <span data-ttu-id="fbc6a-106">第一个动画是 <xref:System.Windows.Media.Animation.ColorAnimation> ，将画笔的颜色更改为 <xref:System.Windows.Media.Colors.Gray%2A> 鼠标进入矩形时的颜色。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
- <span data-ttu-id="fbc6a-107">接下来的动画会将 <xref:System.Windows.Media.Animation.ColorAnimation> 画笔的颜色更改为 <xref:System.Windows.Media.Colors.Orange%2A> 鼠标离开矩形时的颜色。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
- <span data-ttu-id="fbc6a-108"><xref:System.Windows.Media.Animation.DoubleAnimation>当按下鼠标左键时，最终动画 a 会将画笔的不透明度更改为0.0。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="fbc6a-109">有关演示如何对不同类型的画笔进行动画处理的更完整示例，请参阅 [画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="fbc6a-110">有关动画的详细信息，请参阅 [动画概述](animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="fbc6a-111">为了与其他动画示例保持一致，此示例的代码版本使用 <xref:System.Windows.Media.Animation.Storyboard> 对象应用其动画。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="fbc6a-112">但是，在代码中应用单个动画时，使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法比使用方法更为简单 <xref:System.Windows.Media.Animation.Storyboard> 。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="fbc6a-113">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc6a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbc6a-114">See also</span></span>

- [<span data-ttu-id="fbc6a-115">动画概述</span><span class="sxs-lookup"><span data-stu-id="fbc6a-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="fbc6a-116">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="fbc6a-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="fbc6a-117">画笔示例</span><span class="sxs-lookup"><span data-stu-id="fbc6a-117">Brushes Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
