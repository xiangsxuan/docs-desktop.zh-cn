---
title: 如何：使用 ScrollViewer 的内容滚动方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: ac186cc9da0648b714627e9b7d70b5e9bc7d840f
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664010"
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a><span data-ttu-id="44b3e-102">如何：使用 ScrollViewer 的内容滚动方法</span><span class="sxs-lookup"><span data-stu-id="44b3e-102">How to: Use the Content-Scrolling Methods of ScrollViewer</span></span>
<span data-ttu-id="44b3e-103">此示例演示如何使用元素的滚动方法 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="44b3e-103">This example shows how to use the scrolling methods of the <xref:System.Windows.Controls.ScrollViewer> element.</span></span> <span data-ttu-id="44b3e-104">这些方法在中按行或页的方式提供内容的增量滚动 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="44b3e-104">These methods provide incremental scrolling of content, either by line or by page, in a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44b3e-105">示例</span><span class="sxs-lookup"><span data-stu-id="44b3e-105">Example</span></span>  
 <span data-ttu-id="44b3e-106">下面的示例创建一个 <xref:System.Windows.Controls.ScrollViewer> 名为的 `sv1` ，它承载一个子 <xref:System.Windows.Controls.TextBlock> 元素。</span><span class="sxs-lookup"><span data-stu-id="44b3e-106">The following example creates a <xref:System.Windows.Controls.ScrollViewer> named `sv1`, which hosts a child <xref:System.Windows.Controls.TextBlock> element.</span></span> <span data-ttu-id="44b3e-107">因为大于 <xref:System.Windows.Controls.TextBlock> 父项 <xref:System.Windows.Controls.ScrollViewer> ，所以滚动条会出现以便启用滚动。</span><span class="sxs-lookup"><span data-stu-id="44b3e-107">Because the <xref:System.Windows.Controls.TextBlock> is larger than the parent <xref:System.Windows.Controls.ScrollViewer>, scroll bars appear in order to enable scrolling.</span></span> <span data-ttu-id="44b3e-108"><xref:System.Windows.Controls.Button> 表示各种滚动方法的元素停靠在单独的的左侧 <xref:System.Windows.Controls.StackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="44b3e-108"><xref:System.Windows.Controls.Button> elements that represent the various scrolling methods are docked on the left in a separate <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="44b3e-109">文件中的每个都 <xref:System.Windows.Controls.Button> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 调用相关的自定义方法，该方法控制中的滚动行为 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="44b3e-109">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file calls a related custom method that controls scrolling behavior in <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 [!code-xaml[ScrollViewerMethods#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="44b3e-110">下面的示例使用 <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> 和 <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="44b3e-110">The following example uses the <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> and <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> methods.</span></span>  
  
 [!code-csharp[ScrollViewerMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="44b3e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="44b3e-111">See also</span></span>

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.StackPanel>
