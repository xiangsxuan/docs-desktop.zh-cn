---
title: 如何：使 UIElement 呈现为透明或半透明
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 1de9a7e11fee241ecb71242e9808e77b7e5e63b0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971817"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a>如何：使 UIElement 呈现为透明或半透明
此示例演示如何使 <xref:System.Windows.UIElement> 透明或半透明。 若要使元素透明或半透明，请设置其 <xref:System.Windows.UIElement.Opacity%2A> 属性。 值 `0.0` 使元素完全透明，而值则 `1.0` 使元素完全不透明。 如果值为 `0.5` ，则使元素50% 不透明，依此类推。 <xref:System.Windows.UIElement.Opacity%2A>默认情况下，元素的设置为 `1.0` 。  
  
## <a name="example"></a>示例  
 下面的示例将按钮的设置 <xref:System.Windows.UIElement.Opacity%2A> 为 `0.25` ，使其及其内容 (在这种情况下，该按钮的文本) 25% 不透明。  
  
 [!code-xaml[brushsamples_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 如果元素的内容具有其自己的 <xref:System.Windows.UIElement.Opacity%2A> 设置，则这些值将与包含元素相乘 <xref:System.Windows.UIElement.Opacity%2A> 。  
  
 下面的示例将按钮的设置 <xref:System.Windows.UIElement.Opacity%2A> 为 `0.25` ，并将 <xref:System.Windows.UIElement.Opacity%2A> <xref:System.Windows.Controls.Image> 包含在中的控件的设置为 `0.5` 。 因此，图像显示12.5% 不透明： 0.25 * 0.5 = 0.125。  
  
 [!code-xaml[brushsamples_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 控制元素不透明度的另一种方法是设置绘制元素的的不透明度 <xref:System.Windows.Media.Brush> 。 利用此方法，您可以有选择地改变元素部分的不透明度，并通过使用元素的属性提供性能优势 <xref:System.Windows.UIElement.Opacity%2A> 。 下面的示例设置 <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.SolidColorBrush> 用于绘制按钮的的，其 <xref:System.Windows.Controls.Control.Background%2A> 设置为 `0.25` 。 因此，画笔的背景为25% 不透明，但其内容 (按钮的文本) 仍然为100% 不透明。  
  
 [!code-xaml[brushsamples_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 您还可以控制画笔内各个颜色的不透明度。 有关颜色和画笔的详细信息，请参阅 [用纯色和渐变进行绘制概述](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。 有关演示如何对元素的不透明度进行动画处理的示例，请参阅对 [元素或画笔的不透明度进行动画处理](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md)。
