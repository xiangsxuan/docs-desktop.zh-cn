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
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a><span data-ttu-id="f2e3c-102">如何：使用四元数对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="f2e3c-102">How to: Animate a 3D Rotation Using Quaternions</span></span>
<span data-ttu-id="f2e3c-103">此示例演示如何使用四元数对三维对象的旋转进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="f2e3c-103">This example shows how to animate a rotation of a 3D object using quaternions.</span></span>  
  
 <span data-ttu-id="f2e3c-104">下面的代码演示了一个用作的 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> 属性的值 <xref:System.Windows.Media.Media3D.RotateTransform3D> 。</span><span class="sxs-lookup"><span data-stu-id="f2e3c-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="f2e3c-105"><xref:System.Windows.Media.Media3D.QuaternionRotation3D> <xref:System.Windows.Media.Animation.QuaternionAnimation> 使用下面的代码在中通过对进行动画处理 <xref:System.Windows.Media.Animation.Storyboard> 。</span><span class="sxs-lookup"><span data-stu-id="f2e3c-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="f2e3c-106">示例</span><span class="sxs-lookup"><span data-stu-id="f2e3c-106">Example</span></span>  
 <span data-ttu-id="f2e3c-107">下面的代码显示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="f2e3c-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f2e3c-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2e3c-108">See also</span></span>

- [<span data-ttu-id="f2e3c-109">动画概述</span><span class="sxs-lookup"><span data-stu-id="f2e3c-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f2e3c-110">创建三维场景</span><span class="sxs-lookup"><span data-stu-id="f2e3c-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="f2e3c-111">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="f2e3c-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="f2e3c-112">转换概述</span><span class="sxs-lookup"><span data-stu-id="f2e3c-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="f2e3c-113">使用故事板对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="f2e3c-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="f2e3c-114">使用 Rotation3DAnimation 对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="f2e3c-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
