---
title: 如何：创建简单或复杂的 TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 7edb4933ebcc0f0d2cb02754238c2342ee9dd4a2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973720"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a><span data-ttu-id="8f46d-102">如何：创建简单或复杂的 TreeView</span><span class="sxs-lookup"><span data-stu-id="8f46d-102">How to: Create Simple or Complex TreeViews</span></span>
<span data-ttu-id="8f46d-103">此示例演示如何创建简单或复杂的 <xref:System.Windows.Controls.TreeView> 控件。</span><span class="sxs-lookup"><span data-stu-id="8f46d-103">This example shows how to create simple or complex <xref:System.Windows.Controls.TreeView> controls.</span></span>  
  
 <span data-ttu-id="8f46d-104">包含 <xref:System.Windows.Controls.TreeView> 控件的层次结构 <xref:System.Windows.Controls.TreeViewItem> ，这些控件可以包含简单的文本字符串和更复杂的内容，例如 <xref:System.Windows.Controls.Button> 控件或 <xref:System.Windows.Controls.StackPanel> 具有嵌入内容的。</span><span class="sxs-lookup"><span data-stu-id="8f46d-104">A <xref:System.Windows.Controls.TreeView> consists of a hierarchy of <xref:System.Windows.Controls.TreeViewItem> controls, which can contain simple text strings and also more complex content, such as <xref:System.Windows.Controls.Button> controls or a <xref:System.Windows.Controls.StackPanel> with embedded content.</span></span> <span data-ttu-id="8f46d-105">可以显式定义内容， <xref:System.Windows.Controls.TreeView> 也可以使用数据源提供内容。</span><span class="sxs-lookup"><span data-stu-id="8f46d-105">You can explicitly define the <xref:System.Windows.Controls.TreeView> content or a data source can provide the content.</span></span> <span data-ttu-id="8f46d-106">本主题提供这些概念的示例。</span><span class="sxs-lookup"><span data-stu-id="8f46d-106">This topic provides examples of these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f46d-107">示例</span><span class="sxs-lookup"><span data-stu-id="8f46d-107">Example</span></span>  
 <span data-ttu-id="8f46d-108"><xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>的属性 <xref:System.Windows.Controls.TreeViewItem> 包含 <xref:System.Windows.Controls.TreeView> 为该项显示的内容。</span><span class="sxs-lookup"><span data-stu-id="8f46d-108">The <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property of the <xref:System.Windows.Controls.TreeViewItem> contains the content that the <xref:System.Windows.Controls.TreeView> displays for that item.</span></span> <span data-ttu-id="8f46d-109"><xref:System.Windows.Controls.TreeViewItem>还可以将 <xref:System.Windows.Controls.TreeViewItem> 控件作为其子元素，并且可以通过使用属性来定义这些子元素 <xref:System.Windows.Controls.ItemsControl.Items%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8f46d-109">A <xref:System.Windows.Controls.TreeViewItem> can also have <xref:System.Windows.Controls.TreeViewItem> controls as its child elements and you can define these child elements by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="8f46d-110">下面的示例演示如何 <xref:System.Windows.Controls.TreeViewItem> 通过将 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 属性设置为文本字符串来显式定义内容。</span><span class="sxs-lookup"><span data-stu-id="8f46d-110">The following example shows how to explicitly define <xref:System.Windows.Controls.TreeViewItem> content by setting the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property to a text string.</span></span>  
  
 [!code-xaml[TreeViewSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="8f46d-111">下面的示例演示如何通过定义为控件定义的子元素 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.ItemsControl.Items%2A> <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="8f46d-111">The following example show how to define child elements of a <xref:System.Windows.Controls.TreeViewItem> by defining <xref:System.Windows.Controls.ItemsControl.Items%2A> that are <xref:System.Windows.Controls.Button> controls.</span></span>  
  
 [!code-xaml[TreeViewSimple#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 <span data-ttu-id="8f46d-112">下面的示例演示如何创建， <xref:System.Windows.Controls.TreeView> 其中 <xref:System.Windows.Data.XmlDataProvider> 提供 <xref:System.Windows.Controls.TreeViewItem> 内容并 <xref:System.Windows.HierarchicalDataTemplate> 定义内容的外观。</span><span class="sxs-lookup"><span data-stu-id="8f46d-112">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where an <xref:System.Windows.Data.XmlDataProvider> provides <xref:System.Windows.Controls.TreeViewItem> content and a <xref:System.Windows.HierarchicalDataTemplate> defines the appearance of the content.</span></span>  
  
 [!code-xaml[TreeViewSimple#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 <span data-ttu-id="8f46d-113">下面的示例演示如何创建一个 <xref:System.Windows.Controls.TreeView> 内容，其中 <xref:System.Windows.Controls.TreeViewItem> 包含 <xref:System.Windows.Controls.DockPanel> 具有嵌入内容的控件。</span><span class="sxs-lookup"><span data-stu-id="8f46d-113">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where the <xref:System.Windows.Controls.TreeViewItem> content contains <xref:System.Windows.Controls.DockPanel> controls that have embedded content.</span></span>  
  
 [!code-xaml[TreeViewSimple#9](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a><span data-ttu-id="8f46d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f46d-114">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="8f46d-115">TreeView 概述</span><span class="sxs-lookup"><span data-stu-id="8f46d-115">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="8f46d-116">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="8f46d-116">How-to Topics</span></span>](treeview-how-to-topics.md)
