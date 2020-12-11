---
title: 如何：沿着路径针对对象进行动画处理（偏移量进行累积的矩阵动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 8b3975ef5031b50381dfa9baf7f34a58fc05ab4e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973233"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a>如何：沿着路径针对对象进行动画处理（偏移量进行累积的矩阵动画）
此示例演示如何使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 类沿着路径对对象进行动画处理，并使动画在重复时累计其偏移量值。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 对象对 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 应用于按钮的的属性进行动画处理 <xref:System.Windows.Media.MatrixTransform> 。 因此，按钮会沿着曲线路径移动。  
  
 此外，该示例将属性设置 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> 为 `true` ，这将导致动画矩阵的偏移量在动画重复时累计。 由于偏移量累积，因此按钮会在动画重复时更快速地在屏幕上移动，而不是重置为起始位置。  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 请注意，尽管 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> 属性会导致偏移量值在重复的情况下累积，但它不会导致旋转值堆积。 若要累积旋转值，请将动画的 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 和 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> 属性设置为 `true` 。  
  
 有关完整示例，请参阅 [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。 有关演示如何在 <xref:System.Windows.Media.Matrix> 不累积偏移量的情况下沿着路径对值进行动画处理的示例，请参阅按 [路径对对象进行动画处理 (矩阵动画) ](how-to-animate-an-object-along-a-path-matrix-animation.md)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [路径动画帮助主题](path-animation-how-to-topics.md)
