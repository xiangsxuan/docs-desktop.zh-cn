---
title: 如何：使用 From、To 和 By 控制动画
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: b06df97dc57c58a01f30be2d70bfeebf104521ad
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973124"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>如何：使用 From、To 和 By 控制动画
"From/To/By" 或 "基本动画" 创建两个目标值之间的转换 (参阅 [动画概述](animation-overview.md) ，了解不同类型的动画) 的简介。 若要设置基本动画的目标值，请使用其 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 、 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性。  下表总结了如何 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 结合使用、和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性，以确定动画的目标值。  
  
|指定的属性|产生的行为|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|动画从属性指定的值前进到要 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 进行动画处理的属性的基值或前一个动画的输出值，具体取决于以前的动画的配置方式。|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|动画从属性指定的值前进 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 到属性指定的值 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 。|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|动画从属性指定的值前进 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 到和属性的和所指定的值 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 。|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|动画从经过动画处理的属性的基值或前一个动画的输出值前进到属性指定的值 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 。|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|动画从要进行动画处理的属性的基值或前一个动画的输出值前进到该值与属性指定的值的和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 。|  
  
> [!NOTE]
> 不要 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 在同一动画上设置属性和属性。  
  
 若要在两个以上的目标值之间使用内插方法或进行动画处理，请使用关键帧动画。 有关详细信息，请参阅 [关键帧动画概述](key-frame-animations-overview.md) 。  
  
 有关将多个动画应用于单个属性的信息，请参阅 [关键帧动画概述](key-frame-animations-overview.md)。  
  
 下面的示例显示了 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 在动画上设置、和属性的不同效果。  
  
## <a name="example"></a>示例  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>请参阅

- [动画概述](animation-overview.md)
- [关键帧动画概述](key-frame-animations-overview.md)
- [From、To 和 By 动画目标值示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
