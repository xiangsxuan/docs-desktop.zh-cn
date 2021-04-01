---
title: 如何：使用关键帧对大小变化进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970949"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>如何：使用关键帧对大小变化进行动画处理
此示例演示如何使用关键帧对大小变化进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> 类对的属性进行动画处理 <xref:System.Windows.Media.ArcSegment.Size%2A> <xref:System.Windows.Media.ArcSegment> 。 此动画按以下方式使用三个关键帧：  
  
1. 在动画的前半秒中，使用类的实例 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 逐渐增加弧的大小。线性关键帧，如在 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 值之间创建平滑线性过渡。  
  
2. 在接下来的半秒结束时，使用类的实例 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> 突然增加弧的大小。离散关键帧（如 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create 突然跳转到值之间），也就是说，大小变化突然发生，并且不是微妙的。  
  
3. 在最后两秒内，使用类的实例 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> 来增加弧的大小。样条关键帧 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> ，如根据属性的值在值之间进行变量转换 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> 。 在本例中，弧的大小开始时缓慢增加，然后以指数方式增加，直到时间段结束。  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
