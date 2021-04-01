---
title: 如何：在数据集合视图中的对象之间导航
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: dc8b1e0dec0f99c3537587fe60cbecf165047f44
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971495"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>如何：在数据集合视图中的对象之间导航
视图允许以不同的方式查看相同的数据集合，具体取决于排序、筛选或分组。 视图还提供当前记录指针概念并启用移动指针。 此示例演示如何获取当前对象，以及如何使用类中提供的功能在数据集合中的对象之间进行导航 <xref:System.Windows.Data.CollectionView> 。  
  
## <a name="example"></a>示例  
 在此示例中， `myCollectionView` 是一个 <xref:System.Windows.Data.CollectionView> 对象，该对象是绑定集合上的视图。  
  
 在下面的示例中， `OnButton` 是 `Previous` 应用程序中的和按钮的事件处理程序 `Next` ，这是允许用户导航数据集合的按钮。 请注意， <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> 和 <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> 属性报告当前记录指针是否分别到达列表的开头和末尾，以便 <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> 可以适当地调用和。  
  
 <xref:System.Windows.Data.CollectionView.CurrentItem%2A>视图的属性被强制转换为 `Order` ，以返回集合中的当前订单项。  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>请参阅

- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [在视图中对数据进行排序](how-to-sort-data-in-a-view.md)
- [筛选视图中的数据](how-to-filter-data-in-a-view.md)
- [在 XAML 中使用视图对数据进行排序和分组](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [操作指南主题](data-binding-how-to-topics.md)
