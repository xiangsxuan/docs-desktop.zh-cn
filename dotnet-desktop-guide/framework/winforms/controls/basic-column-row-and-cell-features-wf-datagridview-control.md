---
title: DataGridView 控件中的基本列、行和单元格功能
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: 02f8ad7e11a61e9434748a8b3b2f853f98b013d1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971567"
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d1ced-102">Windows 窗体 DataGridView 控件中的基本列、行和单元格功能</span><span class="sxs-lookup"><span data-stu-id="d1ced-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d1ced-103">`DataGridView`可以通过设置单个属性来修改单元格、行和列的许多基本行为。</span><span class="sxs-lookup"><span data-stu-id="d1ced-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="d1ced-104">本节中的主题介绍了这些功能的几个最常用的功能。</span><span class="sxs-lookup"><span data-stu-id="d1ced-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1ced-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="d1ced-105">In This Section</span></span>  
 [<span data-ttu-id="d1ced-106">如何：隐藏 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="d1ced-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d1ced-107">描述如何防止特定列出现在控件中。</span><span class="sxs-lookup"><span data-stu-id="d1ced-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="d1ced-108">如何：隐藏 Windows 窗体 DataGridView 控件中的列标题</span><span class="sxs-lookup"><span data-stu-id="d1ced-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d1ced-109">描述如何防止列标头出现在控件中。</span><span class="sxs-lookup"><span data-stu-id="d1ced-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="d1ced-110">如何：启用 Windows 窗体 DataGridView 控件中列的重新排序</span><span class="sxs-lookup"><span data-stu-id="d1ced-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d1ced-111">描述如何使用户能够重新排列控件中的列。</span><span class="sxs-lookup"><span data-stu-id="d1ced-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="d1ced-112">如何：冻结 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="d1ced-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d1ced-113">介绍如何防止一个或多个相邻列滚动。</span><span class="sxs-lookup"><span data-stu-id="d1ced-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="d1ced-114">如何：将 Windows 窗体 DataGridView 控件中的列设为只读</span><span class="sxs-lookup"><span data-stu-id="d1ced-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d1ced-115">描述如何防止用户编辑控件中的特定列。</span><span class="sxs-lookup"><span data-stu-id="d1ced-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="d1ced-116">如何：防止在 Windows 窗体 DataGridView 控件中添加和删除行</span><span class="sxs-lookup"><span data-stu-id="d1ced-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="d1ced-117">介绍如何删除控件底部的新记录行，以防止用户添加行。</span><span class="sxs-lookup"><span data-stu-id="d1ced-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="d1ced-118">还介绍如何防止用户删除行。</span><span class="sxs-lookup"><span data-stu-id="d1ced-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="d1ced-119">如何：获取和设置 Windows 窗体 DataGridView 控件中的当前单元格</span><span class="sxs-lookup"><span data-stu-id="d1ced-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="d1ced-120">介绍如何访问控件中当前具有焦点的单元格。</span><span class="sxs-lookup"><span data-stu-id="d1ced-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="d1ced-121">如何：在 Windows 窗体 DataGridView 控件的单元格中显示图像</span><span class="sxs-lookup"><span data-stu-id="d1ced-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d1ced-122">介绍如何创建在每个单元格中显示图标的 image 列。</span><span class="sxs-lookup"><span data-stu-id="d1ced-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d1ced-123">参考</span><span class="sxs-lookup"><span data-stu-id="d1ced-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="d1ced-124">提供控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="d1ced-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d1ced-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="d1ced-125">Related Sections</span></span>  
 [<span data-ttu-id="d1ced-126">Windows 窗体 DataGridView 控件中的基本格式设置和样式设置</span><span class="sxs-lookup"><span data-stu-id="d1ced-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d1ced-127">提供一些主题，描述如何修改该控件的基本外观和单元数据的显示格式。</span><span class="sxs-lookup"><span data-stu-id="d1ced-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="d1ced-128">使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程</span><span class="sxs-lookup"><span data-stu-id="d1ced-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="d1ced-129">提供一些主题，介绍如何使用单元格、行和列对象进行编程。</span><span class="sxs-lookup"><span data-stu-id="d1ced-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ced-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1ced-130">See also</span></span>

- [<span data-ttu-id="d1ced-131">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="d1ced-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="d1ced-132">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="d1ced-132">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
