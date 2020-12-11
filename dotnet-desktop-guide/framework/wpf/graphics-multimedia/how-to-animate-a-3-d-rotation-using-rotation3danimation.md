---
title: 如何：使用 Rotation3DAnimation 对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with Rotation3DAnimation
- Rotation3DAnimation [WPF]
- animation [WPF], 3D translations [WPF], with Rotation3DAnimation
ms.assetid: a92223ec-b634-4f5e-8e79-d33bc43ecfb3
ms.openlocfilehash: 4016b2e17d273fc401d00e769ce721e6a381cc23
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973222"
---
# <a name="how-to-animate-a-3d-rotation-using-rotation3danimation"></a><span data-ttu-id="d8be2-102">如何：使用 Rotation3DAnimation 对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="d8be2-102">How to: Animate a 3D Rotation Using Rotation3DAnimation</span></span>
<span data-ttu-id="d8be2-103">下面的示例演示如何通过使用 <xref:System.Windows.Media.Animation.Rotation3DAnimation> 对 <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> <xref:System.Windows.Media.Media3D.RotateTransform3D> 应用于三维对象的对象的属性进行动画处理，使3d 对象在 "wobbles" 时旋转。</span><span class="sxs-lookup"><span data-stu-id="d8be2-103">The following example shows how to make a 3D object rotate while it "wobbles" by using <xref:System.Windows.Media.Animation.Rotation3DAnimation> to animate the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of the <xref:System.Windows.Media.Media3D.RotateTransform3D> object applied to the 3D object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8be2-104">示例</span><span class="sxs-lookup"><span data-stu-id="d8be2-104">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationExample.xaml#rotation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d8be2-105">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8be2-105">See also</span></span>

- [<span data-ttu-id="d8be2-106">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="d8be2-106">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="d8be2-107">使用关键帧对三维旋转进行动画处理 (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="d8be2-107">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="d8be2-108">使用故事板对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="d8be2-108">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="d8be2-109">使用四元数对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="d8be2-109">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="d8be2-110">动画概述</span><span class="sxs-lookup"><span data-stu-id="d8be2-110">Animation Overview</span></span>](animation-overview.md)