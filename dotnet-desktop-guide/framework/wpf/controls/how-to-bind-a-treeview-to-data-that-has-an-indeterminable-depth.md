---
title: 如何：将 TreeView 绑定到深度无法确定的数据
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: 3d9d082b712750d66c63ae0a309afb9cd3c9b4d8
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971047"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>如何：将 TreeView 绑定到深度无法确定的数据
有时可能需要将绑定 <xref:System.Windows.Controls.TreeView> 到深度未知的数据源。  如果数据在本质上是递归的，如文件系统、文件夹可以包含文件夹的位置或公司的组织结构（其中员工将其他员工作为直接下属），就会发生这种情况。  
  
 数据源必须具有分层对象模型。 例如， `Employee` 类可以包含员工对象的集合，这些对象是员工的直接下属。 如果以非层次结构的方式表示数据，则必须生成数据的分层表示形式。  
  
 设置属性时， <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> 如果 <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ItemsControl> 为每个子项生成，则子级将使用与父项 <xref:System.Windows.Controls.ItemsControl> 相同的 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 。 例如，如果在 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 数据绑定上设置属性 <xref:System.Windows.Controls.TreeView> ，则每个生成的都 <xref:System.Windows.Controls.TreeViewItem> 使用 <xref:System.Windows.DataTemplate> 分配给的属性的 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.TreeView> 。  
  
 使用可以为 <xref:System.Windows.HierarchicalDataTemplate> <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.TreeViewItem> 数据模板指定（或任何 <xref:System.Windows.Controls.HeaderedItemsControl> ）。 设置 <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> 属性时，将在应用时使用该值 <xref:System.Windows.HierarchicalDataTemplate> 。 通过使用 <xref:System.Windows.HierarchicalDataTemplate> ，您可以在中以递归方式设置 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 每个的 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.TreeView> 。  
  
## <a name="example"></a>示例  
 下面的示例演示如何将绑定 <xref:System.Windows.Controls.TreeView> 到分层数据并使用 <xref:System.Windows.HierarchicalDataTemplate> 来指定 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 每个的 <xref:System.Windows.Controls.TreeViewItem> 。  <xref:System.Windows.Controls.TreeView>绑定到表示公司中雇员的 XML 数据。  每个 `Employee` 元素可以包含其他 `Employee` 元素，以指示向谁报告。 由于数据是递归的，因此 <xref:System.Windows.HierarchicalDataTemplate> 可以应用于每个级别。  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>请参阅

- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [数据模板化概述](../data/data-templating-overview.md)
