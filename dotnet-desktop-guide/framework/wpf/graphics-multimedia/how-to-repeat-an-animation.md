---
title: 如何：重复动画
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973920"
---
# <a name="how-to-repeat-an-animation"></a>如何：重复动画
此示例演示如何使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 的属性 <xref:System.Windows.Media.Animation.Timeline> 来控制动画的重复行为。  
  
## <a name="example"></a>示例  
 的 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性 <xref:System.Windows.Media.Animation.Timeline> 控制动画重复其简单持续时间的次数。 通过使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> ，您可以指定重复一 <xref:System.Windows.Media.Animation.Timeline> 次 (迭代计数) 或指定的时间段。 无论是哪种情况，动画都会经历任意数量的开始到端运行，以便填充请求的计数或持续时间。  
  
 默认情况下，时间线的重复次数为1.0，这意味着它们播放一次并且不重复。 但是，如果将的 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性设置 <xref:System.Windows.Media.Animation.Timeline> 为 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> ，则时间线会无限期地重复。  
  
 下面的示例演示如何使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性来控制动画的重复行为。 该示例 <xref:System.Windows.FrameworkElement.Width%2A> 使用不同类型的重复行为，对每个矩形的五个矩形的属性进行动画处理。  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 有关完整示例，请参阅 [动画计时行为示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)。  
  
## <a name="see-also"></a>请参阅

- [在重复循环过程中累积动画值](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [指定时间线是否自动反转](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [动画和计时帮助主题](animation-and-timing-how-to-topics.md)
- [动画概述](animation-overview.md)
- [动画计时行为示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
