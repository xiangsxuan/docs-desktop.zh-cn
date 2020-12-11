---
title: 如何：筛选视图中的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: c015194609de507725a17fbe5d72e41d7027c68f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974050"
---
# <a name="how-to-filter-data-in-a-view"></a>如何：筛选视图中的数据
此示例演示如何在视图中筛选数据。  
  
## <a name="example"></a>示例  
 若要创建筛选器，请定义提供筛选逻辑的方法。 方法用作回调并接受类型的参数 `object` 。 下面的方法将返回 `Order` `filled` 属性设置为 "No" 的所有对象，并筛选出其余的对象。  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 然后，你可以应用筛选器，如以下示例中所示。 在此示例中， `myCollectionView` 是一个 <xref:System.Windows.Data.ListCollectionView> 对象。  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 若要撤消筛选，可以将 <xref:System.Windows.Data.CollectionView.Filter%2A> 属性设置为 `null` ：  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 有关如何创建或获取视图的信息，请参阅 [获取数据集合的默认视图](how-to-get-the-default-view-of-a-data-collection.md)。 有关完整示例，请参阅 [在视图示例中对项目进行排序和筛选](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter)。  
  
 如果视图对象来自 <xref:System.Windows.Data.CollectionViewSource> 对象，则可以通过设置事件的事件处理程序来应用筛选逻辑 <xref:System.Windows.Data.CollectionViewSource.Filter> 。 在下面的示例中， `listingDataView` 是的实例 <xref:System.Windows.Data.CollectionViewSource> 。  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 下面显示了示例 `ShowOnlyBargainsFilter` 筛选器事件处理程序的实现。 此事件处理程序使用 <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> 属性筛选出 `AuctionItem` `CurrentPrice` $25 或更高版本的对象。  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [在视图中对数据进行排序](how-to-sort-data-in-a-view.md)
- [操作指南主题](data-binding-how-to-topics.md)
