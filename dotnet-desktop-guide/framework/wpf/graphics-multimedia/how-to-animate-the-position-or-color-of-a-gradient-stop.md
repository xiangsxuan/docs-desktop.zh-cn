---
title: 如何：对渐变停止点的位置或颜色进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970866"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>如何：对渐变停止点的位置或颜色进行动画处理
此示例演示如何对对象的和进行动画处理 <xref:System.Windows.Media.GradientStop.Color%2A> <xref:System.Windows.Media.GradientStop.Offset%2A> <xref:System.Windows.Media.GradientStop> 。  
  
## <a name="example"></a>示例  
 下面的示例在中对三个梯度停止点进行动画处理 <xref:System.Windows.Media.LinearGradientBrush> 。 该示例使用三个动画，其中每个动画对不同梯度停止点进行动画处理：  
  
- 第一个动画（a <xref:System.Windows.Media.Animation.DoubleAnimation> ）动画处理第一个梯度停止点（ <xref:System.Windows.Media.GradientStop.Offset%2A> 从0.0 到1.0，然后再回0.0）。 因此，渐变中的第一种颜色会从矩形的左侧向右移动，然后返回到左侧。  
  
- 第二个动画（a）动画处理 <xref:System.Windows.Media.Animation.ColorAnimation> 第二个梯度停止点， <xref:System.Windows.Media.GradientStop.Color%2A> <xref:System.Windows.Media.Colors.Purple%2A> <xref:System.Windows.Media.Colors.Yellow%2A> 然后返回到 <xref:System.Windows.Media.Colors.Purple%2A> 。 因此，渐变的中间颜色会从紫色变为黄色并返回到紫色。  
  
- 第三个动画，另一个动画会 <xref:System.Windows.Media.Animation.ColorAnimation> 将第三个梯度停止点的不透明度进行动画处理， <xref:System.Windows.Media.GradientStop.Color%2A> 然后返回。 因此，渐变中的第三种颜色淡出，然后再次变为不透明。  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 虽然此示例使用，但在中对 <xref:System.Windows.Media.LinearGradientBrush> 对象进行动画处理是相同的 <xref:System.Windows.Media.GradientStop> <xref:System.Windows.Media.RadialGradientBrush> 。  
  
 有关其他示例，请参阅 [画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.GradientStop>
- [动画概述](animation-overview.md)
- [演示图板概述](storyboards-overview.md)
