---
title: Expander 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
ms.openlocfilehash: 3fcbcc67b65383133eef8d3e59cb1f8f0ff06f20
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972467"
---
# <a name="expander-overview"></a>Expander 概述
<xref:System.Windows.Controls.Expander>控件提供了一种在类似于窗口并包含标题的可展开区域中提供内容的方式。  

<a name="CreatinganExpanderinXAML"></a>
## <a name="creating-a-simple-expander"></a>创建简单的 Expander  
 下面的示例演示如何创建一个简单的 <xref:System.Windows.Controls.Expander> 控件。 此示例创建一个与 <xref:System.Windows.Controls.Expander> 上图类似的。  
  
 [!code-xaml[ExpanderExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 的 <xref:System.Windows.Controls.ContentControl.Content%2A> 和 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> <xref:System.Windows.Controls.Expander> 还可以包含复杂内容，如 <xref:System.Windows.Controls.RadioButton> 和 <xref:System.Windows.Controls.Image> 对象。  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>
## <a name="setting-the-direction-of-the-expanding-content-area"></a>设置展开内容区域的方向  
 您可以使用属性将控件的内容区域设置 <xref:System.Windows.Controls.Expander> 为 (<xref:System.Windows.Controls.ExpandDirection.Down> 、 <xref:System.Windows.Controls.ExpandDirection.Up> 、 <xref:System.Windows.Controls.ExpandDirection.Left> 或 <xref:System.Windows.Controls.ExpandDirection.Right>) 的四个方向之一展开 <xref:System.Windows.Controls.ExpandDirection> 。 当内容区域处于折叠状态时，仅 <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 显示及其切换按钮。 <xref:System.Windows.Controls.Button>显示方向箭头的控件用作用于展开或折叠内容区域的切换按钮。 展开后，会 <xref:System.Windows.Controls.Expander> 尝试将其所有内容显示在类似于窗口的区域中。  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>在面板中控制 Expander 的大小  
 如果 <xref:System.Windows.Controls.Expander> 控件位于从继承的布局控件内（ <xref:System.Windows.Controls.Panel> 如），则在 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 属性设置为或时，不要在上指定 <xref:System.Windows.Controls.ExpandDirection.Down> <xref:System.Windows.Controls.ExpandDirection.Up> 。 同样， <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Controls.Expander> 如果将 <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 属性设置为或，则不要在上指定 <xref:System.Windows.Controls.ExpandDirection.Left> <xref:System.Windows.Controls.ExpandDirection.Right> 。  
  
 当你 <xref:System.Windows.Controls.Expander> 在控件上按显示展开内容的方向设置大小维度时， <xref:System.Windows.Controls.Expander> 会控制内容所使用的区域并在其周围显示边框。 即使内容已折叠，也会显示该边框。 若要设置展开内容区域的大小，请在的内容上设置大小维度 <xref:System.Windows.Controls.Expander> ，或者，如果你希望滚动功能，请在包含内容的上设置大小 <xref:System.Windows.Controls.ScrollViewer> 。  
  
 当 <xref:System.Windows.Controls.Expander> 控件是中的最后一个元素时 <xref:System.Windows.Controls.DockPanel> ， [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 会自动将 <xref:System.Windows.Controls.Expander> 维度设置为等于的剩余区域 <xref:System.Windows.Controls.DockPanel> 。 若要防止此默认行为，请将 <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> 对象的属性设置 <xref:System.Windows.Controls.DockPanel> 为 `false` ，或确保 <xref:System.Windows.Controls.Expander> 不是中的最后一个元素 <xref:System.Windows.Controls.DockPanel> 。  
  
<a name="CreatingScrollableContent"></a>
## <a name="creating-scrollable-content"></a>创建可滚动内容  
 如果内容超出内容区域的大小，可以在中包装的内容， <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.ScrollViewer> 以便提供可滚动的内容。 <xref:System.Windows.Controls.Expander>控件不自动提供滚动功能。 下图显示了一个 <xref:System.Windows.Controls.Expander> 包含控件的控件 <xref:System.Windows.Controls.ScrollViewer> 。  
  
 **ScrollViewer 中的 Expander**  
  
 ![显示具有滚动条的扩展器的屏幕截图。](./media/expander-overview/expander-scrollbar-control.jpg)  
  
 将 <xref:System.Windows.Controls.Expander> 控件放置在中时 <xref:System.Windows.Controls.ScrollViewer> ，请将 <xref:System.Windows.Controls.ScrollViewer> 与内容的打开方向相对应的维度属性设置 <xref:System.Windows.Controls.Expander> 为 <xref:System.Windows.Controls.Expander> 内容区域的大小。 例如，如果将 <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 上的属性设置 <xref:System.Windows.Controls.Expander> 为 <xref:System.Windows.Controls.ExpandDirection.Down> (内容区域) 关闭，请将控件的属性设置 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.ScrollViewer> 为内容区域所需的高度。 如果改为对内容本身设置 height 维度，则不 <xref:System.Windows.Controls.ScrollViewer> 会识别此设置，因此，不提供可滚动的内容。  
  
 下面的示例演示如何创建 <xref:System.Windows.Controls.Expander> 具有复杂内容并包含控件的控件 <xref:System.Windows.Controls.ScrollViewer> 。 此示例创建一个 <xref:System.Windows.Controls.Expander> ，它类似于本部分开头的插图。  
  
 [!code-csharp[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>
## <a name="using-the-alignment-properties"></a>使用对齐属性  
 可以通过设置控件的和属性来对齐内容 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> <xref:System.Windows.Controls.Expander> 。 当设置这些属性时，对齐将同时应用于标头和展开的内容。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Expander>
- <xref:System.Windows.Controls.ExpandDirection>
- [操作指南主题](expander-how-to-topics.md)
