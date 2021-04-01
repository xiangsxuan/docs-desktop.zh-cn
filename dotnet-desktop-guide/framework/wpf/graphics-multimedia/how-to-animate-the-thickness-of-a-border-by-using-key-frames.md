---
title: 如何：使用关键帧对边框的粗细进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970862"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>如何：使用关键帧对边框的粗细进行动画处理
此示例演示如何对的属性进行动画处理 <xref:System.Windows.Controls.Control.BorderThickness%2A> <xref:System.Windows.Controls.Border> 。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> 类对的属性进行动画处理 <xref:System.Windows.Controls.Control.BorderThickness%2A> <xref:System.Windows.Controls.Border> 。 此动画按以下方式使用三个关键帧：  
  
1. 在前半秒中，使用类的实例 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> 逐渐增加边框的粗细。 该示例使用在 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> 值之间创建平滑线性增长。  
  
2. 在接下来的半秒结束时，使用类的实例 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 突然增加边框的粗细。 分离型关键帧（如从 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 创建值之间的突然跳转），也就是说，动画的移动是不平稳的。  
  
3. 在最后两秒内，使用类的实例 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 来减小边框的粗细。 样条关键帧（如从派生的帧） <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 根据属性的值在值之间进行转换 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> 。 在此关键帧中，动画开始时缓慢，然后以指数方式加速，直到时间段结束。  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
- [对 BorderThickness 值进行动画处理](../controls/how-to-animate-a-borderthickness-value.md)
