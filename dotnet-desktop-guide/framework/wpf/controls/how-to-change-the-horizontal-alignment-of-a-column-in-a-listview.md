---
title: 如何：更改 ListView 中列的水平对齐方式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: cdf479fc9f84f88fccc877e9fdf8ca56d53c1c4b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973372"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="064b4-102">如何：更改 ListView 中列的水平对齐方式</span><span class="sxs-lookup"><span data-stu-id="064b4-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="064b4-103">默认情况下，中每一列的内容 <xref:System.Windows.Controls.ListViewItem> 都为左对齐。</span><span class="sxs-lookup"><span data-stu-id="064b4-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="064b4-104">可以通过提供 <xref:System.Windows.DataTemplate> 并在 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 中的元素上设置属性，来更改每个列的对齐方式 <xref:System.Windows.DataTemplate> 。</span><span class="sxs-lookup"><span data-stu-id="064b4-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="064b4-105">本主题说明如何 <xref:System.Windows.Controls.ListView> 默认对齐其内容，以及如何更改中某一列的对齐方式 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="064b4-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="064b4-106">示例</span><span class="sxs-lookup"><span data-stu-id="064b4-106">Example</span></span>  
 <span data-ttu-id="064b4-107">在下面的示例中，和列中的数据 `Title` `ISBN` 是左对齐的。</span><span class="sxs-lookup"><span data-stu-id="064b4-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="064b4-108">若要更改列的对齐方式 `ISBN` ，需要指定 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 每个的属性 <xref:System.Windows.Controls.ListViewItem> 为 <xref:System.Windows.HorizontalAlignment.Stretch> ，以便每个中的元素都 <xref:System.Windows.Controls.ListViewItem> 可以跨每个列的整个宽度。</span><span class="sxs-lookup"><span data-stu-id="064b4-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="064b4-109">由于 <xref:System.Windows.Controls.ListView> 已绑定到数据源，因此需要创建设置的样式 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 。</span><span class="sxs-lookup"><span data-stu-id="064b4-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="064b4-110">接下来，您需要使用 <xref:System.Windows.DataTemplate> 来显示内容，而不是使用 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="064b4-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="064b4-111">若要显示 `ISBN` 每个模板的， <xref:System.Windows.DataTemplate> 可以只包含一个 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 将其属性设置为的 <xref:System.Windows.HorizontalAlignment.Right> 。</span><span class="sxs-lookup"><span data-stu-id="064b4-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="064b4-112">下面的示例定义了 <xref:System.Windows.DataTemplate> 使列右对齐所必需的样式， `ISBN` 并将更改 <xref:System.Windows.Controls.GridViewColumn> 为引用 <xref:System.Windows.DataTemplate> 。</span><span class="sxs-lookup"><span data-stu-id="064b4-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="064b4-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="064b4-113">See also</span></span>

- [<span data-ttu-id="064b4-114">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="064b4-114">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="064b4-115">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="064b4-115">Data Templating Overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="064b4-116">使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据</span><span class="sxs-lookup"><span data-stu-id="064b4-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="064b4-117">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="064b4-117">ListView Overview</span></span>](listview-overview.md)
