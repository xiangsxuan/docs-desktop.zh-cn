---
title: 在 DataGridView 控件中调整列和行的大小
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 8f8394a837ccc11c469f9ad4feeb60464d0014fe
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972011"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="eb6a7-102">调整 Windows 窗体 DataGridView 控件中列和行的大小</span><span class="sxs-lookup"><span data-stu-id="eb6a7-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="eb6a7-103">`DataGridView`控件提供了很多用于自定义其列和行的大小调整行为的选项。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="eb6a7-104">通常， `DataGridView` 单元不会根据其内容调整大小。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="eb6a7-105">相反，它们会剪裁大于该单元的任何显示值。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="eb6a7-106">如果内容显示为字符串，则单元格会在工具提示中显示它。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="eb6a7-107">默认情况下，用户可以使用鼠标拖动行、列和标题分隔符来显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="eb6a7-108">用户还可以双击分隔线，根据其内容自动调整关联的行、列或标题带区的大小。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="eb6a7-109">`DataGridView`控件提供属性、方法和事件，使您可以自定义或禁用所有这些用户定向行为。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="eb6a7-110">此外，可以以编程方式调整行、列和标头的大小以适应其内容，也可以将其配置为在其内容更改时自动调整其大小。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="eb6a7-111">您还可以将列配置为按您指定的比例将控件的可用宽度自动划分。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb6a7-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="eb6a7-112">In This Section</span></span>  
 [<span data-ttu-id="eb6a7-113">Windows 窗体 DataGridView 控件中的大小调整选项</span><span class="sxs-lookup"><span data-stu-id="eb6a7-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="eb6a7-114">介绍用于调整行、列和标头大小的选项。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="eb6a7-115">还提供了有关大小调整的属性和方法的详细信息，并介绍了常见的使用方案。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="eb6a7-116">Windows 窗体 DataGridView 控件中的列填充模式</span><span class="sxs-lookup"><span data-stu-id="eb6a7-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="eb6a7-117">详细说明列填充模式，并提供可用于试验列填充模式和其他模式的演示代码。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="eb6a7-118">如何：设置 Windows 窗体 DataGridView 控件的大小调整模式</span><span class="sxs-lookup"><span data-stu-id="eb6a7-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="eb6a7-119">描述如何为常见用途配置大小调整模式。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="eb6a7-120">如何：以编程方式调整单元格的大小来适应 Windows 窗体 DataGridView 控件中的内容</span><span class="sxs-lookup"><span data-stu-id="eb6a7-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="eb6a7-121">提供可用于试验编程大小的演示代码。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="eb6a7-122">如何：自动调整单元格的大小来适应 Windows 窗体 DataGridView 控件中的内容变化</span><span class="sxs-lookup"><span data-stu-id="eb6a7-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="eb6a7-123">提供了可用于尝试自动调整大小模式的演示代码。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eb6a7-124">参考</span><span class="sxs-lookup"><span data-stu-id="eb6a7-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="eb6a7-125">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="eb6a7-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb6a7-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb6a7-126">See also</span></span>

- [<span data-ttu-id="eb6a7-127">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="eb6a7-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
