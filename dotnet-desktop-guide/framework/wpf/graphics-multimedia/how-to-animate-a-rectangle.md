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
# <a name="how-to-animate-a-rectangle"></a>如何：对矩形进行动画处理
此示例演示如何对矩形的大小和位置变化进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例使用类的实例 <xref:System.Windows.Media.Animation.RectAnimation> 对的属性进行动画处理 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> <xref:System.Windows.Media.RectangleGeometry> ，这会对矩形的大小和位置进行动画处理。  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.RectAnimation>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.RectangleGeometry>
- [动画概述](animation-overview.md)
- [图形和多媒体](index.md)
- [图形帮助主题](graphics-how-to-topics.md)
- [动画和计时帮助主题](animation-and-timing-how-to-topics.md)
