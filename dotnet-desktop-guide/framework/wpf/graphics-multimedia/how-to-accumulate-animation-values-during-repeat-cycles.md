---
title: 如何：在重复循环过程中累积动画值
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: bccdc9b7bf2d5a0ea476e39e8d54107854db7ae3
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973581"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>如何：在重复循环过程中累积动画值
此示例演示如何使用 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 属性在重复循环之间累积动画值。  
  
## <a name="example"></a>示例  
 使用 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 属性可在重复循环之间累计动画的基值。 例如，如果你将动画设置为重复 (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 为 "9x" 的9倍 ) 并且将属性设置为在10到15之间进行动画处理 (从 = 10 到 = 15) ），则在第一个周期（从15到20）期间，此属性将在第一个周期（从15到20，在第三个周期中为20到25）进行动画 因此，每个动画周期都使用上一动画周期中的结束动画值作为其基值。  
  
 可以将 `IsCumulative` 属性与大多数基本动画和大多数关键帧动画一起使用。 有关详细信息，请参阅 [动画概述](animation-overview.md) 和 [关键帧动画概述](key-frame-animations-overview.md)。  
  
 下面的示例通过对四个矩形的宽度进行动画处理来显示此行为。 示例：  
  
- 对第一个矩形进行动画处理 <xref:System.Windows.Media.Animation.DoubleAnimation> ，并将 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 属性设置为 `true` 。  
  
- 对第二个矩形进行动画处理 <xref:System.Windows.Media.Animation.DoubleAnimation> ，并将 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 属性设置为的默认值 `false` 。  
  
- 对第三个矩形进行动画处理 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> ，并将 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> 属性设置为 `true` 。  
  
- 对最后一个矩形进行动画处理 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> ，并将 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> 属性设置为 `false` 。  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>请参阅

- [向动画起始值添加动画输出值](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [重复动画](how-to-repeat-an-animation.md)
- [动画概述](animation-overview.md)
- [关键帧动画概述](key-frame-animations-overview.md)
- [操作指南主题](animation-and-timing-how-to-topics.md)
