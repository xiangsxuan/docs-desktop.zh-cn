---
title: 如何：绑定到 LINQ 查询的结果
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 47f39319f2d6a6c67361157afaceb6d605ce01d1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970486"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>如何：绑定到 LINQ 查询的结果

此示例演示如何运行 LINQ 查询并将其绑定到结果。

## <a name="example"></a>示例

下面的示例创建两个列表框。 第一个列表框包含三个列表项。

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

从第一个列表框中选择一项将调用以下事件处理程序。 在此示例中， `Tasks` 是对象的集合 `Task` 。 `Task`类具有一个名为的属性 `Priority` 。 此事件处理程序运行 LINQ 查询，该查询返回 `Task` 具有选定优先级值的对象的集合，然后将其设置为 <xref:System.Windows.FrameworkElement.DataContext%2A> ：

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

第二个列表框绑定到该集合，因为其 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 值设置为 `{Binding}` 。 因此，它会基于) 显示返回的集合 (`myTaskTemplate` <xref:System.Windows.DataTemplate> 。

## <a name="see-also"></a>请参阅

- [使数据可用于 XAML 中的绑定](how-to-make-data-available-for-binding-in-xaml.md)
- [绑定到集合并基于选择显示信息](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [WPF 版本 4.5 的新增功能](../getting-started/whats-new.md)
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
