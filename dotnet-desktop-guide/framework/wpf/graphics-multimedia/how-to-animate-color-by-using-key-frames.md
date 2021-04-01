---
title: 如何：使用关键帧对颜色进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973545"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>如何：使用关键帧对颜色进行动画处理
此示例演示如何 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 使用关键帧对的进行动画处理 <xref:System.Windows.Media.SolidColorBrush> 。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> 类对的属性进行动画处理 <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush> 。 此动画按以下方式使用三个关键帧：  
  
1. 在前两秒内，使用类的实例 <xref:System.Windows.Media.Animation.LinearColorKeyFrame> 逐渐将颜色从绿色更改为红色。 线性关键帧，如在 <xref:System.Windows.Media.Animation.LinearColorKeyFrame> 值之间创建平滑线性过渡。  
  
2. 在接下来的半秒结束时，使用类的实例 <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> 快速将颜色从红色更改为黄色。 离散关键帧（如 <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> 创建值之间的突然变化）即，动画的此部分中的颜色变化会迅速发生，并且不是微妙的。  
  
3. 在最后两秒内，使用类的实例 <xref:System.Windows.Media.Animation.SplineColorKeyFrame> 再次更改颜色，这一次是从黄色改回绿色。 样条关键帧 <xref:System.Windows.Media.Animation.SplineColorKeyFrame> ，如根据属性的值在值之间进行变量转换 <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> 。 在此示例中，颜色变化开始时缓慢，然后以指数方式加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
