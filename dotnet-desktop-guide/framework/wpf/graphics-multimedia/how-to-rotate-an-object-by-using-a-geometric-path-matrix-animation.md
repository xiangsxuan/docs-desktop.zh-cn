---
title: 如何：使用几何路径来旋转对象（矩阵动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970589"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="cbe3e-102">如何：使用几何路径来旋转对象（矩阵动画）</span><span class="sxs-lookup"><span data-stu-id="cbe3e-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="cbe3e-103">此示例演示如何使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 和来围绕对象 <xref:System.Windows.Media.MatrixTransform> 定义的几何路径旋转 (透视) 对象 <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="cbe3e-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbe3e-104">示例</span><span class="sxs-lookup"><span data-stu-id="cbe3e-104">Example</span></span>  
 <span data-ttu-id="cbe3e-105">下面的示例使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 对象对的属性进行动画处理 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> <xref:System.Windows.Media.MatrixTransform> 。</span><span class="sxs-lookup"><span data-stu-id="cbe3e-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="cbe3e-106"><xref:System.Windows.Media.MatrixTransform>应用于按钮并使其沿着曲线路径移动。</span><span class="sxs-lookup"><span data-stu-id="cbe3e-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="cbe3e-107">由于 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 属性设置为，因此 `true` 矩形沿路径的切线旋转。</span><span class="sxs-lookup"><span data-stu-id="cbe3e-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="cbe3e-108">有关完整示例，请参阅 [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。</span><span class="sxs-lookup"><span data-stu-id="cbe3e-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="cbe3e-109">前面示例的代码版本使用 <xref:System.Windows.Media.Animation.Storyboard> 对进行动画处理 <xref:System.Windows.Media.EllipseGeometry> ，即使只应用了一个动画也是如此。</span><span class="sxs-lookup"><span data-stu-id="cbe3e-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="cbe3e-110">在代码中将单个动画应用于属性的更简单方法是使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="cbe3e-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="cbe3e-111">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe3e-111">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe3e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbe3e-112">See also</span></span>

- [<span data-ttu-id="cbe3e-113">动画概述</span><span class="sxs-lookup"><span data-stu-id="cbe3e-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="cbe3e-114">路径动画帮助主题</span><span class="sxs-lookup"><span data-stu-id="cbe3e-114">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
- [<span data-ttu-id="cbe3e-115">路径动画示例</span><span class="sxs-lookup"><span data-stu-id="cbe3e-115">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
