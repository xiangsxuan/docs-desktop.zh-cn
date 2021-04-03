---
title: 如何：使用关键帧针对对象进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973178"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>如何：使用关键帧针对对象进行动画处理
此示例演示如何使用关键帧对对象（在此示例中为 <xref:System.Windows.Controls.Page.Background%2A> 控件的属性）进行动画处理 <xref:System.Windows.Controls.Page> 。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 类对控件的属性的颜色更改进行动画处理 <xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page> 。 该示例动画会按固定的时间间隔更改为不同的背景画笔。 此动画使用 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 类创建三个不同的关键帧。 动画按以下方式使用关键帧：  
  
1. 在第一秒结束时，对类的实例进行动画处理 <xref:System.Windows.Media.LinearGradientBrush> 。 此部分示例对背景色应用线性渐变，使颜色从黄色转换为橙色。  
  
2. 在下一秒结束时，对类的实例进行动画处理 <xref:System.Windows.Media.RadialGradientBrush> 。 此部分示例对背景色应用径向渐变，使颜色从白色过渡到蓝色。  
  
3. 在第三秒结束时，对类的实例进行动画处理 <xref:System.Windows.Media.DrawingBrush> 。 此部分示例将棋盘模式应用于背景。  
  
4. 动画将再次开始，并无限期地重复。  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 是唯一可与类一起使用的关键帧类型 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 。 关键帧（如 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 创建值的突然变化）即，此示例中的颜色更改突然发生。  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
