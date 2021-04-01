---
title: 如何：使用关键帧对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2b9059df079125c34c70237c0f600751020044c6
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971725"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames"></a>如何：使用关键帧对三维旋转进行动画处理
在下面的示例中， <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> 用于使3d 对象旋转，同时其旋转轴动画处理导致 "wobble"。 此动画使用以下关键帧：  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> 用于在值之间创建平滑的线性内插。  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> 用于在值之间创建突然 "跳转" (没有内插) 。  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> 用于根据属性在值之间创建变量转换 <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> 。 在下面的示例中，动画的此部分的开始时间慢，但在时间段结束时，将呈指数级增加速度。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [三维图形概述](3-d-graphics-overview.md)
- [关键帧动画概述](key-frame-animations-overview.md)
- [使用故事板对三维旋转进行动画处理](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [使用 Rotation3DAnimation 对三维旋转进行动画处理](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [使用四元数对三维旋转进行动画处理](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames)](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
