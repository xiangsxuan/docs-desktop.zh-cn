---
title: 如何：对 SolidColorBrush 的颜色或不透明度进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970946"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>如何：对 SolidColorBrush 的颜色或不透明度进行动画处理
此示例演示如何对的和进行动画处理 <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.SolidColorBrush> 。  
  
## <a name="example"></a>示例  
 下面的示例使用三个动画对的和进行动画处理 <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.SolidColorBrush> 。  
  
- 第一个动画是 <xref:System.Windows.Media.Animation.ColorAnimation> ，将画笔的颜色更改为 <xref:System.Windows.Media.Colors.Gray%2A> 鼠标进入矩形时的颜色。  
  
- 接下来的动画会将 <xref:System.Windows.Media.Animation.ColorAnimation> 画笔的颜色更改为 <xref:System.Windows.Media.Colors.Orange%2A> 鼠标离开矩形时的颜色。  
  
- <xref:System.Windows.Media.Animation.DoubleAnimation>当按下鼠标左键时，最终动画 a 会将画笔的不透明度更改为0.0。  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 有关演示如何对不同类型的画笔进行动画处理的更完整示例，请参阅 [画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。 有关动画的详细信息，请参阅 [动画概述](animation-overview.md)。  
  
 为了与其他动画示例保持一致，此示例的代码版本使用 <xref:System.Windows.Media.Animation.Storyboard> 对象应用其动画。 但是，在代码中应用单个动画时，使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法比使用方法更为简单 <xref:System.Windows.Media.Animation.Storyboard> 。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [演示图板概述](storyboards-overview.md)
- [画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
