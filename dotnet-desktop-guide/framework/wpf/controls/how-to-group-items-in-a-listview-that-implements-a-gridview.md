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
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="81a60-102">如何：对实现 GridView 的 ListView 中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="81a60-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="81a60-103">此示例演示如何在 <xref:System.Windows.Controls.GridView> 控件的视图模式下显示项组 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="81a60-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81a60-104">示例</span><span class="sxs-lookup"><span data-stu-id="81a60-104">Example</span></span>  
 <span data-ttu-id="81a60-105">若要在中显示项组 <xref:System.Windows.Controls.ListView> ，请定义 <xref:System.Windows.Data.CollectionViewSource> 。</span><span class="sxs-lookup"><span data-stu-id="81a60-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="81a60-106">下面的示例演示了 <xref:System.Windows.Data.CollectionViewSource> 根据数据字段的值对数据项进行分组的 `Catalog` 。</span><span class="sxs-lookup"><span data-stu-id="81a60-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="81a60-107">下面的示例将的设置为 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListView> <xref:System.Windows.Data.CollectionViewSource> 上一个示例所定义的。</span><span class="sxs-lookup"><span data-stu-id="81a60-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="81a60-108">该示例还定义一个 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> 实现控件的 <xref:System.Windows.Controls.Expander> 。</span><span class="sxs-lookup"><span data-stu-id="81a60-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="81a60-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="81a60-109">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="81a60-110">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="81a60-110">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="81a60-111">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="81a60-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="81a60-112">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="81a60-112">GridView Overview</span></span>](gridview-overview.md)
