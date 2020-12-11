---
title: 如何：使用 PointAnimation 针对对象的位置进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 1ef3f77e551affaa7e61d2aabf95f10c29275417
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970867"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>如何：使用 PointAnimation 针对对象的位置进行动画处理
此示例演示如何使用 <xref:System.Windows.Media.Animation.PointAnimation> 类对中的对象进行动画处理 <xref:System.Windows.Shapes.Path> 。  
  
## <a name="example"></a>示例  
 下面的示例将一个椭圆沿 <xref:System.Windows.Shapes.Path> 屏幕上的一个点移到另一个点。 该示例 <xref:System.Windows.Media.EllipseGeometry> 通过使用 <xref:System.Windows.Media.Animation.PointAnimation> 对属性进行动画处理来对的位置进行动画处理 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 。  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [动画概述](animation-overview.md)
- [图形和多媒体](index.md)
- [图形帮助主题](graphics-how-to-topics.md)
- [动画和计时帮助主题](animation-and-timing-how-to-topics.md)
