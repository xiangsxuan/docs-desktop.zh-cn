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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974046"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="16e19-102">如何：获取数据集合的默认视图</span><span class="sxs-lookup"><span data-stu-id="16e19-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="16e19-103">视图允许根据排序、筛选或分组条件以不同的方式查看相同的数据集合。</span><span class="sxs-lookup"><span data-stu-id="16e19-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="16e19-104">每个集合都有一个共享的默认视图，当绑定将集合指定为其源时，该视图将用作实际的绑定源。</span><span class="sxs-lookup"><span data-stu-id="16e19-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="16e19-105">此示例演示如何获取集合的默认视图。</span><span class="sxs-lookup"><span data-stu-id="16e19-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16e19-106">示例</span><span class="sxs-lookup"><span data-stu-id="16e19-106">Example</span></span>  
 <span data-ttu-id="16e19-107">若要创建视图，需要对集合的对象引用。</span><span class="sxs-lookup"><span data-stu-id="16e19-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="16e19-108">可以通过以下方式获取此数据对象：引用自己的代码隐藏对象、获取数据上下文、获取数据源的属性或获取绑定的属性。</span><span class="sxs-lookup"><span data-stu-id="16e19-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="16e19-109">此示例演示如何获取 <xref:System.Windows.FrameworkElement.DataContext%2A> 数据对象的，并使用该对象直接获取此集合的默认集合视图。</span><span class="sxs-lookup"><span data-stu-id="16e19-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="16e19-110">在此示例中，根元素是 <xref:System.Windows.Controls.StackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="16e19-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="16e19-111"><xref:System.Windows.FrameworkElement.DataContext%2A>设置为 *myDataSource*，这是指作为 <xref:System.Collections.ObjectModel.ObservableCollection%601> *顺序* 对象的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="16e19-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="16e19-112">或者，你可以使用类实例化并绑定到你自己的集合视图 <xref:System.Windows.Data.CollectionViewSource> 。</span><span class="sxs-lookup"><span data-stu-id="16e19-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="16e19-113">此集合视图仅由直接绑定到它的控件共享。</span><span class="sxs-lookup"><span data-stu-id="16e19-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="16e19-114">有关示例，请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)中的 "如何创建视图" 部分。</span><span class="sxs-lookup"><span data-stu-id="16e19-114">For an example, see the How to Create a View section in the [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>  
  
 <span data-ttu-id="16e19-115">有关集合视图提供的功能的示例，请参阅 [在视图中对数据进行排序](how-to-sort-data-in-a-view.md)、 [筛选视图中的数据](how-to-filter-data-in-a-view.md)，以及 [在数据 CollectionView 中的对象](how-to-navigate-through-the-objects-in-a-data-collectionview.md)之间进行导航。</span><span class="sxs-lookup"><span data-stu-id="16e19-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e19-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16e19-116">See also</span></span>

- [<span data-ttu-id="16e19-117">在 XAML 中使用视图对数据进行排序和分组</span><span class="sxs-lookup"><span data-stu-id="16e19-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="16e19-118">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="16e19-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
