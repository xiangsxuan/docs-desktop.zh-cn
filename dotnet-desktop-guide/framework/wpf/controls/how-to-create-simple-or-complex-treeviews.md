---
title: 如何：创建简单或复杂的 TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 7edb4933ebcc0f0d2cb02754238c2342ee9dd4a2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973720"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a>如何：创建简单或复杂的 TreeView
此示例演示如何创建简单或复杂的 <xref:System.Windows.Controls.TreeView> 控件。  
  
 包含 <xref:System.Windows.Controls.TreeView> 控件的层次结构 <xref:System.Windows.Controls.TreeViewItem> ，这些控件可以包含简单的文本字符串和更复杂的内容，例如 <xref:System.Windows.Controls.Button> 控件或 <xref:System.Windows.Controls.StackPanel> 具有嵌入内容的。 可以显式定义内容， <xref:System.Windows.Controls.TreeView> 也可以使用数据源提供内容。 本主题提供这些概念的示例。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>的属性 <xref:System.Windows.Controls.TreeViewItem> 包含 <xref:System.Windows.Controls.TreeView> 为该项显示的内容。 <xref:System.Windows.Controls.TreeViewItem>还可以将 <xref:System.Windows.Controls.TreeViewItem> 控件作为其子元素，并且可以通过使用属性来定义这些子元素 <xref:System.Windows.Controls.ItemsControl.Items%2A> 。  
  
 下面的示例演示如何 <xref:System.Windows.Controls.TreeViewItem> 通过将 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 属性设置为文本字符串来显式定义内容。  
  
 [!code-xaml[TreeViewSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 下面的示例演示如何通过定义为控件定义的子元素 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.ItemsControl.Items%2A> <xref:System.Windows.Controls.Button> 。  
  
 [!code-xaml[TreeViewSimple#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 下面的示例演示如何创建， <xref:System.Windows.Controls.TreeView> 其中 <xref:System.Windows.Data.XmlDataProvider> 提供 <xref:System.Windows.Controls.TreeViewItem> 内容并 <xref:System.Windows.HierarchicalDataTemplate> 定义内容的外观。  
  
 [!code-xaml[TreeViewSimple#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 下面的示例演示如何创建一个 <xref:System.Windows.Controls.TreeView> 内容，其中 <xref:System.Windows.Controls.TreeViewItem> 包含 <xref:System.Windows.Controls.DockPanel> 具有嵌入内容的控件。  
  
 [!code-xaml[TreeViewSimple#9](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [TreeView 概述](treeview-overview.md)
- [操作指南主题](treeview-how-to-topics.md)
