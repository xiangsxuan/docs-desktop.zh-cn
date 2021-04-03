---
title: 如何：使用演示图板对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973221"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a>如何：使用演示图板对三维旋转进行动画处理
下面的示例演示如何通过对对象的和属性进行动画处理，使3D 对象在 "wobbles" 时旋转 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> 。 此 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> 对象指定3d 对象的旋转转换，并使其属性产生动画效果，以创建所需的旋转效果。 在情节提要中， <xref:System.Windows.Media.Animation.DoubleAnimation> 用于对属性进行动画处理， <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> 而 <xref:System.Windows.Media.Animation.Vector3DAnimation> 用于对属性进行动画处理 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> 。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [使用 Rotation3DAnimation 对三维旋转进行动画处理](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [使用关键帧对三维旋转进行动画处理 (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [三维图形概述](3-d-graphics-overview.md)
- [演示图板概述](storyboards-overview.md)
