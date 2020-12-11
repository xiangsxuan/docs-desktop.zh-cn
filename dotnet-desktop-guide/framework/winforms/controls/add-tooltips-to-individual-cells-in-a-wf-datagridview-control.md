---
title: 向 DataGridView 控件中的各个单元格添加工具提示
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970736"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="06dcc-102">如何：为 Windows 窗体 DataGridView 控件中的各个单元格添加工具提示</span><span class="sxs-lookup"><span data-stu-id="06dcc-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="06dcc-103">默认情况下，工具提示用于显示 <xref:System.Windows.Forms.DataGridView> 太小而无法显示其全部内容的单元格的值。</span><span class="sxs-lookup"><span data-stu-id="06dcc-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="06dcc-104">不过，您可以重写此行为，以便为个别单元格设置工具提示文本值。</span><span class="sxs-lookup"><span data-stu-id="06dcc-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="06dcc-105">这对于向用户显示有关单元的其他信息或向用户提供单元内容的替代说明非常有用。</span><span class="sxs-lookup"><span data-stu-id="06dcc-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="06dcc-106">例如，如果有一个显示状态图标的行，则可能需要使用工具提示提供文本说明。</span><span class="sxs-lookup"><span data-stu-id="06dcc-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="06dcc-107">通过将属性设置为，还可以禁用单元格级工具提示的显示 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> `false` 。</span><span class="sxs-lookup"><span data-stu-id="06dcc-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="06dcc-108">向单元格添加工具提示</span><span class="sxs-lookup"><span data-stu-id="06dcc-108">To add a ToolTip to a cell</span></span>  
  
- <span data-ttu-id="06dcc-109">设置 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="06dcc-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="06dcc-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="06dcc-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="06dcc-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="06dcc-111">This example requires:</span></span>  
  
- <span data-ttu-id="06dcc-112">一个 <xref:System.Windows.Forms.DataGridView> 名为的控件 `dataGridView1` ，其中包含一个名 `Rating` 为的列，其中包含一个通过四个星号的字符串值 ( "\*" ) 符号。</span><span class="sxs-lookup"><span data-stu-id="06dcc-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="06dcc-113"><xref:System.Windows.Forms.DataGridView.CellFormatting>控件的事件必须与此示例中所示的事件处理程序方法相关联。</span><span class="sxs-lookup"><span data-stu-id="06dcc-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
- <span data-ttu-id="06dcc-114">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="06dcc-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="06dcc-115">可靠编程</span><span class="sxs-lookup"><span data-stu-id="06dcc-115">Robust Programming</span></span>  
 <span data-ttu-id="06dcc-116">将 <xref:System.Windows.Forms.DataGridView> 控件绑定到外部数据源或通过实现虚拟模式提供自己的数据源时，可能会遇到性能问题。</span><span class="sxs-lookup"><span data-stu-id="06dcc-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="06dcc-117">若要避免在处理大量数据时出现性能损失，请处理 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> 事件，而不是设置 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 多个单元的属性。</span><span class="sxs-lookup"><span data-stu-id="06dcc-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="06dcc-118">处理此事件时，获取单元属性的值将 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 引发事件，并返回 <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> 事件处理程序中指定的属性的值。</span><span class="sxs-lookup"><span data-stu-id="06dcc-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06dcc-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06dcc-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="06dcc-120">使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程</span><span class="sxs-lookup"><span data-stu-id="06dcc-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
