---
title: 如何：使用关键帧对布尔属性值进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973220"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a>如何：使用关键帧对布尔属性值进行动画处理
此示例演示如何使用关键帧对控件的布尔属性值进行动画处理 <xref:System.Windows.Controls.Button> 。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> 类对控件的属性进行动画处理 <xref:System.Windows.UIElement.IsEnabled%2A> <xref:System.Windows.Controls.Button> 。 此示例中的所有关键帧均使用类的实例 <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> 。 离散关键帧（如 <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create 突然跳转到值之间），也就是说，动画的移动是不平稳的。  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
