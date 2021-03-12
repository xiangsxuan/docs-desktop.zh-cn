---
title: 如何：为 ListView 创建自定义视图模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 6c6c8475849354493330105e93316d6424ebe2f3
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604272"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="9dbb9-102">如何：为 ListView 创建自定义视图模式</span><span class="sxs-lookup"><span data-stu-id="9dbb9-102">How to: Create a custom view mode for a ListView</span></span>

<span data-ttu-id="9dbb9-103">此示例演示如何为控件创建自定义 <xref:System.Windows.Controls.ListView.View%2A> 模式 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dbb9-104">示例</span><span class="sxs-lookup"><span data-stu-id="9dbb9-104">Example</span></span>  
 <span data-ttu-id="9dbb9-105"><xref:System.Windows.Controls.ViewBase>为控件创建自定义视图时，必须使用类 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="9dbb9-106">下面的示例演示一个名为的视图模式 `PlainView` ，该类派生自 <xref:System.Windows.Controls.ViewBase> 类。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-106">The following example shows a view mode called `PlainView` that's derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="9dbb9-107">若要将样式应用于自定义视图，请使用 <xref:System.Windows.Style> 类。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="9dbb9-108">下面的示例定义 <xref:System.Windows.Style> `PlainView` 视图模式的。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="9dbb9-109">在上面的示例中，此样式设置为 <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> 为定义的属性的值 `PlainView` 。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that's defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="9dbb9-110">若要在自定义视图模式下定义数据布局，请定义一个 <xref:System.Windows.DataTemplate> 对象。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="9dbb9-111">下面的示例定义一个 <xref:System.Windows.DataTemplate> ，它可用于在 `PlainView` 视图模式下显示数据。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="9dbb9-112">下面的示例演示如何为 <xref:System.Windows.ResourceKey> `PlainView` 使用 <xref:System.Windows.DataTemplate> 上一示例中定义的的视图模式定义。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="9dbb9-113"><xref:System.Windows.Controls.ListView>如果将 <xref:System.Windows.Controls.ListView.View%2A> 属性设置为资源键，则控件可以使用自定义视图。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="9dbb9-114">下面的示例演示如何将指定 `PlainView` 为的查看模式 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="9dbb9-115">有关完整示例，请参阅 [具有多个视图的 listview (c # ) ](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) 或 [包含多个视图的 listview (Visual Basic) ](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)。</span><span class="sxs-lookup"><span data-stu-id="9dbb9-115">For the complete sample, see [ListView with Multiple Views (C#)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views (Visual Basic)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbb9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9dbb9-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="9dbb9-117">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="9dbb9-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="9dbb9-118">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="9dbb9-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="9dbb9-119">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="9dbb9-119">GridView Overview</span></span>](gridview-overview.md)
