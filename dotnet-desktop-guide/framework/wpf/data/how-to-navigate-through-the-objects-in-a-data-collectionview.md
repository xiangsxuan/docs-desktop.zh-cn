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
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="c7f6d-102">如何：在数据集合视图中的对象之间导航</span><span class="sxs-lookup"><span data-stu-id="c7f6d-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="c7f6d-103">视图允许以不同的方式查看相同的数据集合，具体取决于排序、筛选或分组。</span><span class="sxs-lookup"><span data-stu-id="c7f6d-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="c7f6d-104">视图还提供当前记录指针概念并启用移动指针。</span><span class="sxs-lookup"><span data-stu-id="c7f6d-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="c7f6d-105">此示例演示如何获取当前对象，以及如何使用类中提供的功能在数据集合中的对象之间进行导航 <xref:System.Windows.Data.CollectionView> 。</span><span class="sxs-lookup"><span data-stu-id="c7f6d-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7f6d-106">示例</span><span class="sxs-lookup"><span data-stu-id="c7f6d-106">Example</span></span>  
 <span data-ttu-id="c7f6d-107">在此示例中， `myCollectionView` 是一个 <xref:System.Windows.Data.CollectionView> 对象，该对象是绑定集合上的视图。</span><span class="sxs-lookup"><span data-stu-id="c7f6d-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="c7f6d-108">在下面的示例中， `OnButton` 是 `Previous` 应用程序中的和按钮的事件处理程序 `Next` ，这是允许用户导航数据集合的按钮。</span><span class="sxs-lookup"><span data-stu-id="c7f6d-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="c7f6d-109">请注意， <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> 和 <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> 属性报告当前记录指针是否分别到达列表的开头和末尾，以便 <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> 可以适当地调用和。</span><span class="sxs-lookup"><span data-stu-id="c7f6d-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="c7f6d-110"><xref:System.Windows.Data.CollectionView.CurrentItem%2A>视图的属性被强制转换为 `Order` ，以返回集合中的当前订单项。</span><span class="sxs-lookup"><span data-stu-id="c7f6d-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="c7f6d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7f6d-111">See also</span></span>

- [<span data-ttu-id="c7f6d-112">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="c7f6d-112">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="c7f6d-113">在视图中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="c7f6d-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="c7f6d-114">筛选视图中的数据</span><span class="sxs-lookup"><span data-stu-id="c7f6d-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="c7f6d-115">在 XAML 中使用视图对数据进行排序和分组</span><span class="sxs-lookup"><span data-stu-id="c7f6d-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="c7f6d-116">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="c7f6d-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
