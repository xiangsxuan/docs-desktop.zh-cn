---
title: 如何：提高 ListBox 的滚动性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: a9d1ca1d8ac2ef830984408f3052eb0ed0987c5d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973093"
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="54192-102">如何：提高 ListBox 的滚动性能</span><span class="sxs-lookup"><span data-stu-id="54192-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="54192-103">如果 <xref:System.Windows.Controls.ListBox> 包含很多项，则当用户 <xref:System.Windows.Controls.ListBox> 使用鼠标滚轮滚动或拖动滚动条的滚动块时，用户界面响应可能会很慢。</span><span class="sxs-lookup"><span data-stu-id="54192-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="54192-104"><xref:System.Windows.Controls.ListBox>通过将附加属性设置为，可以提高用户滚动时的性能 `VirtualizingStackPanel.VirtualizationMode` <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="54192-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54192-105">示例</span><span class="sxs-lookup"><span data-stu-id="54192-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="54192-106">描述</span><span class="sxs-lookup"><span data-stu-id="54192-106">Description</span></span>  
<span data-ttu-id="54192-107">下面的示例创建一个 <xref:System.Windows.Controls.ListBox> ，并将 `VirtualizingStackPanel.VirtualizationMode` 附加属性设置为， <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 以在滚动过程中提高性能。</span><span class="sxs-lookup"><span data-stu-id="54192-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="54192-108">代码</span><span class="sxs-lookup"><span data-stu-id="54192-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="54192-109">下面的示例显示了上一示例所使用的数据。</span><span class="sxs-lookup"><span data-stu-id="54192-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
