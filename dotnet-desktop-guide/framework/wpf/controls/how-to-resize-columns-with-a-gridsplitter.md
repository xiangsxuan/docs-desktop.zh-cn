---
title: 如何：使用 GridSplitter 调整列的大小
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: f743e9ccf8a984a646a4b8f05ee99162e5bc73ad
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972935"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a>如何：使用 GridSplitter 调整列的大小
此示例演示如何创建一个垂直，以便在 <xref:System.Windows.Controls.GridSplitter> 中重新分布两列之间的空间， <xref:System.Windows.Controls.Grid> 而无需更改的尺寸 <xref:System.Windows.Controls.Grid> 。  
  
## <a name="example"></a>示例  
 **如何创建覆盖列边缘的 GridSplitter**  
  
 若要指定在 <xref:System.Windows.Controls.GridSplitter> 中调整相邻列的大小 <xref:System.Windows.Controls.Grid> ，请将 <xref:System.Windows.Controls.Grid.Column%2A> 附加属性设置为要重设大小的列之一。 如果 <xref:System.Windows.Controls.Grid> 有多个行，请将 <xref:System.Windows.Controls.Grid.RowSpan%2A> 附加属性设置为行数。 然后将 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性设置为 <xref:System.Windows.HorizontalAlignment.Left> 或 <xref:System.Windows.HorizontalAlignment.Right> (您设置的对齐方式取决于要重设其大小) 的两个列。 最后，将 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 属性设置为 <xref:System.Windows.VerticalAlignment.Stretch> 。  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <xref:System.Windows.Controls.GridSplitter>不具有自己的列的可能会被中的其他控件遮盖 <xref:System.Windows.Controls.Grid> 。 有关如何避免此问题的详细信息，请参阅[确保 GridSplitter 可见](how-to-make-sure-that-a-gridsplitter-is-visible.md)。  
  
 **如何创建占据一列的 GridSplitter**  
  
 若要指定 <xref:System.Windows.Controls.GridSplitter> 在中占据列的 <xref:System.Windows.Controls.Grid> ，请将 <xref:System.Windows.Controls.Grid.Column%2A> 附加属性设置为要重设大小的列之一。 如果网格具有多行，请将 <xref:System.Windows.Controls.Grid.RowSpan%2A> 附加属性设置为行数。 然后，将设置 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 为 <xref:System.Windows.HorizontalAlignment.Center> ，将 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 属性设置为 <xref:System.Windows.VerticalAlignment.Stretch> ，并将 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 包含的列的设置为 <xref:System.Windows.Controls.GridSplitter> <xref:System.Windows.GridLength.Auto%2A> 。  
  
 下面的示例演示如何定义一个垂直 <xref:System.Windows.Controls.GridSplitter> ，它占用一列并调整其两侧的列的大小。  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.GridSplitter>
- [操作指南主题](gridsplitter-how-to-topics.md)
