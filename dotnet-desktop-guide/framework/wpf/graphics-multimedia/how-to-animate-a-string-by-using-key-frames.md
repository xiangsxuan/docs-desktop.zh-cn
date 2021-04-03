---
title: 如何：使用关键帧对字符串进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972925"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>如何：使用关键帧对字符串进行动画处理
此示例演示如何使用关键帧对字符串（在本示例中为 <xref:System.Windows.Controls.ContentControl.Content%2A> 控件的属性）进行动画处理 <xref:System.Windows.Controls.Button> 。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> 类对的属性进行动画处理 <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.Button> 。  
  
 此示例中的所有关键帧都使用类的实例， <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> 因为使用关键帧创建的字符串动画只能使用离散关键帧。 离散关键帧（如 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create 突然跳转到值之间），这就是动画的更改会迅速发生，并且不是微妙的。  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
