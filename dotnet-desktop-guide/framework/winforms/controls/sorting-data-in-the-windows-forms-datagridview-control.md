---
title: 对 DataGridView 控件中的数据进行排序
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972922"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="37e02-102">对 Windows 窗体 DataGridView 控件中的数据进行排序</span><span class="sxs-lookup"><span data-stu-id="37e02-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="37e02-103">默认情况下，用户可以通过单击文本框列的标题来对控件中的数据进行排序， <xref:System.Windows.Forms.DataGridView> (或在文本框单元格集中于 .NET Framework 4.7.2 和更高版本) 时按 F3。</span><span class="sxs-lookup"><span data-stu-id="37e02-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="37e02-104">您可以修改 <xref:System.Windows.Forms.DataGridViewColumn.SortMode> 特定列的属性，以允许用户在执行此操作时按其他列类型进行排序。</span><span class="sxs-lookup"><span data-stu-id="37e02-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="37e02-105">还可以通过编程方式按任何列或多个列对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="37e02-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="37e02-106">在本节中</span><span class="sxs-lookup"><span data-stu-id="37e02-106">In this section</span></span>

[<span data-ttu-id="37e02-107">Windows 窗体 DataGridView 控件中的列排序模式</span><span class="sxs-lookup"><span data-stu-id="37e02-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="37e02-108">描述用于对控件中的数据进行排序的选项。</span><span class="sxs-lookup"><span data-stu-id="37e02-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="37e02-109">如何：设置 Windows 窗体 DataGridView 控件中列的排序模式</span><span class="sxs-lookup"><span data-stu-id="37e02-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="37e02-110">介绍如何使用户能够按默认情况下不可排序的列排序。</span><span class="sxs-lookup"><span data-stu-id="37e02-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="37e02-111">如何：自定义 Windows 窗体 DataGridView 控件中的排序方式</span><span class="sxs-lookup"><span data-stu-id="37e02-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="37e02-112">描述如何以编程方式对数据进行排序，以及如何使用 <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> 事件或通过实现接口自定义排序 <xref:System.Collections.IComparer> 。</span><span class="sxs-lookup"><span data-stu-id="37e02-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="37e02-113">参考</span><span class="sxs-lookup"><span data-stu-id="37e02-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="37e02-114">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="37e02-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="37e02-115">提供方法的参考文档 <xref:System.Windows.Forms.DataGridView.Sort%2A> 。</span><span class="sxs-lookup"><span data-stu-id="37e02-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="37e02-116">提供属性的参考文档 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 。</span><span class="sxs-lookup"><span data-stu-id="37e02-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="37e02-117">提供枚举的参考文档 <xref:System.Windows.Forms.DataGridViewColumnSortMode> 。</span><span class="sxs-lookup"><span data-stu-id="37e02-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="37e02-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37e02-118">See also</span></span>

- [<span data-ttu-id="37e02-119">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="37e02-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="37e02-120">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="37e02-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
