---
title: DataGrid 控件
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: efcc8770232f657c13135cefb4027f814d4d7d19
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970141"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="91715-102">DataGrid 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="91715-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="91715-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 `DataGrid` 控件并添加了功能；但是，可以选择保留 `DataGrid` 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="91715-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="91715-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="91715-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="91715-105">Windows 窗体 `DataGrid` 控件提供一个用户界面，用于 ADO.NET 数据集，并显示表格数据和启用数据源更新。</span><span class="sxs-lookup"><span data-stu-id="91715-105">The Windows Forms `DataGrid` control provides a user interface to ADO.NET datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="91715-106">`DataGrid` 控件设置为有效数据源时，则自动填充该控件，同时根据数据的形状创建列和行。</span><span class="sxs-lookup"><span data-stu-id="91715-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="91715-107">`DataGrid` 控件可用于显示单个表或显示一组表之间的分层关系。</span><span class="sxs-lookup"><span data-stu-id="91715-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91715-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="91715-108">In This Section</span></span>  
 [<span data-ttu-id="91715-109">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="91715-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="91715-110">描述 `DataGrid` 控件的基本功能。</span><span class="sxs-lookup"><span data-stu-id="91715-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="91715-111">如何：使用设计器向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="91715-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="91715-112">描述如何使用设计器向 `DataGrid` 控件添加表和列。</span><span class="sxs-lookup"><span data-stu-id="91715-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="91715-113">如何：向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="91715-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="91715-114">描述如何以编程方式向 `DataGrid` 控件添加表和列。</span><span class="sxs-lookup"><span data-stu-id="91715-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="91715-115">如何：使用设计器将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="91715-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="91715-116">介绍如何使用设计器将 ADO.NET 数据集绑定到 `DataGrid` 控件。</span><span class="sxs-lookup"><span data-stu-id="91715-116">Describes how to bind an ADO.NET dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="91715-117">如何：将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="91715-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="91715-118">介绍如何将 ADO.NET 数据集绑定到 `DataGrid` 控件。</span><span class="sxs-lookup"><span data-stu-id="91715-118">Describes how to bind an ADO.NET dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="91715-119">如何：更改 Windows 窗体 DataGrid 控件中在运行时显示的数据</span><span class="sxs-lookup"><span data-stu-id="91715-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="91715-120">描述如何在 `DataGrid` 控件中以编程方式更改数据。</span><span class="sxs-lookup"><span data-stu-id="91715-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="91715-121">如何：通过使用设计器使用 Windows 窗体 DataGrid 控件创建主/详细信息列表</span><span class="sxs-lookup"><span data-stu-id="91715-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="91715-122">描述如何使用设计器在两个独立的 `DataGrid` 控件中显示以父/子关系关联在一起的两个表。</span><span class="sxs-lookup"><span data-stu-id="91715-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="91715-123">如何：使用 Windows 窗体 DataGrid 控件创建主/从列表</span><span class="sxs-lookup"><span data-stu-id="91715-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="91715-124">描述如何在两个独立的 `DataGrid` 控件中显示以父/子关系关联在一起的两个表。</span><span class="sxs-lookup"><span data-stu-id="91715-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="91715-125">如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列</span><span class="sxs-lookup"><span data-stu-id="91715-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="91715-126">描述如何在 `DataGrid` 控件中删除列。</span><span class="sxs-lookup"><span data-stu-id="91715-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="91715-127">如何：使用设计器设置 Windows 窗体 DataGrid 控件的格式</span><span class="sxs-lookup"><span data-stu-id="91715-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="91715-128">描述如何使用设计器更改 `DataGrid` 控件与外观相关的属性。</span><span class="sxs-lookup"><span data-stu-id="91715-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="91715-129">如何：设置 Windows 窗体 DataGrid 控件的格式</span><span class="sxs-lookup"><span data-stu-id="91715-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="91715-130">描述如何更改 `DataGrid` 控件与外观相关的属性。</span><span class="sxs-lookup"><span data-stu-id="91715-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="91715-131">Windows 窗体 DataGrid 控件的键盘快捷键</span><span class="sxs-lookup"><span data-stu-id="91715-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="91715-132">列出通过 `DataGrid` 控件进行导航的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="91715-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="91715-133">如何：响应 Windows 窗体 DataGrid 控件中的单击</span><span class="sxs-lookup"><span data-stu-id="91715-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="91715-134">描述如何确定用户在 `DataGrid` 控件中单击的单元格。</span><span class="sxs-lookup"><span data-stu-id="91715-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="91715-135">如何：用 Windows 窗体 DataGrid 控件验证输入</span><span class="sxs-lookup"><span data-stu-id="91715-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="91715-136">描述如何验证绑定到 `DataGrid` 控件的数据集中的输入。</span><span class="sxs-lookup"><span data-stu-id="91715-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="91715-137">参考</span><span class="sxs-lookup"><span data-stu-id="91715-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="91715-138">提供类的概述 <xref:System.Windows.Forms.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="91715-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="91715-139">提供有关使用此属性将控件绑定到数据的详细信息 <xref:System.Windows.Forms.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="91715-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="91715-140">相关章节</span><span class="sxs-lookup"><span data-stu-id="91715-140">Related Sections</span></span>  
 [<span data-ttu-id="91715-141">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="91715-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="91715-142">提供有关 Windows 窗体中数据绑定的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="91715-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91715-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91715-143">See also</span></span>

- [<span data-ttu-id="91715-144">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="91715-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="91715-145">Windows 窗体 DataGridView 控件和 DataGrid 控件之间的区别</span><span class="sxs-lookup"><span data-stu-id="91715-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)
