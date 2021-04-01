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
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>如何：沿着路径针对对象进行动画处理（矩阵动画）
此示例演示如何使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 类对对象沿定义的路径进行动画处理 <xref:System.Windows.Media.PathGeometry> 。  
  
## <a name="example"></a>示例  
 下面的示例通过执行以下操作沿着路径针对对象进行动画处理：  
  
- 将应用于对象，以便 <xref:System.Windows.Media.MatrixTransform> 移动它。  
  
- 使用定义路径 <xref:System.Windows.Media.PathGeometry> 。  
  
- 创建 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> ，并使用它对的属性进行动画处理 <xref:System.Windows.Media.Matrix> <xref:System.Windows.Media.MatrixTransform> 。 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>采用 <xref:System.Windows.Media.PathGeometry> ，并使用它来生成 <xref:System.Windows.Media.Matrix> 值。  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 有关完整示例，请参阅 [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。 有关几何路径的详细信息，请参阅 [几何概述](geometry-overview.md)。  
  
## <a name="see-also"></a>请参阅

- [动画概述](animation-overview.md)
- [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [路径动画帮助主题](path-animation-how-to-topics.md)
