---
title: 如何：使用 CheckBox 创建 ListViewItem
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: b09d5ad11b0961febf524cec1e19cb1e59832e44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973723"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a>如何：使用 CheckBox 创建 ListViewItem
此示例演示如何 <xref:System.Windows.Controls.CheckBox> 在使用的控件中显示一列控件 <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.GridView> 。  
  
## <a name="example"></a>示例  
 若要创建包含中的 <xref:System.Windows.Controls.CheckBox> 控件的列 <xref:System.Windows.Controls.ListView> ，请创建一个 <xref:System.Windows.DataTemplate> 包含的 <xref:System.Windows.Controls.CheckBox> 。 然后将 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 的设置 <xref:System.Windows.Controls.GridViewColumn> 为 <xref:System.Windows.DataTemplate> 。  
  
 下面的示例演示一个 <xref:System.Windows.DataTemplate> 包含的 <xref:System.Windows.Controls.CheckBox> 。 该示例将 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 的属性绑定 <xref:System.Windows.Controls.CheckBox> 到 <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> 包含它的的属性值 <xref:System.Windows.Controls.ListViewItem> 。 因此，在 <xref:System.Windows.Controls.ListViewItem> 选择包含的时 <xref:System.Windows.Controls.CheckBox> ，将 <xref:System.Windows.Controls.CheckBox> 选中。  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 下面的示例演示如何创建一个 <xref:System.Windows.Controls.CheckBox> 控件列。 为了使列成为，此示例将 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 的属性设置 <xref:System.Windows.Controls.GridViewColumn> 为 <xref:System.Windows.DataTemplate> 。  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [ListView 概述](listview-overview.md)
- [操作指南主题](listview-how-to-topics.md)
- [GridView 概述](gridview-overview.md)
