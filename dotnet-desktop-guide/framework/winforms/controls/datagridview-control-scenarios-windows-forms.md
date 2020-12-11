---
title: DataGridView 控件方案
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: 160d967c6445fb753cb6c73babfb02a734a07e28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970115"
---
# <a name="datagridview-control-scenarios-windows-forms"></a><span data-ttu-id="0dd53-102">DataGridView 控件方案（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="0dd53-102">DataGridView Control Scenarios (Windows Forms)</span></span>
<span data-ttu-id="0dd53-103">使用 <xref:System.Windows.Forms.DataGridView> 控件，可以显示来自各种数据源的表格数据。</span><span class="sxs-lookup"><span data-stu-id="0dd53-103">With the <xref:System.Windows.Forms.DataGridView> control, you can display tabular data from a variety of data sources.</span></span> <span data-ttu-id="0dd53-104">对于简单的用法，可以手动填充 <xref:System.Windows.Forms.DataGridView> 并通过控件直接操作数据。</span><span class="sxs-lookup"><span data-stu-id="0dd53-104">For simple uses, you can manually populate a <xref:System.Windows.Forms.DataGridView> and manipulate the data directly through the control.</span></span> <span data-ttu-id="0dd53-105">不过，通常会将数据存储在外部数据源中，并通过组件将控件绑定到该数据源 <xref:System.Windows.Forms.BindingSource> 。</span><span class="sxs-lookup"><span data-stu-id="0dd53-105">Typically, however, you will store your data in an external data source and bind the control to it through a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="0dd53-106">本主题介绍了一些涉及控件的常见方案 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="0dd53-106">This topic describes some of the common scenarios that involve the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a><span data-ttu-id="0dd53-107">方案1：显示少量数据</span><span class="sxs-lookup"><span data-stu-id="0dd53-107">Scenario 1: Displaying Small Amounts of Data</span></span>  
 <span data-ttu-id="0dd53-108">无需将数据存储在外部数据源中即可在控件中显示数据 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="0dd53-108">You do not have to store your data in an external data source to display it in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0dd53-109">如果你使用少量的数据，则可以自行填充控件，并通过控件处理数据。</span><span class="sxs-lookup"><span data-stu-id="0dd53-109">If you are working with a small amount of data, you can populate the control yourself and manipulate the data through the control.</span></span> <span data-ttu-id="0dd53-110">这称为 *未绑定模式*。</span><span class="sxs-lookup"><span data-stu-id="0dd53-110">This is called *unbound mode*.</span></span> <span data-ttu-id="0dd53-111">有关详细信息，请参阅 [如何：创建未绑定的 Windows 窗体 DataGridView 控件](how-to-create-an-unbound-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd53-111">For more information, see [How to: Create an Unbound Windows Forms DataGridView Control](how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="0dd53-112">方案关键点</span><span class="sxs-lookup"><span data-stu-id="0dd53-112">Scenario Key Points</span></span>  
  
- <span data-ttu-id="0dd53-113">在未绑定模式下，手动填充控件。</span><span class="sxs-lookup"><span data-stu-id="0dd53-113">In unbound mode, you populate the control manually.</span></span>  
  
- <span data-ttu-id="0dd53-114">未绑定模式特别适用于少量的只读数据。</span><span class="sxs-lookup"><span data-stu-id="0dd53-114">Unbound mode is particularly suited for small amounts of read-only data.</span></span>  
  
- <span data-ttu-id="0dd53-115">未绑定模式也适用于类似电子表格或稀疏填充的表。</span><span class="sxs-lookup"><span data-stu-id="0dd53-115">Unbound mode is also suited for spreadsheet-like or sparsely populated tables.</span></span>  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a><span data-ttu-id="0dd53-116">方案2：查看和更新存储在外部数据源中的数据</span><span class="sxs-lookup"><span data-stu-id="0dd53-116">Scenario 2: Viewing and Updating Data Stored in an External Data Source</span></span>  
 <span data-ttu-id="0dd53-117">您可以使用 <xref:System.Windows.Forms.DataGridView> 控件作为 (UI) 用户界面，用户可以通过该界面访问数据源（如数据库表或业务对象集合）中保存的数据。</span><span class="sxs-lookup"><span data-stu-id="0dd53-117">You can use the <xref:System.Windows.Forms.DataGridView> control as a user interface (UI) through which users can access data kept in a data source such as a database table or a collection of business objects.</span></span> <span data-ttu-id="0dd53-118">有关详细信息，请参阅 [如何：将数据绑定到 Windows 窗体 DataGridView 控件](how-to-bind-data-to-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd53-118">For more information, see [How to: Bind Data to the Windows Forms DataGridView Control](how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="0dd53-119">方案关键点</span><span class="sxs-lookup"><span data-stu-id="0dd53-119">Scenario Key Points</span></span>  
  
- <span data-ttu-id="0dd53-120">绑定模式使您可以连接到数据源，并基于数据源属性或数据库列自动生成列，并自动填充控件。</span><span class="sxs-lookup"><span data-stu-id="0dd53-120">Bound mode lets you connect to a data source, automatically generate columns based on the data source properties or database columns, and automatically populate the control.</span></span>  
  
- <span data-ttu-id="0dd53-121">绑定模式适用于与数据的繁重用户交互。</span><span class="sxs-lookup"><span data-stu-id="0dd53-121">Bound mode is suited for heavy user interaction with data.</span></span> <span data-ttu-id="0dd53-122">数据可以设置为显示格式，用户指定的数据可以解析为数据源所需的格式。</span><span class="sxs-lookup"><span data-stu-id="0dd53-122">Data can be formatted for display, and user-specified data can be parsed into the format expected by the data source.</span></span> <span data-ttu-id="0dd53-123">可以检测到数据输入格式错误和数据库约束错误，以便可以警告用户和更正错误的单元格。</span><span class="sxs-lookup"><span data-stu-id="0dd53-123">Data entry formatting errors and database constraint errors can be detected so that users can be warned and erroneous cells can be corrected.</span></span>  
  
- <span data-ttu-id="0dd53-124">其他功能（如列排序、冻结和重新排序）使用户能够以最方便的方式查看其工作流中的数据。</span><span class="sxs-lookup"><span data-stu-id="0dd53-124">Additional functionality such as column sorting, freezing, and reordering enable users to view data in the way most convenient for their workflow.</span></span>  
  
- <span data-ttu-id="0dd53-125">剪贴板支持使用户能够将数据从应用程序复制到其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="0dd53-125">Clipboard support enables users to copy data from your application into other applications.</span></span>  
  
## <a name="scenario-3-advanced-data"></a><span data-ttu-id="0dd53-126">方案3：高级数据</span><span class="sxs-lookup"><span data-stu-id="0dd53-126">Scenario 3: Advanced Data</span></span>  
 <span data-ttu-id="0dd53-127">如果你有标准数据绑定模型没有解决的特殊需求，则可以通过实现 *虚拟模式* 来管理控件和数据之间的交互。</span><span class="sxs-lookup"><span data-stu-id="0dd53-127">If you have special needs that the standard data binding model does not address, you can manage the interaction between the control and your data by implementing *virtual mode*.</span></span> <span data-ttu-id="0dd53-128">实现虚拟模式意味着实现一个或多个事件处理程序，以便在需要信息时控制单元请求相关信息。</span><span class="sxs-lookup"><span data-stu-id="0dd53-128">Implementing virtual mode means implementing one or more event handlers that let the control request information about cells as the information is needed.</span></span>  
  
 <span data-ttu-id="0dd53-129">例如，如果你使用大量数据，则可能需要实现虚拟模式，以确保获得最佳效率。</span><span class="sxs-lookup"><span data-stu-id="0dd53-129">For example, if you work with large amounts of data, you may want to implement virtual mode to ensure optimal efficiency.</span></span> <span data-ttu-id="0dd53-130">虚拟模式对于维护与从另一个数据源检索的列一起显示的未绑定列的值也很有用。</span><span class="sxs-lookup"><span data-stu-id="0dd53-130">Virtual mode is also useful for maintaining the values of unbound columns that you display along with columns retrieved from another data source.</span></span>  
  
 <span data-ttu-id="0dd53-131">有关虚拟模式的详细信息，请参阅 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd53-131">For more information about virtual mode, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="0dd53-132">方案关键点</span><span class="sxs-lookup"><span data-stu-id="0dd53-132">Scenario Key Points</span></span>  
  
- <span data-ttu-id="0dd53-133">当你需要对性能进行微调时，虚拟模式适用于显示大量的数据。</span><span class="sxs-lookup"><span data-stu-id="0dd53-133">Virtual mode is suited for displaying very large amounts of data when you need to fine-tune performance.</span></span>  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a><span data-ttu-id="0dd53-134">方案4：自动调整行和列的大小</span><span class="sxs-lookup"><span data-stu-id="0dd53-134">Scenario 4: Automatically Resizing Rows and Columns</span></span>  
 <span data-ttu-id="0dd53-135">当显示定期更新的数据时，可以自动调整行和列的大小，以确保所有内容都可见。</span><span class="sxs-lookup"><span data-stu-id="0dd53-135">When you display data that is regularly updated, you can automatically resize rows and columns to ensure that all content is visible.</span></span> <span data-ttu-id="0dd53-136"><xref:System.Windows.Forms.DataGridView>控件提供了几个选项，可用于启用或禁用手动调整大小、在特定时间以编程方式调整大小，或在内容发生更改时自动调整大小。</span><span class="sxs-lookup"><span data-stu-id="0dd53-136">The <xref:System.Windows.Forms.DataGridView> control provides several options that let you enable or disable manual resizing, resize programmatically at specific times, or resize automatically whenever content changes.</span></span> <span data-ttu-id="0dd53-137">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件中的调整大小选项](sizing-options-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd53-137">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="0dd53-138">方案关键点</span><span class="sxs-lookup"><span data-stu-id="0dd53-138">Scenario Key Points</span></span>  
  
- <span data-ttu-id="0dd53-139">手动调整大小使用户能够调整单元高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="0dd53-139">Manual resizing enables users to adjust cell heights and widths.</span></span>  
  
- <span data-ttu-id="0dd53-140">自动调整大小使您能够保持单元大小，以便永远不会剪辑单元内容。</span><span class="sxs-lookup"><span data-stu-id="0dd53-140">Automatic resizing enables you to maintain cell sizes so that cell content is never clipped.</span></span>  
  
- <span data-ttu-id="0dd53-141">编程调整大小使您能够在特定时间调整单元格的大小，以避免连续自动调整大小的性能损失。</span><span class="sxs-lookup"><span data-stu-id="0dd53-141">Programmatic resizing enables you to resize cells at specific times to avoid the performance penalty of continuous automatic resizing.</span></span>  
  
## <a name="scenario-5-simple-customization"></a><span data-ttu-id="0dd53-142">方案5：简单自定义</span><span class="sxs-lookup"><span data-stu-id="0dd53-142">Scenario 5: Simple Customization</span></span>  
 <span data-ttu-id="0dd53-143"><xref:System.Windows.Forms.DataGridView>控件提供多种方法来更改其基本外观和行为。</span><span class="sxs-lookup"><span data-stu-id="0dd53-143">The <xref:System.Windows.Forms.DataGridView> control provides many ways for you to alter its basic appearance and behavior.</span></span> <span data-ttu-id="0dd53-144">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd53-144">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="0dd53-145">方案关键点</span><span class="sxs-lookup"><span data-stu-id="0dd53-145">Scenario Key Points</span></span>  
  
- <span data-ttu-id="0dd53-146"><xref:System.Windows.Forms.DataGridViewCellStyle> 通过对象，可以在多个级别和控件的单个元素上提供颜色、字体、格式设置和定位信息。</span><span class="sxs-lookup"><span data-stu-id="0dd53-146"><xref:System.Windows.Forms.DataGridViewCellStyle> objects let you provide color, font, formatting, and positioning information at multiple levels and for individual elements of the control.</span></span>  
  
- <span data-ttu-id="0dd53-147">单元格样式可由多个元素分层和共享，从而使你可以重复使用代码。</span><span class="sxs-lookup"><span data-stu-id="0dd53-147">Cell styles can be layered and shared by multiple elements, letting you reuse code.</span></span>  
  
## <a name="scenario-6-advanced-customization"></a><span data-ttu-id="0dd53-148">方案6：高级自定义</span><span class="sxs-lookup"><span data-stu-id="0dd53-148">Scenario 6: Advanced Customization</span></span>  
 <span data-ttu-id="0dd53-149"><xref:System.Windows.Forms.DataGridView>控件提供多种方法用于自定义其外观和行为。</span><span class="sxs-lookup"><span data-stu-id="0dd53-149">The <xref:System.Windows.Forms.DataGridView> control provides many ways for you to customize its appearance and behavior.</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="0dd53-150">方案关键点</span><span class="sxs-lookup"><span data-stu-id="0dd53-150">Scenario Key Points</span></span>  
  
- <span data-ttu-id="0dd53-151">可以提供自己的单元格绘制代码。</span><span class="sxs-lookup"><span data-stu-id="0dd53-151">You can provide your own cell painting code.</span></span> <span data-ttu-id="0dd53-152">有关详细信息，请参阅 [如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd53-152">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="0dd53-153">可以提供自己的行绘制。</span><span class="sxs-lookup"><span data-stu-id="0dd53-153">You can provide your own row painting.</span></span> <span data-ttu-id="0dd53-154">这很有用，例如，创建包含跨多个列的内容的行。</span><span class="sxs-lookup"><span data-stu-id="0dd53-154">This is useful, for example, to create rows with content that spans multiple columns.</span></span> <span data-ttu-id="0dd53-155">有关详细信息，请参阅 [如何：自定义 Windows 窗体 DataGridView 控件中的行的外观](customize-the-appearance-of-rows-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd53-155">For more information, see [How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control](customize-the-appearance-of-rows-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="0dd53-156">您可以实现自己的单元格和列类，以自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="0dd53-156">You can implement your own cell and column classes to customize cell appearance.</span></span> <span data-ttu-id="0dd53-157">有关详细信息，请参阅 [如何：通过扩展控件的行为和外观自定义 Windows 窗体 DataGridView 控件中的单元格和列](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd53-157">For more information, see [How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).</span></span>  
  
- <span data-ttu-id="0dd53-158">您可以实现自己的单元格和列类来承载除内置列类型提供的控件以外的其他控件。</span><span class="sxs-lookup"><span data-stu-id="0dd53-158">You can implement your own cell and column classes to host controls other than the ones provided by the built-in column types.</span></span> <span data-ttu-id="0dd53-159">有关详细信息，请参阅 [如何：在 Windows 窗体 DataGridView 单元格中承载控件](how-to-host-controls-in-windows-forms-datagridview-cells.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd53-159">For more information, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd53-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0dd53-160">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="0dd53-161">DataGridView 控件概述</span><span class="sxs-lookup"><span data-stu-id="0dd53-161">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
