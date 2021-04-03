---
title: 如何：沿着路径针对对象进行动画处理（双重动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973182"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="9d35c-102">如何：沿着路径针对对象进行动画处理（双重动画）</span><span class="sxs-lookup"><span data-stu-id="9d35c-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="9d35c-103">此示例演示如何使用 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 类沿定义的路径移动对象 <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="9d35c-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d35c-104">示例</span><span class="sxs-lookup"><span data-stu-id="9d35c-104">Example</span></span>  
 <span data-ttu-id="9d35c-105">下面的示例使用两个 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 对象沿几何路径移动一个矩形：</span><span class="sxs-lookup"><span data-stu-id="9d35c-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
- <span data-ttu-id="9d35c-106">第一个对 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> <xref:System.Windows.Media.TranslateTransform.X%2A> 应用到矩形的的进行了动画处理 <xref:System.Windows.Media.TranslateTransform> 。</span><span class="sxs-lookup"><span data-stu-id="9d35c-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="9d35c-107">这使矩形沿路径水平移动。</span><span class="sxs-lookup"><span data-stu-id="9d35c-107">It makes the rectangle move horizontally along the path.</span></span>  
  
- <span data-ttu-id="9d35c-108">第二个对应用于矩形的的 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 进行了动画处理 <xref:System.Windows.Media.TranslateTransform.Y%2A> <xref:System.Windows.Media.TranslateTransform> 。</span><span class="sxs-lookup"><span data-stu-id="9d35c-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="9d35c-109">这使矩形沿路径垂直移动。</span><span class="sxs-lookup"><span data-stu-id="9d35c-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="9d35c-110">有关完整示例，请参阅 [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。</span><span class="sxs-lookup"><span data-stu-id="9d35c-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="9d35c-111">使用几何路径移动对象的另一种方法是使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 对象。</span><span class="sxs-lookup"><span data-stu-id="9d35c-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="9d35c-112">有关示例，请参阅按 [路径对对象进行动画处理 (矩阵动画) ](how-to-animate-an-object-along-a-path-matrix-animation.md)。</span><span class="sxs-lookup"><span data-stu-id="9d35c-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d35c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d35c-113">See also</span></span>

- [<span data-ttu-id="9d35c-114">动画概述</span><span class="sxs-lookup"><span data-stu-id="9d35c-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="9d35c-115">路径动画帮助主题</span><span class="sxs-lookup"><span data-stu-id="9d35c-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
