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
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a>如何：在使用演示图板对属性进行动画处理后设置该属性
在某些情况下，可能会出现这样的情况：您在对属性进行动画处理后，不能更改该属性的值。  
  
## <a name="example"></a>示例  
 在下面的示例中， <xref:System.Windows.Media.Animation.Storyboard> 用于对的颜色进行动画处理 <xref:System.Windows.Media.SolidColorBrush> 。 当单击此按钮时，将触发情节提要。 <xref:System.Windows.Media.Animation.Timeline.Completed>处理事件，以便在完成时通知程序 <xref:System.Windows.Media.Animation.ColorAnimation> 。  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a>示例  
 完成后 <xref:System.Windows.Media.Animation.ColorAnimation> ，程序将尝试将画笔的颜色更改为蓝色。  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 前面的代码不会执行任何操作：画笔保持为黄色，这是由动画处理画笔的所提供的值 <xref:System.Windows.Media.Animation.ColorAnimation> 。 基础属性值 (基值) 实际变为蓝色。 但是，有效的或当前的值将保持为黄色，因为 <xref:System.Windows.Media.Animation.ColorAnimation> 仍然会重写基值。 如果希望基值再次成为有效值，则必须停止动画以影响属性。 有三种方法可通过情节提要动画实现此目的：  
  
- 将动画的 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性设置为 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
  
- 删除整个情节提要。  
  
- 从单个属性中删除动画。  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a>将动画的 "System.windows.media.animation.timeline.fillbehavior" 属性设置为 "停止"  
 通过将设置 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 为 <xref:System.Windows.Media.Animation.FillBehavior.Stop> ，可以告知动画在其活动期结束后停止影响其目标属性。  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a>删除整个情节提要  
 通过使用 <xref:System.Windows.Media.Animation.RemoveStoryboard> 触发器或 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> 方法，可以告知情节提要动画停止影响其目标属性。 此方法与设置属性之间的区别在于， <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 您可以随时删除该情节提要，而 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性仅在动画到达其活动期结束时才起作用。  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a>从单个属性删除动画  
 停止动画影响属性的另一种方法是使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 正在进行动画处理的对象的方法。 将要进行动画处理的属性指定为第一个参数，并将指定 `null` 为第二个参数。  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 此方法也适用于非情节提要动画。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [动画概述](animation-overview.md)
- [属性动画技术概述](property-animation-techniques-overview.md)
