---
title: 如何：在视图中对数据进行排序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 4ff90cc58cb3d7ceee0be2fd7f6ddaaa27df4cef
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973236"
---
# <a name="how-to-sort-data-in-a-view"></a>如何：在视图中对数据进行排序
此示例说明如何在视图中对数据进行排序。  
  
## <a name="example"></a>示例  
 下面的示例创建一个简单 <xref:System.Windows.Controls.ListBox> 的和一个 <xref:System.Windows.Controls.Button> ：  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <xref:System.Windows.Controls.Primitives.ButtonBase.Click>按钮的事件处理程序包含按降序对中的项进行排序的逻辑 <xref:System.Windows.Controls.ListBox> 。 你可以这样做，因为以 <xref:System.Windows.Controls.ListBox> 这种方式添加项会将项添加到的 <xref:System.Windows.Controls.ItemCollection> <xref:System.Windows.Controls.ListBox> ，并 <xref:System.Windows.Controls.ItemCollection> 从 <xref:System.Windows.Data.CollectionView> 类派生。 如果使用属性将绑定 <xref:System.Windows.Controls.ListBox> 到集合 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> ，则可以使用相同的方法进行排序。  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 只要具有对视图对象的引用，就可以使用相同的方法对其他集合视图的内容进行排序。 有关如何获取视图的示例，请参阅 [获取数据集合的默认视图](how-to-get-the-default-view-of-a-data-collection.md)。 若要查看其他示例，请参阅 [在单击标题时对 GridView 列进行排序](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)。 有关视图的详细信息，请参阅绑定到 [数据绑定](/dotnet/desktop-wpf/data/data-binding-overview)中的集合概述。  
  
 有关如何在中应用排序逻辑的示例 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，请参阅 [在 XAML 中使用视图对数据进行排序和分组](how-to-sort-and-group-data-using-a-view-in-xaml.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [在标题获得单击时对 GridView 列进行排序](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [筛选视图中的数据](how-to-filter-data-in-a-view.md)
- [操作指南主题](data-binding-how-to-topics.md)
