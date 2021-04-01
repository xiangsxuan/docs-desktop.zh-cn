---
title: 如何：使用模板创建使用 GridView 的 ListView 的样式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
ms.openlocfilehash: 1caa652c4a2a3a7d0a8d40fe703df7a3e8038c9b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970488"
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="83825-102">如何：使用模板创建使用 GridView 的 ListView 的样式</span><span class="sxs-lookup"><span data-stu-id="83825-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="83825-103">此示例演示如何使用 <xref:System.Windows.DataTemplate> 和 <xref:System.Windows.Style> 对象来指定 <xref:System.Windows.Controls.ListView> 使用视图模式的控件的外观 <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="83825-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83825-104">示例</span><span class="sxs-lookup"><span data-stu-id="83825-104">Example</span></span>  
 <span data-ttu-id="83825-105">下面的示例演示了 <xref:System.Windows.Style> 和 <xref:System.Windows.DataTemplate> 对象，这些对象用于自定义的列标题的外观 <xref:System.Windows.Controls.GridViewColumn> 。</span><span class="sxs-lookup"><span data-stu-id="83825-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="83825-106">下面的示例演示如何使用 <xref:System.Windows.Style> 和 <xref:System.Windows.DataTemplate> 对象来设置的 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> 和 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> 属性 <xref:System.Windows.Controls.GridViewColumn> 。</span><span class="sxs-lookup"><span data-stu-id="83825-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="83825-107"><xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性定义列单元格的内容。</span><span class="sxs-lookup"><span data-stu-id="83825-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="83825-108"><xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>和 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> 只是几个可用于为控件自定义列标题外观的属性中的两个 <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="83825-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="83825-109">有关详细信息，请参阅 [GridView 列标题的样式和模板概述](gridview-column-header-styles-and-templates-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="83825-109">For more information, see [GridView Column Header Styles and Templates Overview](gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="83825-110">下面的示例演示如何定义 <xref:System.Windows.DataTemplate> 用于自定义中的单元格外观的 <xref:System.Windows.Controls.GridViewColumn> 。</span><span class="sxs-lookup"><span data-stu-id="83825-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="83825-111">下面的示例演示如何使用此 <xref:System.Windows.DataTemplate> 定义 <xref:System.Windows.Controls.GridViewColumn> 单元格的内容。</span><span class="sxs-lookup"><span data-stu-id="83825-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="83825-112">使用此模板而不是 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 前面示例中所示的属性 <xref:System.Windows.Controls.GridViewColumn> 。</span><span class="sxs-lookup"><span data-stu-id="83825-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="83825-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="83825-113">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="83825-114">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="83825-114">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="83825-115">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="83825-115">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="83825-116">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="83825-116">ListView Overview</span></span>](listview-overview.md)
