---
title: 如何：沿着路径针对对象进行动画处理（点动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973179"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>如何：沿着路径针对对象进行动画处理（点动画）
此示例演示如何使用 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 对象 <xref:System.Windows.Point> 沿着曲线路径对进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Windows.Media.EllipseGeometry> 沿着定义的路径移动 <xref:System.Windows.Media.PathGeometry> 。 省略号几何图形的 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 属性（采用 <xref:System.Windows.Point> 值）指定其位置; 若要移动椭圆几何，请对其属性进行动画处理 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 。 该示例使用 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 来对 <xref:System.Windows.Media.EllipseGeometry> 对象的属性进行动画处理 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 。  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 有关完整示例，请参阅 [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。  
  
 前面示例的代码版本使用 <xref:System.Windows.Media.Animation.Storyboard> 对进行动画处理 <xref:System.Windows.Media.EllipseGeometry> ，即使只应用了一个动画也是如此。 <xref:System.Windows.Media.Animation.Storyboard>通常是应用多个动画的最简单方法，因为这些动画可以通过相同的方式控制 <xref:System.Windows.Media.Animation.Storyboard> 。 但是，使用代码时，将单个动画应用于属性的更简单方法是使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>另请参阅

- [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [动画概述](animation-overview.md)
- [路径动画帮助主题](path-animation-how-to-topics.md)
