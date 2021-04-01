---
title: 如何：设置元素的宽度属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: fcdb8d58c17137d22edd4ee8cf6768c5d7def7c5
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970874"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>如何：设置元素的宽度属性
## <a name="example"></a>示例  
 此示例直观显示了中四个与宽度相关的属性之间的呈现行为差异 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。  
  
 <xref:System.Windows.FrameworkElement>类公开了四个用于描述元素的宽度特征的属性。 这四个属性可能会发生冲突，当发生这种情况时，将按如下所示确定优先级值： <xref:System.Windows.FrameworkElement.MinWidth%2A> 值优先于 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 值，而后者又优先于 <xref:System.Windows.FrameworkElement.Width%2A> 值。 第四个属性 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 是只读的，并报告与布局过程的交互确定的实际宽度。  
  
 下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例将 <xref:System.Windows.Shapes.Rectangle> () 的元素绘制 `rect1` 为的子元素 <xref:System.Windows.Controls.Canvas> 。 您可以 <xref:System.Windows.Shapes.Rectangle> 通过使用一系列 <xref:System.Windows.Controls.ListBox> 表示、和属性值的元素来更改的宽度属性 <xref:System.Windows.FrameworkElement.MinWidth%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> <xref:System.Windows.FrameworkElement.Width%2A> 。 通过这种方式，可直观显示每个属性的优先级。  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 下面的代码隐藏示例处理 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 事件引发的事件。 每个自定义方法都使用中的输入 <xref:System.Windows.Controls.ListBox> ，将值分析为 <xref:System.Double> ，并将值应用于指定的与宽度相关的属性。 Width 值还会转换为字符串并写入各个 <xref:System.Windows.Controls.TextBlock> 元素 (这些元素的定义不会显示在所选 XAML) 中。  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 有关完整示例，请参阅 [Width Properties 比较示例](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [面板概述](panels-overview.md)
- [设置元素的高度属性](how-to-set-the-height-properties-of-an-element.md)
- [Width Properties 比较示例](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)
