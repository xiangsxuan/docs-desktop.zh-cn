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
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="6486d-102">如何：使用关键帧对照相机位置和方向进行动画处理</span><span class="sxs-lookup"><span data-stu-id="6486d-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="6486d-103">在下面的示例中， <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> 用于对 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 三维场景中的位置进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="6486d-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="6486d-104">此外， <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> 用于对相机指向三维场景的方向进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="6486d-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="6486d-105">这两个动画都使用几个关键帧，它们会创建一系列动画效果：</span><span class="sxs-lookup"><span data-stu-id="6486d-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <span data-ttu-id="6486d-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> 和 <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> 用于在值之间创建平滑的线性内插。</span><span class="sxs-lookup"><span data-stu-id="6486d-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="6486d-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> 和 <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> 用于在值之间创建突然 "跳转" (没有内插) 。</span><span class="sxs-lookup"><span data-stu-id="6486d-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="6486d-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> 和 <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> 用于根据属性在值之间创建变量转换 <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6486d-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="6486d-109">在下面的示例中，动画的启动速度慢，但直到时间段结束时，以指数方式加快速度。</span><span class="sxs-lookup"><span data-stu-id="6486d-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6486d-110">示例</span><span class="sxs-lookup"><span data-stu-id="6486d-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6486d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6486d-111">See also</span></span>

- [<span data-ttu-id="6486d-112">在三维场景中对照相机位置和方向进行动画处理</span><span class="sxs-lookup"><span data-stu-id="6486d-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="6486d-113">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="6486d-113">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
