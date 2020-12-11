---
title: 如何：在使用演示图板对属性进行动画处理后设置该属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: 593d3fcefe3bb81518d0886afde82f9a172874ba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972774"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="4339f-102">如何：在使用演示图板对属性进行动画处理后设置该属性</span><span class="sxs-lookup"><span data-stu-id="4339f-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="4339f-103">在某些情况下，可能会出现这样的情况：您在对属性进行动画处理后，不能更改该属性的值。</span><span class="sxs-lookup"><span data-stu-id="4339f-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4339f-104">示例</span><span class="sxs-lookup"><span data-stu-id="4339f-104">Example</span></span>  
 <span data-ttu-id="4339f-105">在下面的示例中， <xref:System.Windows.Media.Animation.Storyboard> 用于对的颜色进行动画处理 <xref:System.Windows.Media.SolidColorBrush> 。</span><span class="sxs-lookup"><span data-stu-id="4339f-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="4339f-106">当单击此按钮时，将触发情节提要。</span><span class="sxs-lookup"><span data-stu-id="4339f-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="4339f-107"><xref:System.Windows.Media.Animation.Timeline.Completed>处理事件，以便在完成时通知程序 <xref:System.Windows.Media.Animation.ColorAnimation> 。</span><span class="sxs-lookup"><span data-stu-id="4339f-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="4339f-108">示例</span><span class="sxs-lookup"><span data-stu-id="4339f-108">Example</span></span>  
 <span data-ttu-id="4339f-109">完成后 <xref:System.Windows.Media.Animation.ColorAnimation> ，程序将尝试将画笔的颜色更改为蓝色。</span><span class="sxs-lookup"><span data-stu-id="4339f-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="4339f-110">前面的代码不会执行任何操作：画笔保持为黄色，这是由动画处理画笔的所提供的值 <xref:System.Windows.Media.Animation.ColorAnimation> 。</span><span class="sxs-lookup"><span data-stu-id="4339f-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="4339f-111">基础属性值 (基值) 实际变为蓝色。</span><span class="sxs-lookup"><span data-stu-id="4339f-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="4339f-112">但是，有效的或当前的值将保持为黄色，因为 <xref:System.Windows.Media.Animation.ColorAnimation> 仍然会重写基值。</span><span class="sxs-lookup"><span data-stu-id="4339f-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="4339f-113">如果希望基值再次成为有效值，则必须停止动画以影响属性。</span><span class="sxs-lookup"><span data-stu-id="4339f-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="4339f-114">有三种方法可通过情节提要动画实现此目的：</span><span class="sxs-lookup"><span data-stu-id="4339f-114">There are three ways to do this with storyboard animations:</span></span>  
  
- <span data-ttu-id="4339f-115">将动画的 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性设置为 <xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="4339f-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
- <span data-ttu-id="4339f-116">删除整个情节提要。</span><span class="sxs-lookup"><span data-stu-id="4339f-116">Remove the entire Storyboard.</span></span>  
  
- <span data-ttu-id="4339f-117">从单个属性中删除动画。</span><span class="sxs-lookup"><span data-stu-id="4339f-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="4339f-118">将动画的 "System.windows.media.animation.timeline.fillbehavior" 属性设置为 "停止"</span><span class="sxs-lookup"><span data-stu-id="4339f-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="4339f-119">通过将设置 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 为 <xref:System.Windows.Media.Animation.FillBehavior.Stop> ，可以告知动画在其活动期结束后停止影响其目标属性。</span><span class="sxs-lookup"><span data-stu-id="4339f-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="4339f-120">删除整个情节提要</span><span class="sxs-lookup"><span data-stu-id="4339f-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="4339f-121">通过使用 <xref:System.Windows.Media.Animation.RemoveStoryboard> 触发器或 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> 方法，可以告知情节提要动画停止影响其目标属性。</span><span class="sxs-lookup"><span data-stu-id="4339f-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="4339f-122">此方法与设置属性之间的区别在于， <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 您可以随时删除该情节提要，而 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性仅在动画到达其活动期结束时才起作用。</span><span class="sxs-lookup"><span data-stu-id="4339f-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="4339f-123">从单个属性删除动画</span><span class="sxs-lookup"><span data-stu-id="4339f-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="4339f-124">停止动画影响属性的另一种方法是使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 正在进行动画处理的对象的方法。</span><span class="sxs-lookup"><span data-stu-id="4339f-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="4339f-125">将要进行动画处理的属性指定为第一个参数，并将指定 `null` 为第二个参数。</span><span class="sxs-lookup"><span data-stu-id="4339f-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="4339f-126">此方法也适用于非情节提要动画。</span><span class="sxs-lookup"><span data-stu-id="4339f-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4339f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4339f-127">See also</span></span>

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [<span data-ttu-id="4339f-128">动画概述</span><span class="sxs-lookup"><span data-stu-id="4339f-128">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="4339f-129">属性动画技术概述</span><span class="sxs-lookup"><span data-stu-id="4339f-129">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
