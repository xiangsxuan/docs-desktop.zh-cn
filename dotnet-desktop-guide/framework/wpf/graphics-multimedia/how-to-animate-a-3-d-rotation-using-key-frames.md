---
title: 如何：使用关键帧对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2b9059df079125c34c70237c0f600751020044c6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971725"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames"></a><span data-ttu-id="daf76-102">如何：使用关键帧对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="daf76-102">How to: Animate a 3D Rotation Using Key Frames</span></span>
<span data-ttu-id="daf76-103">在下面的示例中， <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> 用于使3d 对象旋转，同时其旋转轴动画处理导致 "wobble"。</span><span class="sxs-lookup"><span data-stu-id="daf76-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="daf76-104">此动画使用以下关键帧：</span><span class="sxs-lookup"><span data-stu-id="daf76-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="daf76-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> 用于在值之间创建平滑的线性内插。</span><span class="sxs-lookup"><span data-stu-id="daf76-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="daf76-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> 用于在值之间创建突然 "跳转" (没有内插) 。</span><span class="sxs-lookup"><span data-stu-id="daf76-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="daf76-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> 用于根据属性在值之间创建变量转换 <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> 。</span><span class="sxs-lookup"><span data-stu-id="daf76-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="daf76-108">在下面的示例中，动画的此部分的开始时间慢，但在时间段结束时，将呈指数级增加速度。</span><span class="sxs-lookup"><span data-stu-id="daf76-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daf76-109">示例</span><span class="sxs-lookup"><span data-stu-id="daf76-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="daf76-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="daf76-110">See also</span></span>

- [<span data-ttu-id="daf76-111">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="daf76-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="daf76-112">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="daf76-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="daf76-113">使用故事板对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="daf76-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="daf76-114">使用 Rotation3DAnimation 对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="daf76-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="daf76-115">使用四元数对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="daf76-115">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="daf76-116">使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="daf76-116">Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
