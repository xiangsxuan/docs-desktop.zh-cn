---
title: 如何：设置元素的高度属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: f18612d66c477562eb387b76ea30e71dd5f4e8d7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973809"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>如何：设置元素的高度属性
## <a name="example"></a>示例  
 此示例直观显示了中四个与高度相关的属性之间的呈现行为差异 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。  
  
 <xref:System.Windows.FrameworkElement>类公开四个属性，这些属性描述元素的高度特性。 这四个属性可能会发生冲突，当发生这种情况时，将按如下所示确定优先级值： <xref:System.Windows.FrameworkElement.MinHeight%2A> 值优先于 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 值，而后者又优先于 <xref:System.Windows.FrameworkElement.Height%2A> 值。 第四个属性 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 是只读的，并报告与布局过程的交互确定的实际高度。  
  
 下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例将 <xref:System.Windows.Shapes.Rectangle> () 的元素绘制 `rect1` 为的子元素 <xref:System.Windows.Controls.Canvas> 。 您可以 <xref:System.Windows.Shapes.Rectangle> 通过使用一系列 <xref:System.Windows.Controls.ListBox> 表示、和属性值的元素来更改的高度属性 <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> <xref:System.Windows.FrameworkElement.Height%2A> 。 通过这种方式，可直观显示每个属性的优先级。  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 下面的代码隐藏示例处理 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 事件引发的事件。 每个处理程序都从获取输入 <xref:System.Windows.Controls.ListBox> ，将值分析为 <xref:System.Double> ，并将值应用于指定的与高度相关的属性。 高度值还会转换为字符串并写入各个 <xref:System.Windows.Controls.TextBlock> 元素 (这些元素的定义不会显示在所选 XAML) 中。  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 有关完整示例，请参阅 [高度属性示例](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [设置元素的宽度属性](how-to-set-the-width-properties-of-an-element.md)
- [面板概述](panels-overview.md)
- [Height 属性示例](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
