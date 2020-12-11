---
title: 如何：在 TreeView 中查找 TreeViewItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: ad72c7a7fb11dfe605db4119dde831b47dd7c5a4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971045"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a><span data-ttu-id="20164-102">如何：在 TreeView 中查找 TreeViewItem</span><span class="sxs-lookup"><span data-stu-id="20164-102">How to: Find a TreeViewItem in a TreeView</span></span>
<span data-ttu-id="20164-103"><xref:System.Windows.Controls.TreeView>控件提供了一种简便的方法来显示分层数据。</span><span class="sxs-lookup"><span data-stu-id="20164-103">The <xref:System.Windows.Controls.TreeView> control provides a convenient way to display hierarchical data.</span></span> <span data-ttu-id="20164-104">如果 <xref:System.Windows.Controls.TreeView> 将绑定到数据源，则 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 属性提供了一种方便的方法来快速检索所选的数据对象。</span><span class="sxs-lookup"><span data-stu-id="20164-104">If your <xref:System.Windows.Controls.TreeView> is bound to a data source, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property provides a convenient way for you to quickly retrieve the selected data object.</span></span> <span data-ttu-id="20164-105">通常情况下，最好使用基础数据对象，但有时你可能需要以编程方式操作包含的数据 <xref:System.Windows.Controls.TreeViewItem> 。</span><span class="sxs-lookup"><span data-stu-id="20164-105">It is typically best to work with the underlying data object, but sometimes you may need to programmatically manipulate the data's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="20164-106">例如，你可能需要以编程方式展开 <xref:System.Windows.Controls.TreeViewItem> ，或在中选择其他项 <xref:System.Windows.Controls.TreeView> 。</span><span class="sxs-lookup"><span data-stu-id="20164-106">For example, you may need to programmatically expand the <xref:System.Windows.Controls.TreeViewItem>, or select a different item in the <xref:System.Windows.Controls.TreeView>.</span></span>  
  
 <span data-ttu-id="20164-107">若要查找 <xref:System.Windows.Controls.TreeViewItem> 包含特定数据对象的，必须遍历的每个级别 <xref:System.Windows.Controls.TreeView> 。</span><span class="sxs-lookup"><span data-stu-id="20164-107">To find a <xref:System.Windows.Controls.TreeViewItem> that contains a specific data object, you must traverse each level of the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="20164-108">还可以对中的项进行 <xref:System.Windows.Controls.TreeView> 虚拟化以提高性能。</span><span class="sxs-lookup"><span data-stu-id="20164-108">The items in a <xref:System.Windows.Controls.TreeView> can also be virtualized to improve performance.</span></span> <span data-ttu-id="20164-109">如果项可能虚拟化，还必须实现， <xref:System.Windows.Controls.TreeViewItem> 以检查其是否包含数据对象。</span><span class="sxs-lookup"><span data-stu-id="20164-109">In the case where items might be virtualized, you also must realize a <xref:System.Windows.Controls.TreeViewItem> to check whether it contains the data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20164-110">示例</span><span class="sxs-lookup"><span data-stu-id="20164-110">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="20164-111">描述</span><span class="sxs-lookup"><span data-stu-id="20164-111">Description</span></span>  
 <span data-ttu-id="20164-112">下面的示例在 <xref:System.Windows.Controls.TreeView> 中搜索特定对象，并返回包含的对象 <xref:System.Windows.Controls.TreeViewItem> 。</span><span class="sxs-lookup"><span data-stu-id="20164-112">The following example searches a <xref:System.Windows.Controls.TreeView> for a specific object and returns the object's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="20164-113">该示例确保每个 <xref:System.Windows.Controls.TreeViewItem> 实例化后，才能搜索其子项。</span><span class="sxs-lookup"><span data-stu-id="20164-113">The example ensures that each <xref:System.Windows.Controls.TreeViewItem> is instantiated so that its child items can be searched.</span></span> <span data-ttu-id="20164-114">此示例也适用于不 <xref:System.Windows.Controls.TreeView> 使用虚拟化项的情况。</span><span class="sxs-lookup"><span data-stu-id="20164-114">This example also works if the <xref:System.Windows.Controls.TreeView> does not use virtualized items.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20164-115">下面的示例适用于任何 <xref:System.Windows.Controls.TreeView> ，而不考虑基础数据模型，并在每次 <xref:System.Windows.Controls.TreeViewItem> 找到该对象之前搜索。</span><span class="sxs-lookup"><span data-stu-id="20164-115">The following example works for any <xref:System.Windows.Controls.TreeView>, regardless of the underlying data model, and searches every <xref:System.Windows.Controls.TreeViewItem> until the object is found.</span></span> <span data-ttu-id="20164-116">性能更好的另一种方法是，在数据模型中搜索指定的对象，记录其在数据层次结构中的位置，然后在中查找相应的 <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.TreeView> 。</span><span class="sxs-lookup"><span data-stu-id="20164-116">Another technique that has better performance is to search the data model for the specified object, keep track of its location within the data hierarchy, and then find the corresponding <xref:System.Windows.Controls.TreeViewItem> in the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="20164-117">但是，具有更好性能的技术需要了解数据模型，并且不能对任何给定的进行通用化 <xref:System.Windows.Controls.TreeView> 。</span><span class="sxs-lookup"><span data-stu-id="20164-117">However, the technique that has better performance requires knowledge of the data model and cannot be generalized for any given <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="20164-118">代码</span><span class="sxs-lookup"><span data-stu-id="20164-118">Code</span></span>  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 <span data-ttu-id="20164-119">前面的代码依赖于 <xref:System.Windows.Controls.VirtualizingStackPanel> 公开一个名为的方法的自定义 `BringIntoView` 。</span><span class="sxs-lookup"><span data-stu-id="20164-119">The previous code relies on a custom <xref:System.Windows.Controls.VirtualizingStackPanel> that exposes a method named `BringIntoView`.</span></span> <span data-ttu-id="20164-120">下面的代码定义了自定义 <xref:System.Windows.Controls.VirtualizingStackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="20164-120">The following code defines the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 <span data-ttu-id="20164-121">下面的 XAML 演示如何创建 <xref:System.Windows.Controls.TreeView> 使用自定义的 <xref:System.Windows.Controls.VirtualizingStackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="20164-121">The following XAML shows how to create a <xref:System.Windows.Controls.TreeView> that uses the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="20164-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20164-122">See also</span></span>

- [<span data-ttu-id="20164-123">提升 TreeView 的性能</span><span class="sxs-lookup"><span data-stu-id="20164-123">Improve the Performance of a TreeView</span></span>](how-to-improve-the-performance-of-a-treeview.md)
