---
title: 如何：使用演示图板对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973221"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a><span data-ttu-id="dc9fa-102">如何：使用演示图板对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="dc9fa-102">How to: Animate a 3D Rotation Using Storyboards</span></span>
<span data-ttu-id="dc9fa-103">下面的示例演示如何通过对对象的和属性进行动画处理，使3D 对象在 "wobbles" 时旋转 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> 。</span><span class="sxs-lookup"><span data-stu-id="dc9fa-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="dc9fa-104">此 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> 对象指定3d 对象的旋转转换，并使其属性产生动画效果，以创建所需的旋转效果。</span><span class="sxs-lookup"><span data-stu-id="dc9fa-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="dc9fa-105">在情节提要中， <xref:System.Windows.Media.Animation.DoubleAnimation> 用于对属性进行动画处理， <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> 而 <xref:System.Windows.Media.Animation.Vector3DAnimation> 用于对属性进行动画处理 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> 。</span><span class="sxs-lookup"><span data-stu-id="dc9fa-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc9fa-106">示例</span><span class="sxs-lookup"><span data-stu-id="dc9fa-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="dc9fa-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc9fa-107">See also</span></span>

- [<span data-ttu-id="dc9fa-108">使用 Rotation3DAnimation 对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="dc9fa-108">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="dc9fa-109">使用关键帧对三维旋转进行动画处理 (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="dc9fa-109">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="dc9fa-110">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="dc9fa-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="dc9fa-111">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="dc9fa-111">Storyboards Overview</span></span>](storyboards-overview.md)
