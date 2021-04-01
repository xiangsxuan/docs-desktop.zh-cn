---
title: 如何：使用四元数对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973225"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a>如何：使用四元数对三维旋转进行动画处理
此示例演示如何使用四元数对三维对象的旋转进行动画处理。  
  
 下面的代码演示了一个用作的 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> 属性的值 <xref:System.Windows.Media.Media3D.RotateTransform3D> 。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> <xref:System.Windows.Media.Animation.QuaternionAnimation> 使用下面的代码在中通过对进行动画处理 <xref:System.Windows.Media.Animation.Storyboard> 。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>示例  
 下面的代码显示了整个示例。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>请参阅

- [动画概述](animation-overview.md)
- [创建三维场景](how-to-create-a-3-d-scene.md)
- [三维图形概述](3-d-graphics-overview.md)
- [转换概述](transforms-overview.md)
- [使用故事板对三维旋转进行动画处理](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [使用 Rotation3DAnimation 对三维旋转进行动画处理](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
