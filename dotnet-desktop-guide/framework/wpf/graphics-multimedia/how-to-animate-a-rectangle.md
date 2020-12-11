---
title: 如何：对矩形进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], rectangles
- rectangles [WPF], animating
ms.assetid: 572ffb95-790d-4ace-adbf-b2ea8a90e75b
ms.openlocfilehash: 7f7cf24f7883553329de3761ff0670e8e3a09463
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972926"
---
# <a name="how-to-animate-a-rectangle"></a><span data-ttu-id="b985d-102">如何：对矩形进行动画处理</span><span class="sxs-lookup"><span data-stu-id="b985d-102">How to: Animate a Rectangle</span></span>
<span data-ttu-id="b985d-103">此示例演示如何对矩形的大小和位置变化进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="b985d-103">This example shows how to animate changes to the size and position of a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b985d-104">示例</span><span class="sxs-lookup"><span data-stu-id="b985d-104">Example</span></span>  
 <span data-ttu-id="b985d-105">下面的示例使用类的实例 <xref:System.Windows.Media.Animation.RectAnimation> 对的属性进行动画处理 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> <xref:System.Windows.Media.RectangleGeometry> ，这会对矩形的大小和位置进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="b985d-105">The following example uses an instance of the <xref:System.Windows.Media.Animation.RectAnimation> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>, which animates changes to the size and position of the rectangle.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b985d-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b985d-106">See also</span></span>

- <xref:System.Windows.Media.Animation.RectAnimation>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.RectangleGeometry>
- [<span data-ttu-id="b985d-107">动画概述</span><span class="sxs-lookup"><span data-stu-id="b985d-107">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="b985d-108">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="b985d-108">Graphics and Multimedia</span></span>](index.md)
- [<span data-ttu-id="b985d-109">图形帮助主题</span><span class="sxs-lookup"><span data-stu-id="b985d-109">Graphics How-to Topics</span></span>](graphics-how-to-topics.md)
- [<span data-ttu-id="b985d-110">动画和计时帮助主题</span><span class="sxs-lookup"><span data-stu-id="b985d-110">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
