---
title: 创建未绑定的 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: ceb75d4ee845d1f643d4d88d5a9f1bde73edcc70
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973211"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="91ea2-102">演练：创建未绑定的 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="91ea2-102">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="91ea2-103">您可能经常希望显示不源自数据库的表格数据。</span><span class="sxs-lookup"><span data-stu-id="91ea2-103">You may frequently want to display tabular data that does not originate from a database.</span></span> <span data-ttu-id="91ea2-104">例如，你可能想要显示字符串的二维数组的内容。</span><span class="sxs-lookup"><span data-stu-id="91ea2-104">For example, you may want to show the contents of a two-dimensional array of strings.</span></span> <span data-ttu-id="91ea2-105"><xref:System.Windows.Forms.DataGridView>类提供了一种简单而又高度可自定义的方法，可在不绑定到数据源的情况下显示数据。</span><span class="sxs-lookup"><span data-stu-id="91ea2-105">The <xref:System.Windows.Forms.DataGridView> class provides an easy and highly customizable way to display data without binding to a data source.</span></span> <span data-ttu-id="91ea2-106">本演练演示如何 <xref:System.Windows.Forms.DataGridView> 在 "未绑定" 模式下填充控件并管理行的添加和删除。</span><span class="sxs-lookup"><span data-stu-id="91ea2-106">This walkthrough shows how to populate a <xref:System.Windows.Forms.DataGridView> control and manage the addition and deletion of rows in "unbound" mode.</span></span> <span data-ttu-id="91ea2-107">默认情况下，用户可以添加新行。</span><span class="sxs-lookup"><span data-stu-id="91ea2-107">By default, the user can add new rows.</span></span> <span data-ttu-id="91ea2-108">若要防止添加行，请将 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="91ea2-108">To prevent row addition, set the <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="91ea2-109">若要将本主题中的代码复制为单个列表，请参阅 [如何：创建未绑定的 Windows 窗体 DataGridView 控件](how-to-create-an-unbound-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="91ea2-109">To copy the code in this topic as a single listing, see [How to: Create an Unbound Windows Forms DataGridView Control](how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="91ea2-110">创建窗体</span><span class="sxs-lookup"><span data-stu-id="91ea2-110">Creating the Form</span></span>  
  
#### <a name="to-use-an-unbound-datagridview-control"></a><span data-ttu-id="91ea2-111">使用未绑定的 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="91ea2-111">To use an unbound DataGridView control</span></span>  
  
1. <span data-ttu-id="91ea2-112">创建一个派生自的类 <xref:System.Windows.Forms.Form> ，其中包含以下变量声明和 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="91ea2-112">Create a class that derives from <xref:System.Windows.Forms.Form> and contains the following variable declarations and `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. <span data-ttu-id="91ea2-113">`SetupLayout`在窗体的类定义中实现方法，以设置窗体的布局。</span><span class="sxs-lookup"><span data-stu-id="91ea2-113">Implement a `SetupLayout` method in your form's class definition to set up the form's layout.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. <span data-ttu-id="91ea2-114">创建 `SetupDataGridView` 用于设置 <xref:System.Windows.Forms.DataGridView> 列和属性的方法。</span><span class="sxs-lookup"><span data-stu-id="91ea2-114">Create a `SetupDataGridView` method to set up the <xref:System.Windows.Forms.DataGridView> columns and properties.</span></span>  
  
     <span data-ttu-id="91ea2-115">此方法首先将 <xref:System.Windows.Forms.DataGridView> 控件添加到窗体的 <xref:System.Windows.Forms.Control.Controls%2A> 集合中。</span><span class="sxs-lookup"><span data-stu-id="91ea2-115">This method first adds the <xref:System.Windows.Forms.DataGridView> control to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="91ea2-116">接下来，使用属性设置要显示的列数 <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> 。</span><span class="sxs-lookup"><span data-stu-id="91ea2-116">Next, the number of columns to be displayed is set using the <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> property.</span></span> <span data-ttu-id="91ea2-117">列标题的默认样式通过设置 <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> 属性返回的的、和属性进行设置 <xref:System.Windows.Forms.DataGridViewCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 。</span><span class="sxs-lookup"><span data-stu-id="91ea2-117">The default style for the column headers is set by setting the <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, and <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> returned by the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> property.</span></span>  
  
     <span data-ttu-id="91ea2-118">设置布局和外观属性，然后分配列名称。</span><span class="sxs-lookup"><span data-stu-id="91ea2-118">Layout and appearance properties are set, and then the column names are assigned.</span></span> <span data-ttu-id="91ea2-119">此方法退出时， <xref:System.Windows.Forms.DataGridView> 控件即可填充。</span><span class="sxs-lookup"><span data-stu-id="91ea2-119">When this method exits, the <xref:System.Windows.Forms.DataGridView> control is ready to be populated.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. <span data-ttu-id="91ea2-120">创建向 `PopulateDataGridView` 控件添加行的方法 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="91ea2-120">Create a `PopulateDataGridView` method to add rows to the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="91ea2-121">每一行代表一首歌曲及其关联的信息。</span><span class="sxs-lookup"><span data-stu-id="91ea2-121">Each row represents a song and its associated information.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. <span data-ttu-id="91ea2-122">在实用工具方法就绪后，可以附加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="91ea2-122">With the utility methods in place, you can attach event handlers.</span></span>  
  
     <span data-ttu-id="91ea2-123">您将处理 " **添加** " 和 " **删除** " 按钮的事件 <xref:System.Windows.Forms.Control.Click> 、窗体的 <xref:System.Windows.Forms.Form.Load> 事件和 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件。</span><span class="sxs-lookup"><span data-stu-id="91ea2-123">You will handle the **Add** and **Delete** buttons' <xref:System.Windows.Forms.Control.Click> events, the form's <xref:System.Windows.Forms.Form.Load> event, and the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
     <span data-ttu-id="91ea2-124">引发 " **添加** " 按钮的 <xref:System.Windows.Forms.Control.Click> 事件时，会向中添加一个新的空行 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="91ea2-124">When the **Add** button's <xref:System.Windows.Forms.Control.Click> event is raised, a new, empty row is added to the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="91ea2-125">引发 " **删除** " 按钮的 <xref:System.Windows.Forms.Control.Click> 事件时，将删除所选的行，除非它是新记录的行，从而使用户能够添加新行。</span><span class="sxs-lookup"><span data-stu-id="91ea2-125">When the **Delete** button's <xref:System.Windows.Forms.Control.Click> event is raised, the selected row is deleted, unless it is the row for new records, which enables the user add new rows.</span></span> <span data-ttu-id="91ea2-126">此行始终是控件中的最后一行 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="91ea2-126">This row is always the last row in the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="91ea2-127">引发窗体的 <xref:System.Windows.Forms.Form.Load> 事件时，将 `SetupLayout` 调用、 `SetupDataGridView` 和 `PopulateDataGridView` 实用工具方法。</span><span class="sxs-lookup"><span data-stu-id="91ea2-127">When the form's <xref:System.Windows.Forms.Form.Load> event is raised, the `SetupLayout`, `SetupDataGridView`, and `PopulateDataGridView` utility methods are called.</span></span>  
  
     <span data-ttu-id="91ea2-128"><xref:System.Windows.Forms.DataGridView.CellFormatting>引发事件时，会将列中的每个单元格的 `Date` 格式设置为长日期，除非无法分析该单元的值。</span><span class="sxs-lookup"><span data-stu-id="91ea2-128">When the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is raised, each cell in the `Date` column is formatted as a long date, unless the cell's value cannot be parsed.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="91ea2-129">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="91ea2-129">Testing the Application</span></span>  
 <span data-ttu-id="91ea2-130">你现在可以对窗体进行测试，以确保它按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="91ea2-130">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="91ea2-131">测试窗体</span><span class="sxs-lookup"><span data-stu-id="91ea2-131">To test the form</span></span>  
  
- <span data-ttu-id="91ea2-132">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="91ea2-132">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="91ea2-133">你将看到一个 <xref:System.Windows.Forms.DataGridView> 控件，该控件显示中列出的歌曲 `PopulateDataGridView` 。</span><span class="sxs-lookup"><span data-stu-id="91ea2-133">You will see a <xref:System.Windows.Forms.DataGridView> control that displays the songs listed in `PopulateDataGridView`.</span></span> <span data-ttu-id="91ea2-134">您可以通过 " **添加行** " 按钮添加新行，并且可以通过 " **删除行** " 按钮删除所选行。</span><span class="sxs-lookup"><span data-stu-id="91ea2-134">You can add new rows with the **Add Row** button, and you can delete selected rows with the **Delete Row** button.</span></span> <span data-ttu-id="91ea2-135">未绑定 <xref:System.Windows.Forms.DataGridView> 控件是数据存储区，其数据独立于任何外部源，如 <xref:System.Data.DataSet> 或数组。</span><span class="sxs-lookup"><span data-stu-id="91ea2-135">The unbound <xref:System.Windows.Forms.DataGridView> control is the data store, and its data is independent of any external source, such as a <xref:System.Data.DataSet> or an array.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="91ea2-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="91ea2-136">Next Steps</span></span>  
 <span data-ttu-id="91ea2-137">此应用程序可让你对控件的功能有一个基本的了解 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="91ea2-137">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="91ea2-138">可以通过多种方式自定义控件的外观和行为 <xref:System.Windows.Forms.DataGridView> ：</span><span class="sxs-lookup"><span data-stu-id="91ea2-138">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
- <span data-ttu-id="91ea2-139">更改边框和标题样式。</span><span class="sxs-lookup"><span data-stu-id="91ea2-139">Change border and header styles.</span></span> <span data-ttu-id="91ea2-140">有关详细信息，请参阅 [如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线样式](change-the-border-and-gridline-styles-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="91ea2-140">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="91ea2-141">启用或限制控件的用户输入 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="91ea2-141">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="91ea2-142">有关详细信息，请参阅 [如何：防止在 Windows 窗体 Datagridview 控件中添加和删除行](prevent-row-addition-and-deletion-datagridview.md)，以及 [如何：使列在 Windows 窗体 DataGridView 控件中 Read-Only](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="91ea2-142">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="91ea2-143">检查用户输入中的数据库相关错误。</span><span class="sxs-lookup"><span data-stu-id="91ea2-143">Check user input for database-related errors.</span></span> <span data-ttu-id="91ea2-144">有关详细信息，请参阅 [演练：处理 Windows 窗体 DataGridView 控件中的数据输入过程中发生的错误](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="91ea2-144">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="91ea2-145">使用虚拟模式处理非常大的数据集。</span><span class="sxs-lookup"><span data-stu-id="91ea2-145">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="91ea2-146">有关详细信息，请参阅 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="91ea2-146">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="91ea2-147">自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="91ea2-147">Customize the appearance of cells.</span></span> <span data-ttu-id="91ea2-148">有关详细信息，请参阅 [如何：自定义 Windows 窗体 Datagridview 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md) 和 [如何：为 Windows 窗体 Datagridview 控件设置默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="91ea2-148">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ea2-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91ea2-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="91ea2-150">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="91ea2-150">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="91ea2-151">如何：创建未绑定的 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="91ea2-151">How to: Create an Unbound Windows Forms DataGridView Control</span></span>](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="91ea2-152">Windows 窗体 DataGridView 控件中的数据显示模式</span><span class="sxs-lookup"><span data-stu-id="91ea2-152">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
