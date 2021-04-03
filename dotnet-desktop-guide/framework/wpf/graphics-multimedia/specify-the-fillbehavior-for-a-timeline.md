---
title: 如何：为已经到达有效期末尾的时间线指定 FillBehavior
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972748"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>如何：为已经到达有效期末尾的时间线指定 FillBehavior
此示例演示如何 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 为动画属性的非活动指定 <xref:System.Windows.Media.Animation.Timeline> 。  
  
## <a name="example"></a>示例  
 的 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性 <xref:System.Windows.Media.Animation.Timeline> 确定动画属性的值在未进行动画处理时所发生的情况，即，当 <xref:System.Windows.Media.Animation.Timeline> 处于非活动状态但其父级 <xref:System.Windows.Media.Animation.Timeline> 在其活动或保持期内时的行为。 例如，动画结束后动画属性是否保持其结束值，或者是否还原为开始动画前的值？  
  
 下面的示例使用 <xref:System.Windows.Media.Animation.DoubleAnimation> 对两个矩形的进行动画处理 <xref:System.Windows.FrameworkElement.Width%2A> 。 每个矩形都使用不同的 <xref:System.Windows.Media.Animation.Timeline> 对象。  
  
 一个 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 设置为 <xref:System.Windows.Media.Animation.FillBehavior.Stop> ，它会使矩形的宽度在结束时恢复回其非动画值 <xref:System.Windows.Media.Animation.Timeline> 。 另 <xref:System.Windows.Media.Animation.Timeline> 一个具有 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 的 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> ，这会导致在结束时宽度保持其结束值 <xref:System.Windows.Media.Animation.Timeline> 。  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 有关完整示例，请参阅 [动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [动画概述](animation-overview.md)
- [动画和计时帮助主题](animation-and-timing-how-to-topics.md)
