---
title: 如何：在三维场景中对照相机位置和方向进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3D scenes
- camera direction [WPF], animating in 3D scenes
- 3D scenes [WPF], animating camera position
- 3D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3D scenes
- animation [WPF], camera direction in 3D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 5ce94e154cd5aa29b59260f893ec2b63a08db0fc
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973177"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a><span data-ttu-id="8741d-102">如何：在三维场景中对照相机位置和方向进行动画处理</span><span class="sxs-lookup"><span data-stu-id="8741d-102">How to: Animate Camera Position and Direction in a 3D Scene</span></span>
<span data-ttu-id="8741d-103">下面的示例演示如何对照相机位置进行动画处理，并将其指向三维场景的方向动起来。</span><span class="sxs-lookup"><span data-stu-id="8741d-103">The following example shows how to animate the position of a camera and animate the direction it is pointing in a 3D scene.</span></span> <span data-ttu-id="8741d-104">这是通过使用 <xref:System.Windows.Media.Animation.Point3DAnimation> 和 <xref:System.Windows.Media.Animation.Vector3DAnimation> 分别对和属性进行动画处理来实现的 <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> <xref:System.Windows.Media.Media3D.PerspectiveCamera> 。</span><span class="sxs-lookup"><span data-stu-id="8741d-104">This is done by using <xref:System.Windows.Media.Animation.Point3DAnimation> and <xref:System.Windows.Media.Animation.Vector3DAnimation> to animate the <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> and <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> properties respectively of the <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="8741d-105">你可以使用类似于下面的动画来更改场景的旁观者视角视图以响应事件。</span><span class="sxs-lookup"><span data-stu-id="8741d-105">You might use an animation like this to change the onlooker's view of a scene in response to an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8741d-106">示例</span><span class="sxs-lookup"><span data-stu-id="8741d-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8741d-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8741d-107">See also</span></span>

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [<span data-ttu-id="8741d-108">使用关键帧对照相机位置和方向进行动画处理</span><span class="sxs-lookup"><span data-stu-id="8741d-108">Animate Camera Position and Direction Using Key Frames</span></span>](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [<span data-ttu-id="8741d-109">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="8741d-109">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
