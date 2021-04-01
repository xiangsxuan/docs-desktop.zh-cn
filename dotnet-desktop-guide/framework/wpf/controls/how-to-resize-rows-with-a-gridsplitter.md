---
title: 如何：使用 GridSplitter 调整行的大小
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: 6760a7a691af4f666294556cae3bc95a4299730a
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972933"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a>如何：使用 GridSplitter 调整行的大小
此示例演示如何使用水平在 <xref:System.Windows.Controls.GridSplitter> 中的两行之间重新分布空间， <xref:System.Windows.Controls.Grid> 而无需更改的尺寸 <xref:System.Windows.Controls.Grid> 。  
  
## <a name="example"></a>示例  
 **如何创建覆盖行边缘的 GridSplitter**  
  
 若要指定在 <xref:System.Windows.Controls.GridSplitter> 中调整相邻行的大小 <xref:System.Windows.Controls.Grid> ，请将 <xref:System.Windows.Controls.Grid.Row%2A> 附加属性设置为要重设大小的行之一。 如果 <xref:System.Windows.Controls.Grid> 有多个列，请设置 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 附加属性来指定列数。 然后，将设置 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 为 <xref:System.Windows.VerticalAlignment.Top> 或 <xref:System.Windows.VerticalAlignment.Bottom> (您设置的对齐方式取决于要调整其大小的两行) 。 最后，将 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性设置为 <xref:System.Windows.HorizontalAlignment.Stretch> 。  
  
 下面的示例演示如何定义用于 <xref:System.Windows.Controls.GridSplitter> 调整相邻行大小的水平。  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <xref:System.Windows.Controls.GridSplitter>不占用自己的行的不会被中的其他控件遮盖 <xref:System.Windows.Controls.Grid> 。 有关如何避免此问题的详细信息，请参阅[确保 GridSplitter 可见](how-to-make-sure-that-a-gridsplitter-is-visible.md)。  
  
 **如何创建占据一行的 GridSplitter**  
  
 若要指定 <xref:System.Windows.Controls.GridSplitter> 在中占据行的 <xref:System.Windows.Controls.Grid> ，请将 <xref:System.Windows.Controls.Grid.Row%2A> 附加属性设置为要重设大小的行之一。 如果 <xref:System.Windows.Controls.Grid> 有多个列，请将 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 附加属性设置为列数。 然后，将设置 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 为 <xref:System.Windows.VerticalAlignment.Center> ，将 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性设置为 <xref:System.Windows.HorizontalAlignment.Stretch> ，并将 <xref:System.Windows.Controls.RowDefinition.Height%2A> 包含的行的设置为 <xref:System.Windows.Controls.GridSplitter> <xref:System.Windows.GridLength.Auto%2A> 。  
  
 下面的示例演示如何定义一个 <xref:System.Windows.Controls.GridSplitter> 占据行并调整其两侧行的大小的水平。  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.GridSplitter>
- [操作指南主题](gridsplitter-how-to-topics.md)
