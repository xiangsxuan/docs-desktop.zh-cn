---
title: 如何：获取数据集合的默认视图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 17ec2a40bf2c274f50b39875a23541932438a317
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974046"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>如何：获取数据集合的默认视图
视图允许根据排序、筛选或分组条件以不同的方式查看相同的数据集合。 每个集合都有一个共享的默认视图，当绑定将集合指定为其源时，该视图将用作实际的绑定源。 此示例演示如何获取集合的默认视图。  
  
## <a name="example"></a>示例  
 若要创建视图，需要对集合的对象引用。 可以通过以下方式获取此数据对象：引用自己的代码隐藏对象、获取数据上下文、获取数据源的属性或获取绑定的属性。 此示例演示如何获取 <xref:System.Windows.FrameworkElement.DataContext%2A> 数据对象的，并使用该对象直接获取此集合的默认集合视图。  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 在此示例中，根元素是 <xref:System.Windows.Controls.StackPanel> 。 <xref:System.Windows.FrameworkElement.DataContext%2A>设置为 *myDataSource*，这是指作为 <xref:System.Collections.ObjectModel.ObservableCollection%601> *顺序* 对象的数据提供程序。  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 或者，你可以使用类实例化并绑定到你自己的集合视图 <xref:System.Windows.Data.CollectionViewSource> 。 此集合视图仅由直接绑定到它的控件共享。 有关示例，请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)中的 "如何创建视图" 部分。  
  
 有关集合视图提供的功能的示例，请参阅 [在视图中对数据进行排序](how-to-sort-data-in-a-view.md)、 [筛选视图中的数据](how-to-filter-data-in-a-view.md)，以及 [在数据 CollectionView 中的对象](how-to-navigate-through-the-objects-in-a-data-collectionview.md)之间进行导航。  
  
## <a name="see-also"></a>另请参阅

- [在 XAML 中使用视图对数据进行排序和分组](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [操作指南主题](data-binding-how-to-topics.md)
