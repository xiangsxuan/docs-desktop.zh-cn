---
title: 如何：使用 AnimationClock 对属性进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: 13d91e8589c40d84ba374ffc613388e24407796a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970624"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a>如何：使用 AnimationClock 对属性进行动画处理
此示例演示如何使用 <xref:System.Windows.Media.Animation.Clock> 对象对属性进行动画处理。  
  
 对依赖属性进行动画处理有三种方法：  
  
- 使用创建 <xref:System.Windows.Media.Animation.AnimationTimeline> 并将其与该属性相关联 <xref:System.Windows.Media.Animation.Storyboard> 。  
  
- 使用对象的 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法将单个应用于 <xref:System.Windows.Media.Animation.AnimationTimeline> 目标属性。  
  
- 从创建 <xref:System.Windows.Media.Animation.AnimationClock> <xref:System.Windows.Media.Animation.AnimationTimeline> ，并将其应用到属性。  
  
 <xref:System.Windows.Media.Animation.Storyboard> 对象和 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法使你能够对属性进行动画处理，而无需直接创建和分发时钟 (例如，请参阅 [使用情节提要对属性进行动画](how-to-animate-a-property-by-using-a-storyboard.md) 处理并 [在不使用情节) 提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md) ; 将自动为你创建和分发时钟。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建 <xref:System.Windows.Media.Animation.AnimationClock> 并将其应用到两个相似的属性。  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 有关演示如何在启动后交互控制的示例 <xref:System.Windows.Media.Animation.Clock> ，请参阅 [以交互方式控制时钟](how-to-interactively-control-a-clock.md)。  
  
## <a name="see-also"></a>另请参阅

- [使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)
- [在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)
- [属性动画技术概述](property-animation-techniques-overview.md)
