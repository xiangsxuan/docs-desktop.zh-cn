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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970393"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="14586-102">如何：绑定到 ADO.NET 数据源</span><span class="sxs-lookup"><span data-stu-id="14586-102">How to: Bind to an ADO.NET Data Source</span></span>

<span data-ttu-id="14586-103">此示例演示如何将控件绑定 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> 到 ADO.NET `DataSet` 。</span><span class="sxs-lookup"><span data-stu-id="14586-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an ADO.NET `DataSet`.</span></span>

## <a name="example"></a><span data-ttu-id="14586-104">示例</span><span class="sxs-lookup"><span data-stu-id="14586-104">Example</span></span>

<span data-ttu-id="14586-105">在本示例中，`OleDbConnection` 对象用于连接到数据源，该数据源是在连接字符串中指定的 `Access MDB` 文件。</span><span class="sxs-lookup"><span data-stu-id="14586-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="14586-106">建立连接后，会创建一个 `OleDbDataAdapter` 对象。</span><span class="sxs-lookup"><span data-stu-id="14586-106">After the connection is established, an `OleDbDataAdapter` object is created.</span></span> <span data-ttu-id="14586-107">`OleDbDataAdapter`对象执行 select 结构化查询语言 (SQL) 语句以从数据库中检索记录集。</span><span class="sxs-lookup"><span data-stu-id="14586-107">The `OleDbDataAdapter` object executes a select Structured Query Language (SQL) statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="14586-108">通过调用的方法，将 SQL 命令中的结果存储在的中 `DataTable` `DataSet` `Fill` `OleDbDataAdapter` 。</span><span class="sxs-lookup"><span data-stu-id="14586-108">The results from the SQL command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="14586-109">本示例中，`DataTable` 命名为 `BookTable`。</span><span class="sxs-lookup"><span data-stu-id="14586-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="14586-110">然后，该示例将 <xref:System.Windows.FrameworkElement.DataContext%2A> 的属性设置 <xref:System.Windows.Controls.ListBox> 为 `DataSet` 对象。</span><span class="sxs-lookup"><span data-stu-id="14586-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

<span data-ttu-id="14586-111">然后，可以将的 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 属性绑定 <xref:System.Windows.Controls.ListBox> 到 `BookTable` `DataSet` ：</span><span class="sxs-lookup"><span data-stu-id="14586-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

<span data-ttu-id="14586-112">`BookItemTemplate`<xref:System.Windows.DataTemplate>定义数据显示方式的：</span><span class="sxs-lookup"><span data-stu-id="14586-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

<span data-ttu-id="14586-113">`IntColorConverter` 将 `int` 转换为颜色。</span><span class="sxs-lookup"><span data-stu-id="14586-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="14586-114">使用此转换器时， <xref:System.Windows.Controls.TextBlock.Background%2A> 如果的值小于350，则第三个颜色 <xref:System.Windows.Controls.TextBlock> 显示 `NumPages` 为绿色; 否则为红色。</span><span class="sxs-lookup"><span data-stu-id="14586-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="14586-115">此处未显示此转换器的实现。</span><span class="sxs-lookup"><span data-stu-id="14586-115">The implementation of the converter is not shown here.</span></span>

## <a name="see-also"></a><span data-ttu-id="14586-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14586-116">See also</span></span>

- <xref:System.Windows.Data.BindingListCollectionView>
- [<span data-ttu-id="14586-117">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="14586-117">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="14586-118">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="14586-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
