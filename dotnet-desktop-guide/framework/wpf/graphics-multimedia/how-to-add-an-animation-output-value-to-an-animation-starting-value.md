---
title: 如何：向动画起始值添加动画输出值
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 945675d03a280e2394fdb0eab27c0978dc7cc320
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970869"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a>如何：向动画起始值添加动画输出值
此示例演示如何向动画起始值添加动画输出值。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A>属性指定是否希望将动画的输出值添加到动画属性的起始值 (基值) 。 可以将 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> 属性与大多数基本动画和大多数关键帧动画一起使用。 有关详细信息，请参阅 [动画概述](animation-overview.md) 和 [关键帧动画概述](key-frame-animations-overview.md)。  
  
 下面的示例演示对使用 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> 属性 <xref:System.Windows.Media.Animation.DoubleAnimation> 并将 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> 属性与结合使用的效果 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 。  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [在重复循环过程中累积动画值](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [动画概述](animation-overview.md)
- [关键帧动画概述](key-frame-animations-overview.md)
- [动画和计时帮助主题](animation-and-timing-how-to-topics.md)
