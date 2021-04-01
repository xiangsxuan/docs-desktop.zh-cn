---
title: 如何：指定时间线是否自动反转
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971002"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>如何：指定时间线是否自动反转
时间线的 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 属性确定它在完成向前迭代后是否按相反的顺序播放。 下面的示例显示了几个动画，它们具有相同的持续时间和目标值，但具有不同的 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 设置。 为了演示属性在 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 不同 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 设置下的行为，某些动画设置为重复。 最后一个动画显示了 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 属性如何在嵌套时间线上工作。  
  
## <a name="example"></a>示例  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
