---
title: 如何：使用几何路径来旋转对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973919"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>如何：使用几何路径来旋转对象
此示例演示如何沿对象定义的几何路径旋转 (透视) 对象 <xref:System.Windows.Media.PathGeometry> 。  
  
## <a name="example"></a>示例  
 下面的示例使用三个 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 对象沿几何路径移动一个矩形。  
  
- 第一个 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 动画处理 <xref:System.Windows.Media.RotateTransform> 应用于矩形的。 该动画会生成角度值。 它使矩形沿着路径的轮廓旋转（转动）。  
  
- 其他两个对象对应用于矩形的的和值进行动画处理 <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform.Y%2A> <xref:System.Windows.Media.TranslateTransform> 。 它们使矩形沿路径水平和垂直移动。  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 使用几何路径旋转对象的另一种方法是使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 对象并将其 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 属性设置为 `true` 。 有关详细信息和示例，请参阅 [使用几何路径旋转对象 (矩阵动画) ](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)。  
  
 有关完整示例，请参阅 [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。  
  
## <a name="see-also"></a>请参阅

- [动画概述](animation-overview.md)
- [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [路径动画帮助主题](path-animation-how-to-topics.md)
