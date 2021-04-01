---
title: GridView 列标题的样式和模板概述
ms.date: 03/30/2017
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
ms.openlocfilehash: 83643d8acea706bad439683702e4228d240b97bc
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971048"
---
# <a name="gridview-column-header-styles-and-templates-overview"></a>GridView 列标题的样式和模板概述
本概述讨论了用于在控件的视图模式中自定义列标题的属性的优先级顺序 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView> 。  
  
## <a name="customizing-a-column-header-in-a-gridview"></a>自定义 GridView 中的列标题  
 定义中的列标题的内容、布局和样式的属性 <xref:System.Windows.Controls.GridView> 可在许多相关类中找到。 其中某些属性的功能相似或相同。  
  
 下表中的行显示执行相同功能的属性组。 您可以使用这些属性自定义中的列标题 <xref:System.Windows.Controls.GridView> 。 相关属性的优先级顺序是从右到左，其中最右边的列中的属性具有最高优先级。 例如，如果在 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 对象上设置了 <xref:System.Windows.Controls.GridViewColumnHeader> 并且在 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> 关联的上设置了 <xref:System.Windows.Controls.GridViewColumn> ，则 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 优先。 在这种情况下， <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> 不起作用。  
  
 **GridView 列标题的相关属性**  
  
|||||  
|-|-|-|-|  
|**类**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**上下文菜单属性**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|不适用|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**ToolTip**<br /><br /> **属性**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|不适用|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**标题模板**<br /><br /> **属性**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A><sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A><sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A><sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**样式属性**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>对于 **标头模板属性**，如果同时设置模板和模板选择器属性，则模板属性优先。 例如，如果设置了 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 和 <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> 属性，则 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 属性优先。  
  
## <a name="see-also"></a>请参阅

- [操作指南主题](listview-how-to-topics.md)
- [ListView 概述](listview-overview.md)
- [GridView 概述](gridview-overview.md)
