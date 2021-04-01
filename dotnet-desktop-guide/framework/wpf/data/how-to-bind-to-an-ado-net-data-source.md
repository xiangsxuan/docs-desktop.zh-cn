---
title: 如何：绑定到 ADO.NET 数据源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: d7ffaae472d89ebc23804c4032a75253756dc871
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970393"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>如何：绑定到 ADO.NET 数据源

此示例演示如何将控件绑定 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> 到 ADO.NET `DataSet` 。

## <a name="example"></a>示例

在本示例中，`OleDbConnection` 对象用于连接到数据源，该数据源是在连接字符串中指定的 `Access MDB` 文件。 建立连接后，会创建一个 `OleDbDataAdapter` 对象。 `OleDbDataAdapter`对象执行 select 结构化查询语言 (SQL) 语句以从数据库中检索记录集。 通过调用的方法，将 SQL 命令中的结果存储在的中 `DataTable` `DataSet` `Fill` `OleDbDataAdapter` 。 本示例中，`DataTable` 命名为 `BookTable`。 然后，该示例将 <xref:System.Windows.FrameworkElement.DataContext%2A> 的属性设置 <xref:System.Windows.Controls.ListBox> 为 `DataSet` 对象。

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

然后，可以将的 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 属性绑定 <xref:System.Windows.Controls.ListBox> 到 `BookTable` `DataSet` ：

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

`BookItemTemplate`<xref:System.Windows.DataTemplate>定义数据显示方式的：

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

`IntColorConverter` 将 `int` 转换为颜色。 使用此转换器时， <xref:System.Windows.Controls.TextBlock.Background%2A> 如果的值小于350，则第三个颜色 <xref:System.Windows.Controls.TextBlock> 显示 `NumPages` 为绿色; 否则为红色。 此处未显示此转换器的实现。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.BindingListCollectionView>
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
