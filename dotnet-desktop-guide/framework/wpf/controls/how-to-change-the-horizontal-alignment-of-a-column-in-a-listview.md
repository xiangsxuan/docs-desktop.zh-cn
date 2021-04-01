---
title: 如何：更改 ListView 中列的水平对齐方式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: cdf479fc9f84f88fccc877e9fdf8ca56d53c1c4b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973372"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>如何：更改 ListView 中列的水平对齐方式
默认情况下，中每一列的内容 <xref:System.Windows.Controls.ListViewItem> 都为左对齐。 可以通过提供 <xref:System.Windows.DataTemplate> 并在 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 中的元素上设置属性，来更改每个列的对齐方式 <xref:System.Windows.DataTemplate> 。 本主题说明如何 <xref:System.Windows.Controls.ListView> 默认对齐其内容，以及如何更改中某一列的对齐方式 <xref:System.Windows.Controls.ListView> 。  
  
## <a name="example"></a>示例  
 在下面的示例中，和列中的数据 `Title` `ISBN` 是左对齐的。  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 若要更改列的对齐方式 `ISBN` ，需要指定 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 每个的属性 <xref:System.Windows.Controls.ListViewItem> 为 <xref:System.Windows.HorizontalAlignment.Stretch> ，以便每个中的元素都 <xref:System.Windows.Controls.ListViewItem> 可以跨每个列的整个宽度。 由于 <xref:System.Windows.Controls.ListView> 已绑定到数据源，因此需要创建设置的样式 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 。 接下来，您需要使用 <xref:System.Windows.DataTemplate> 来显示内容，而不是使用 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 属性。 若要显示 `ISBN` 每个模板的， <xref:System.Windows.DataTemplate> 可以只包含一个 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 将其属性设置为的 <xref:System.Windows.HorizontalAlignment.Right> 。  
  
 下面的示例定义了 <xref:System.Windows.DataTemplate> 使列右对齐所必需的样式， `ISBN` 并将更改 <xref:System.Windows.Controls.GridViewColumn> 为引用 <xref:System.Windows.DataTemplate> 。  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>请参阅

- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [数据模板化概述](../data/data-templating-overview.md)
- [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView 概述](listview-overview.md)
