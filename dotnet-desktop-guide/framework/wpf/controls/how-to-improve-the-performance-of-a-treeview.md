---
title: 如何：提高 TreeView 的性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: de1b46da2a7c6c3db0c0c19cdbb654fcf2fbbd6c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973092"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="3012d-102">如何：提高 TreeView 的性能</span><span class="sxs-lookup"><span data-stu-id="3012d-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="3012d-103">如果 <xref:System.Windows.Controls.TreeView> 包含很多项，加载所需的时间可能会导致用户界面出现明显的延迟。</span><span class="sxs-lookup"><span data-stu-id="3012d-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="3012d-104">可以通过将 `VirtualizingStackPanel.IsVirtualizing` 附加属性设置为来缩短加载时间 `true` 。</span><span class="sxs-lookup"><span data-stu-id="3012d-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="3012d-105">当用户 <xref:System.Windows.Controls.TreeView> 使用鼠标轮滚动或拖动滚动条的滚动块时，UI 的响应速度也可能会很慢。</span><span class="sxs-lookup"><span data-stu-id="3012d-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="3012d-106"><xref:System.Windows.Controls.TreeView>通过将附加属性设置为，可以提高用户滚动时的性能 `VirtualizingStackPanel.VirtualizationMode` <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="3012d-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3012d-107">示例</span><span class="sxs-lookup"><span data-stu-id="3012d-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="3012d-108">描述</span><span class="sxs-lookup"><span data-stu-id="3012d-108">Description</span></span>  
<span data-ttu-id="3012d-109">下面的示例创建一个 <xref:System.Windows.Controls.TreeView> ，它将 `VirtualizingStackPanel.IsVirtualizing` 附加属性设置为 true，并将附加属性设置为以 `VirtualizingStackPanel.VirtualizationMode` <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 优化其性能。</span><span class="sxs-lookup"><span data-stu-id="3012d-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="3012d-110">代码</span><span class="sxs-lookup"><span data-stu-id="3012d-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="3012d-111">下面的示例显示了上一示例所使用的数据。</span><span class="sxs-lookup"><span data-stu-id="3012d-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="3012d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3012d-112">See also</span></span>

- [<span data-ttu-id="3012d-113">控件</span><span class="sxs-lookup"><span data-stu-id="3012d-113">Controls</span></span>](../advanced/optimizing-performance-controls.md)
