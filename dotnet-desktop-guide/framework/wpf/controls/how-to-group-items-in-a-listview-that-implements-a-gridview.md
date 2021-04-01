---
title: 如何：对实现 GridView 的 ListView 中的项进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: b3dd6891976a942b299c87fca25e430e9ee59a51
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971035"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a>如何：对实现 GridView 的 ListView 中的项进行分组
此示例演示如何在 <xref:System.Windows.Controls.GridView> 控件的视图模式下显示项组 <xref:System.Windows.Controls.ListView> 。  
  
## <a name="example"></a>示例  
 若要在中显示项组 <xref:System.Windows.Controls.ListView> ，请定义 <xref:System.Windows.Data.CollectionViewSource> 。 下面的示例演示了 <xref:System.Windows.Data.CollectionViewSource> 根据数据字段的值对数据项进行分组的 `Catalog` 。  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 下面的示例将的设置为 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListView> <xref:System.Windows.Data.CollectionViewSource> 上一个示例所定义的。 该示例还定义一个 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> 实现控件的 <xref:System.Windows.Controls.Expander> 。  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [操作指南主题](listview-how-to-topics.md)
- [ListView 概述](listview-overview.md)
- [GridView 概述](gridview-overview.md)
