---
title: 如何：使用关键帧对矩形几何形状进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970623"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>如何：使用关键帧对矩形几何形状进行动画处理
此示例演示如何 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 使用关键帧对的属性进行动画处理 <xref:System.Windows.Media.RectangleGeometry> 。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> 类对的属性进行动画处理 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> <xref:System.Windows.Media.RectangleGeometry> 。 此动画按以下方式使用三个关键帧：  
  
1. 在前两秒内，使用类的实例 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 对矩形的位置、宽度和高度的渐变变化进行动画处理。 线性关键帧，如在 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 值之间创建平滑线性过渡。  
  
2. 在接下来的半秒结束时，使用类的实例 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 突然降低矩形的高度。 离散关键帧（如 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 创建值之间的突然更改，即，高度的减少速度快且不微妙）。  
  
3. 在最后两秒内，使用类的实例将 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 矩形更改回其原始大小和位置。 样条关键帧 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> ，如根据属性的值在值之间进行变量转换 <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> 。 在此示例中，变化开始时缓慢，然后以指数级加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
