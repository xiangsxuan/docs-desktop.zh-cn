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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970589"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>如何：使用几何路径来旋转对象（矩阵动画）
此示例演示如何使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 和来围绕对象 <xref:System.Windows.Media.MatrixTransform> 定义的几何路径旋转 (透视) 对象 <xref:System.Windows.Media.PathGeometry> 。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 对象对的属性进行动画处理 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> <xref:System.Windows.Media.MatrixTransform> 。 <xref:System.Windows.Media.MatrixTransform>应用于按钮并使其沿着曲线路径移动。 由于 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 属性设置为，因此 `true` 矩形沿路径的切线旋转。  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 有关完整示例，请参阅 [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。  
  
 前面示例的代码版本使用 <xref:System.Windows.Media.Animation.Storyboard> 对进行动画处理 <xref:System.Windows.Media.EllipseGeometry> ，即使只应用了一个动画也是如此。 在代码中将单个动画应用于属性的更简单方法是使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [路径动画帮助主题](path-animation-how-to-topics.md)
- [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
