---
title: 通过 DataGridView 控件中的单元格、行和列编程
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], elements
- columns [Windows Forms], data grids
- cells [Windows Forms], data grids
- DataGridView control [Windows Forms], programming with grid elements
- rows [Windows Forms], data grids
ms.assetid: 0d76f7e4-4149-42c6-9118-bb37d6669dc5
ms.openlocfilehash: e2d5927ecff734b359b860701e094480bbf3188f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972841"
---
# <a name="programming-with-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="931f5-102">使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程</span><span class="sxs-lookup"><span data-stu-id="931f5-102">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="931f5-103">本部分提供的主题演示涉及单元、行和列对象的各种编程任务。</span><span class="sxs-lookup"><span data-stu-id="931f5-103">This section provides topics that demonstrate various programming tasks involving cell, row, and column objects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="931f5-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="931f5-104">In This Section</span></span>  
 [<span data-ttu-id="931f5-105">如何：向 Windows 窗体 DataGridView 控件中的各个单元格添加工具提示</span><span class="sxs-lookup"><span data-stu-id="931f5-105">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>](add-tooltips-to-individual-cells-in-a-wf-datagridview-control.md)  
 <span data-ttu-id="931f5-106">描述如何处理 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件，以便为各个单元格提供不同的工具提示。</span><span class="sxs-lookup"><span data-stu-id="931f5-106">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting> event to provide different ToolTips for individual cells.</span></span>  
  
 [<span data-ttu-id="931f5-107">如何：根据 Windows 窗体 DataGridView 控件的单元格中的更改执行自定义操作</span><span class="sxs-lookup"><span data-stu-id="931f5-107">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>](perform-a-custom-action-based-on-changes-in-a-cell-of-a-datagrid.md)  
 <span data-ttu-id="931f5-108">描述如何处理 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 和 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="931f5-108">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
 [<span data-ttu-id="931f5-109">如何：在 Windows 窗体 DataGridView 控件中操作区段</span><span class="sxs-lookup"><span data-stu-id="931f5-109">How to: Manipulate Bands in the Windows Forms DataGridView Control</span></span>](how-to-manipulate-bands-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="931f5-110">介绍如何对类型为的对象进行编程 <xref:System.Windows.Forms.DataGridViewBand> ，这是行和列的基类型。</span><span class="sxs-lookup"><span data-stu-id="931f5-110">Describes how to program with objects of type <xref:System.Windows.Forms.DataGridViewBand>, which is the base type for rows and columns.</span></span>  
  
 [<span data-ttu-id="931f5-111">如何：操作 Windows 窗体 DataGridView 控件中的行</span><span class="sxs-lookup"><span data-stu-id="931f5-111">How to: Manipulate Rows in the Windows Forms DataGridView Control</span></span>](how-to-manipulate-rows-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="931f5-112">介绍如何对类型为的对象进行编程 `DataGridViewRow` 。</span><span class="sxs-lookup"><span data-stu-id="931f5-112">Describes how to program with objects of type `DataGridViewRow`.</span></span>  
  
 [<span data-ttu-id="931f5-113">如何：操作 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="931f5-113">How to: Manipulate Columns in the Windows Forms DataGridView Control</span></span>](how-to-manipulate-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="931f5-114">介绍如何对类型为的对象进行编程 `DataGridViewColumn` 。</span><span class="sxs-lookup"><span data-stu-id="931f5-114">Describes how to program with objects of type `DataGridViewColumn`.</span></span>  
  
 [<span data-ttu-id="931f5-115">如何：使用 Windows 窗体 DataGridView 控件中的图像列</span><span class="sxs-lookup"><span data-stu-id="931f5-115">How to: Work with Image Columns in the Windows Forms DataGridView Control</span></span>](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="931f5-116">描述如何用类进行编程 `DataGridViewImageColumn` 。</span><span class="sxs-lookup"><span data-stu-id="931f5-116">Describes how to program with the `DataGridViewImageColumn` class.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="931f5-117">参考</span><span class="sxs-lookup"><span data-stu-id="931f5-117">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="931f5-118">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="931f5-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="931f5-119">提供类的参考文档 <xref:System.Windows.Forms.DataGridViewCell> 。</span><span class="sxs-lookup"><span data-stu-id="931f5-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="931f5-120">提供类的参考文档 <xref:System.Windows.Forms.DataGridViewRow> 。</span><span class="sxs-lookup"><span data-stu-id="931f5-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="931f5-121">提供类的参考文档 <xref:System.Windows.Forms.DataGridViewColumn> 。</span><span class="sxs-lookup"><span data-stu-id="931f5-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="931f5-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="931f5-122">Related Sections</span></span>  
 [<span data-ttu-id="931f5-123">Windows 窗体 DataGridView 控件中的基本列、行和单元格功能</span><span class="sxs-lookup"><span data-stu-id="931f5-123">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="931f5-124">提供一些主题，这些主题描述常用的单元格、行和列属性。</span><span class="sxs-lookup"><span data-stu-id="931f5-124">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="931f5-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="931f5-125">See also</span></span>

- [<span data-ttu-id="931f5-126">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="931f5-126">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="931f5-127">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="931f5-127">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
