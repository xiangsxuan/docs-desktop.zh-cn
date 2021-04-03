---
title: 如何：沿着路径针对对象进行动画处理（矩阵动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 7dfc233fe60e1cea293edc44a2bba79dc6962f7c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973180"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="711c5-102">如何：沿着路径针对对象进行动画处理（矩阵动画）</span><span class="sxs-lookup"><span data-stu-id="711c5-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="711c5-103">此示例演示如何使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 类对对象沿定义的路径进行动画处理 <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="711c5-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="711c5-104">示例</span><span class="sxs-lookup"><span data-stu-id="711c5-104">Example</span></span>  
 <span data-ttu-id="711c5-105">下面的示例通过执行以下操作沿着路径针对对象进行动画处理：</span><span class="sxs-lookup"><span data-stu-id="711c5-105">The following example animates an object along a path by doing the following:</span></span>  
  
- <span data-ttu-id="711c5-106">将应用于对象，以便 <xref:System.Windows.Media.MatrixTransform> 移动它。</span><span class="sxs-lookup"><span data-stu-id="711c5-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
- <span data-ttu-id="711c5-107">使用定义路径 <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="711c5-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
- <span data-ttu-id="711c5-108">创建 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> ，并使用它对的属性进行动画处理 <xref:System.Windows.Media.Matrix> <xref:System.Windows.Media.MatrixTransform> 。</span><span class="sxs-lookup"><span data-stu-id="711c5-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="711c5-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>采用 <xref:System.Windows.Media.PathGeometry> ，并使用它来生成 <xref:System.Windows.Media.Matrix> 值。</span><span class="sxs-lookup"><span data-stu-id="711c5-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="711c5-110">有关完整示例，请参阅 [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。</span><span class="sxs-lookup"><span data-stu-id="711c5-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span> <span data-ttu-id="711c5-111">有关几何路径的详细信息，请参阅 [几何概述](geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="711c5-111">For more information about geometric paths, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="711c5-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="711c5-112">See also</span></span>

- [<span data-ttu-id="711c5-113">动画概述</span><span class="sxs-lookup"><span data-stu-id="711c5-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="711c5-114">路径动画示例</span><span class="sxs-lookup"><span data-stu-id="711c5-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="711c5-115">路径动画帮助主题</span><span class="sxs-lookup"><span data-stu-id="711c5-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
