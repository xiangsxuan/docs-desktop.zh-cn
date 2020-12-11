---
title: 如何：使用 GridSplitter 调整列的大小
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: f743e9ccf8a984a646a4b8f05ee99162e5bc73ad
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972935"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a><span data-ttu-id="4ab92-102">如何：使用 GridSplitter 调整列的大小</span><span class="sxs-lookup"><span data-stu-id="4ab92-102">How to: Resize Columns with a GridSplitter</span></span>
<span data-ttu-id="4ab92-103">此示例演示如何创建一个垂直，以便在 <xref:System.Windows.Controls.GridSplitter> 中重新分布两列之间的空间， <xref:System.Windows.Controls.Grid> 而无需更改的尺寸 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="4ab92-103">This example shows how to create a vertical <xref:System.Windows.Controls.GridSplitter> in order to redistribute the space between two columns in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ab92-104">示例</span><span class="sxs-lookup"><span data-stu-id="4ab92-104">Example</span></span>  
 <span data-ttu-id="4ab92-105">**如何创建覆盖列边缘的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="4ab92-105">**How to create a GridSplitter that overlays the edge of a column**</span></span>  
  
 <span data-ttu-id="4ab92-106">若要指定在 <xref:System.Windows.Controls.GridSplitter> 中调整相邻列的大小 <xref:System.Windows.Controls.Grid> ，请将 <xref:System.Windows.Controls.Grid.Column%2A> 附加属性设置为要重设大小的列之一。</span><span class="sxs-lookup"><span data-stu-id="4ab92-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent columns in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="4ab92-107">如果 <xref:System.Windows.Controls.Grid> 有多个行，请将 <xref:System.Windows.Controls.Grid.RowSpan%2A> 附加属性设置为行数。</span><span class="sxs-lookup"><span data-stu-id="4ab92-107">If your <xref:System.Windows.Controls.Grid> has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="4ab92-108">然后将 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性设置为 <xref:System.Windows.HorizontalAlignment.Left> 或 <xref:System.Windows.HorizontalAlignment.Right> (您设置的对齐方式取决于要重设其大小) 的两个列。</span><span class="sxs-lookup"><span data-stu-id="4ab92-108">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Left> or <xref:System.Windows.HorizontalAlignment.Right> (which alignment you set depends on which two columns you want to resize).</span></span> <span data-ttu-id="4ab92-109">最后，将 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 属性设置为 <xref:System.Windows.VerticalAlignment.Stretch> 。</span><span class="sxs-lookup"><span data-stu-id="4ab92-109">Finally, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <span data-ttu-id="4ab92-110"><xref:System.Windows.Controls.GridSplitter>不具有自己的列的可能会被中的其他控件遮盖 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="4ab92-110">A <xref:System.Windows.Controls.GridSplitter> that does not have its own column may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="4ab92-111">有关如何避免此问题的详细信息，请参阅[确保 GridSplitter 可见](how-to-make-sure-that-a-gridsplitter-is-visible.md)。</span><span class="sxs-lookup"><span data-stu-id="4ab92-111">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="4ab92-112">**如何创建占据一列的 GridSplitter**</span><span class="sxs-lookup"><span data-stu-id="4ab92-112">**How to create a GridSplitter that occupies a column**</span></span>  
  
 <span data-ttu-id="4ab92-113">若要指定 <xref:System.Windows.Controls.GridSplitter> 在中占据列的 <xref:System.Windows.Controls.Grid> ，请将 <xref:System.Windows.Controls.Grid.Column%2A> 附加属性设置为要重设大小的列之一。</span><span class="sxs-lookup"><span data-stu-id="4ab92-113">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a column in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="4ab92-114">如果网格具有多行，请将 <xref:System.Windows.Controls.Grid.RowSpan%2A> 附加属性设置为行数。</span><span class="sxs-lookup"><span data-stu-id="4ab92-114">If your Grid has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="4ab92-115">然后，将设置 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 为 <xref:System.Windows.HorizontalAlignment.Center> ，将 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 属性设置为 <xref:System.Windows.VerticalAlignment.Stretch> ，并将 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 包含的列的设置为 <xref:System.Windows.Controls.GridSplitter> <xref:System.Windows.GridLength.Auto%2A> 。</span><span class="sxs-lookup"><span data-stu-id="4ab92-115">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> to <xref:System.Windows.HorizontalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>, and set the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the column that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="4ab92-116">下面的示例演示如何定义一个垂直 <xref:System.Windows.Controls.GridSplitter> ，它占用一列并调整其两侧的列的大小。</span><span class="sxs-lookup"><span data-stu-id="4ab92-116">The following example shows how to define a vertical <xref:System.Windows.Controls.GridSplitter> that occupies a column and resizes the columns on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="4ab92-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ab92-117">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="4ab92-118">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="4ab92-118">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
