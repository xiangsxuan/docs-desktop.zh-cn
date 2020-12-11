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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973236"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="49ed2-102">如何：在视图中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="49ed2-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="49ed2-103">此示例说明如何在视图中对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="49ed2-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49ed2-104">示例</span><span class="sxs-lookup"><span data-stu-id="49ed2-104">Example</span></span>  
 <span data-ttu-id="49ed2-105">下面的示例创建一个简单 <xref:System.Windows.Controls.ListBox> 的和一个 <xref:System.Windows.Controls.Button> ：</span><span class="sxs-lookup"><span data-stu-id="49ed2-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="49ed2-106"><xref:System.Windows.Controls.Primitives.ButtonBase.Click>按钮的事件处理程序包含按降序对中的项进行排序的逻辑 <xref:System.Windows.Controls.ListBox> 。</span><span class="sxs-lookup"><span data-stu-id="49ed2-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="49ed2-107">你可以这样做，因为以 <xref:System.Windows.Controls.ListBox> 这种方式添加项会将项添加到的 <xref:System.Windows.Controls.ItemCollection> <xref:System.Windows.Controls.ListBox> ，并 <xref:System.Windows.Controls.ItemCollection> 从 <xref:System.Windows.Data.CollectionView> 类派生。</span><span class="sxs-lookup"><span data-stu-id="49ed2-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="49ed2-108">如果使用属性将绑定 <xref:System.Windows.Controls.ListBox> 到集合 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> ，则可以使用相同的方法进行排序。</span><span class="sxs-lookup"><span data-stu-id="49ed2-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="49ed2-109">只要具有对视图对象的引用，就可以使用相同的方法对其他集合视图的内容进行排序。</span><span class="sxs-lookup"><span data-stu-id="49ed2-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="49ed2-110">有关如何获取视图的示例，请参阅 [获取数据集合的默认视图](how-to-get-the-default-view-of-a-data-collection.md)。</span><span class="sxs-lookup"><span data-stu-id="49ed2-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="49ed2-111">若要查看其他示例，请参阅 [在单击标题时对 GridView 列进行排序](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)。</span><span class="sxs-lookup"><span data-stu-id="49ed2-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="49ed2-112">有关视图的详细信息，请参阅绑定到 [数据绑定](/dotnet/desktop-wpf/data/data-binding-overview)中的集合概述。</span><span class="sxs-lookup"><span data-stu-id="49ed2-112">For more information about views, see Binding to Collections in [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>  
  
 <span data-ttu-id="49ed2-113">有关如何在中应用排序逻辑的示例 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，请参阅 [在 XAML 中使用视图对数据进行排序和分组](how-to-sort-and-group-data-using-a-view-in-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="49ed2-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49ed2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49ed2-114">See also</span></span>

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [<span data-ttu-id="49ed2-115">在标题获得单击时对 GridView 列进行排序</span><span class="sxs-lookup"><span data-stu-id="49ed2-115">Sort a GridView Column When a Header Is Clicked</span></span>](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="49ed2-116">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="49ed2-116">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="49ed2-117">筛选视图中的数据</span><span class="sxs-lookup"><span data-stu-id="49ed2-117">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="49ed2-118">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="49ed2-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
