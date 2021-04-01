---
title: 如何：使用模板创建使用 GridView 的 ListView 的样式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
ms.openlocfilehash: 1caa652c4a2a3a7d0a8d40fe703df7a3e8038c9b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970488"
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a>如何：使用模板创建使用 GridView 的 ListView 的样式
此示例演示如何使用 <xref:System.Windows.DataTemplate> 和 <xref:System.Windows.Style> 对象来指定 <xref:System.Windows.Controls.ListView> 使用视图模式的控件的外观 <xref:System.Windows.Controls.GridView> 。  
  
## <a name="example"></a>示例  
 下面的示例演示了 <xref:System.Windows.Style> 和 <xref:System.Windows.DataTemplate> 对象，这些对象用于自定义的列标题的外观 <xref:System.Windows.Controls.GridViewColumn> 。  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 下面的示例演示如何使用 <xref:System.Windows.Style> 和 <xref:System.Windows.DataTemplate> 对象来设置的 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> 和 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> 属性 <xref:System.Windows.Controls.GridViewColumn> 。 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性定义列单元格的内容。  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>和 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> 只是几个可用于为控件自定义列标题外观的属性中的两个 <xref:System.Windows.Controls.GridView> 。 有关详细信息，请参阅 [GridView 列标题的样式和模板概述](gridview-column-header-styles-and-templates-overview.md)。  
  
 下面的示例演示如何定义 <xref:System.Windows.DataTemplate> 用于自定义中的单元格外观的 <xref:System.Windows.Controls.GridViewColumn> 。  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 下面的示例演示如何使用此 <xref:System.Windows.DataTemplate> 定义 <xref:System.Windows.Controls.GridViewColumn> 单元格的内容。 使用此模板而不是 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 前面示例中所示的属性 <xref:System.Windows.Controls.GridViewColumn> 。  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [GridView 概述](gridview-overview.md)
- [操作指南主题](listview-how-to-topics.md)
- [ListView 概述](listview-overview.md)
