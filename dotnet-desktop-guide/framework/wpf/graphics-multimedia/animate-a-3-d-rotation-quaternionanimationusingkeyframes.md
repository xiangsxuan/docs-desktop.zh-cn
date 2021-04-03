---
title: '如何：使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames) '
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973547"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="5f332-102">如何：使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames) </span><span class="sxs-lookup"><span data-stu-id="5f332-102">How to: Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="5f332-103">在下面的示例中， <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> 用于使3d 对象旋转。</span><span class="sxs-lookup"><span data-stu-id="5f332-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="5f332-104">此动画使用以下关键帧：</span><span class="sxs-lookup"><span data-stu-id="5f332-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="5f332-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> 用于在值之间创建平滑的线性内插。</span><span class="sxs-lookup"><span data-stu-id="5f332-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="5f332-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> 用于在值之间创建突然 "跳转" (没有内插) 。</span><span class="sxs-lookup"><span data-stu-id="5f332-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="5f332-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> 用于根据属性在值之间创建变量转换 <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5f332-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="5f332-108">在下面的示例中，动画的此部分的开始时间慢，但在时间段结束时，将呈指数级增加速度。</span><span class="sxs-lookup"><span data-stu-id="5f332-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f332-109">示例</span><span class="sxs-lookup"><span data-stu-id="5f332-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="5f332-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f332-110">See also</span></span>

- [<span data-ttu-id="5f332-111">使用故事板对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="5f332-111">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="5f332-112">使用 Rotation3DAnimation 对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="5f332-112">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="5f332-113">使用四元数对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="5f332-113">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="5f332-114">使用关键帧对三维旋转进行动画处理 (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="5f332-114">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="5f332-115">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="5f332-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="5f332-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="5f332-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
