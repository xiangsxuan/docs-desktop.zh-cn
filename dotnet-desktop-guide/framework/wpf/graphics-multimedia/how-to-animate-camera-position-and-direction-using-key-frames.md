---
title: 如何：使用关键帧对照相机位置和方向进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 28471f9b42140a6c75b043d33939503528b63194
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973671"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>如何：使用关键帧对照相机位置和方向进行动画处理
在下面的示例中， <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> 用于对 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 三维场景中的位置进行动画处理。 此外， <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> 用于对相机指向三维场景的方向进行动画处理。 这两个动画都使用几个关键帧，它们会创建一系列动画效果：  
  
1. <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> 和 <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> 用于在值之间创建平滑的线性内插。  
  
2. <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> 和 <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> 用于在值之间创建突然 "跳转" (没有内插) 。  
  
3. <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> 和 <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> 用于根据属性在值之间创建变量转换 <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> 。 在下面的示例中，动画的启动速度慢，但直到时间段结束时，以指数方式加快速度。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [在三维场景中对照相机位置和方向进行动画处理](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [三维图形概述](3-d-graphics-overview.md)
