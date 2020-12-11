---
title: 如何：使用 GridSplitter 调整行的大小
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: 6760a7a691af4f666294556cae3bc95a4299730a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972933"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a><span data-ttu-id="3bfb0-102">如何：使用 GridSplitter 调整行的大小</span><span class="sxs-lookup"><span data-stu-id="3bfb0-102">How to: Resize Rows with a GridSplitter</span></span>
<span data-ttu-id="3bfb0-103">此示例演示如何使用水平在 <xref:System.Windows.Controls.GridSplitter> 中的两行之间重新分布空间， <xref:System.Windows.Controls.Grid> 而无需更改的尺寸 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-103">This example shows how to use a horizontal <xref:System.Windows.Controls.GridSplitter> to redistribute the space between two rows in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bfb0-104">示例</span><span class="sxs-lookup"><span data-stu-id="3bfb0-104">Example</span></span>  
 <span data-ttu-id="3bfb0-105">**如何创建覆盖行边缘的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="3bfb0-105">**How to create a GridSplitter that overlays the edge of a row**</span></span>  
  
 <span data-ttu-id="3bfb0-106">若要指定在 <xref:System.Windows.Controls.GridSplitter> 中调整相邻行的大小 <xref:System.Windows.Controls.Grid> ，请将 <xref:System.Windows.Controls.Grid.Row%2A> 附加属性设置为要重设大小的行之一。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="3bfb0-107">如果 <xref:System.Windows.Controls.Grid> 有多个列，请设置 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 附加属性来指定列数。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-107">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to specify the number of columns.</span></span> <span data-ttu-id="3bfb0-108">然后，将设置 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 为 <xref:System.Windows.VerticalAlignment.Top> 或 <xref:System.Windows.VerticalAlignment.Bottom> (您设置的对齐方式取决于要调整其大小的两行) 。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-108">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Top> or <xref:System.Windows.VerticalAlignment.Bottom> (which alignment you set depends on which two rows you want to resize).</span></span> <span data-ttu-id="3bfb0-109">最后，将 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性设置为 <xref:System.Windows.HorizontalAlignment.Stretch> 。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-109">Finally, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>.</span></span>  
  
 <span data-ttu-id="3bfb0-110">下面的示例演示如何定义用于 <xref:System.Windows.Controls.GridSplitter> 调整相邻行大小的水平。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-110">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <span data-ttu-id="3bfb0-111"><xref:System.Windows.Controls.GridSplitter>不占用自己的行的不会被中的其他控件遮盖 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-111">A <xref:System.Windows.Controls.GridSplitter> that does not occupy its own row may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="3bfb0-112">有关如何避免此问题的详细信息，请参阅[确保 GridSplitter 可见](how-to-make-sure-that-a-gridsplitter-is-visible.md)。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-112">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="3bfb0-113">**如何创建占据一行的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="3bfb0-113">**How to create a GridSplitter that occupies a row**</span></span>  
  
 <span data-ttu-id="3bfb0-114">若要指定 <xref:System.Windows.Controls.GridSplitter> 在中占据行的 <xref:System.Windows.Controls.Grid> ，请将 <xref:System.Windows.Controls.Grid.Row%2A> 附加属性设置为要重设大小的行之一。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-114">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a row in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="3bfb0-115">如果 <xref:System.Windows.Controls.Grid> 有多个列，请将 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 附加属性设置为列数。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-115">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to the number of columns.</span></span> <span data-ttu-id="3bfb0-116">然后，将设置 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 为 <xref:System.Windows.VerticalAlignment.Center> ，将 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性设置为 <xref:System.Windows.HorizontalAlignment.Stretch> ，并将 <xref:System.Windows.Controls.RowDefinition.Height%2A> 包含的行的设置为 <xref:System.Windows.Controls.GridSplitter> <xref:System.Windows.GridLength.Auto%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-116">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>, and set the <xref:System.Windows.Controls.RowDefinition.Height%2A> of the row that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="3bfb0-117">下面的示例演示如何定义一个 <xref:System.Windows.Controls.GridSplitter> 占据行并调整其两侧行的大小的水平。</span><span class="sxs-lookup"><span data-stu-id="3bfb0-117">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that occupies a row and resizes the rows on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="3bfb0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bfb0-118">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="3bfb0-119">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="3bfb0-119">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
