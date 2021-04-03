---
title: '如何：使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames) '
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973547"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>如何：使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames) 
在下面的示例中， <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> 用于使3d 对象旋转。 此动画使用以下关键帧：  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> 用于在值之间创建平滑的线性内插。  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> 用于在值之间创建突然 "跳转" (没有内插) 。  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> 用于根据属性在值之间创建变量转换 <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> 。 在下面的示例中，动画的此部分的开始时间慢，但在时间段结束时，将呈指数级增加速度。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [使用故事板对三维旋转进行动画处理](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [使用 Rotation3DAnimation 对三维旋转进行动画处理](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [使用四元数对三维旋转进行动画处理](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [使用关键帧对三维旋转进行动画处理 (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [三维图形概述](3-d-graphics-overview.md)
- [关键帧动画概述](key-frame-animations-overview.md)
