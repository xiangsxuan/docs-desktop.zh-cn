---
title: 设置 DataGrid 控件的格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972034"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="259f9-102">如何：设置 Windows 窗体 DataGrid 控件的格式</span><span class="sxs-lookup"><span data-stu-id="259f9-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="259f9-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="259f9-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="259f9-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="259f9-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="259f9-105">将不同的颜色应用于控件的各个部分， <xref:System.Windows.Forms.DataGrid> 有助于更轻松地读取和解释信息。</span><span class="sxs-lookup"><span data-stu-id="259f9-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="259f9-106">颜色可以应用于行和列。</span><span class="sxs-lookup"><span data-stu-id="259f9-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="259f9-107">还可以根据自己的意愿隐藏或显示行和列。</span><span class="sxs-lookup"><span data-stu-id="259f9-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="259f9-108">有三个基本方面的控件设置格式 <xref:System.Windows.Forms.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="259f9-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="259f9-109">可以设置属性来建立显示数据的默认样式。</span><span class="sxs-lookup"><span data-stu-id="259f9-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="259f9-110">然后，你可以在运行时自定义某些表的显示方式。</span><span class="sxs-lookup"><span data-stu-id="259f9-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="259f9-111">最后，您可以修改在数据网格中显示的列，以及所显示的颜色和其他格式设置。</span><span class="sxs-lookup"><span data-stu-id="259f9-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="259f9-112">作为数据网格格式设置的初始步骤，您可以设置其自身的属性 <xref:System.Windows.Forms.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="259f9-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="259f9-113">这些颜色和格式选项构成一个基础，您可以根据所显示的数据表和列进行更改。</span><span class="sxs-lookup"><span data-stu-id="259f9-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="259f9-114">为 DataGrid 控件建立默认样式</span><span class="sxs-lookup"><span data-stu-id="259f9-114">To establish a default style for the DataGrid control</span></span>  
  
1. <span data-ttu-id="259f9-115">根据需要设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="259f9-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="259f9-116">属性</span><span class="sxs-lookup"><span data-stu-id="259f9-116">Property</span></span>|<span data-ttu-id="259f9-117">描述</span><span class="sxs-lookup"><span data-stu-id="259f9-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="259f9-118"><xref:System.Windows.Forms.DataGrid.BackColor%2A>属性定义网格中偶数行的颜色。</span><span class="sxs-lookup"><span data-stu-id="259f9-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="259f9-119">如果将属性设置 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 为其他颜色，则每个其他行都设置为此新颜色 (第1、3、5) 的行。</span><span class="sxs-lookup"><span data-stu-id="259f9-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="259f9-120">网格中偶数行的背景色 (第0、2、4、6) 行。</span><span class="sxs-lookup"><span data-stu-id="259f9-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="259f9-121"><xref:System.Windows.Forms.DataGrid.BackColor%2A>和 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 属性确定网格中的行颜色，而 <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> 属性则确定 nonrow 区域的颜色，该颜色仅在网格滚动到底部时可见，或在网格中只包含几行时可见。</span><span class="sxs-lookup"><span data-stu-id="259f9-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="259f9-122">网格的边框样式，其中一个 <xref:System.Windows.Forms.BorderStyle> 枚举值。</span><span class="sxs-lookup"><span data-stu-id="259f9-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="259f9-123">网格窗口标题紧上方显示的背景色。</span><span class="sxs-lookup"><span data-stu-id="259f9-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="259f9-124">网格顶部的标题的字体。</span><span class="sxs-lookup"><span data-stu-id="259f9-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="259f9-125">网格窗口标题的背景色。</span><span class="sxs-lookup"><span data-stu-id="259f9-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="259f9-126">用于在网格中显示文本的字体。</span><span class="sxs-lookup"><span data-stu-id="259f9-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="259f9-127">数据网格的行中的数据所显示的字体颜色。</span><span class="sxs-lookup"><span data-stu-id="259f9-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="259f9-128">数据网格网格线的颜色。</span><span class="sxs-lookup"><span data-stu-id="259f9-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="259f9-129">分隔网格中的单元格的行样式，是 <xref:System.Windows.Forms.DataGridLineStyle> 枚举值之一。</span><span class="sxs-lookup"><span data-stu-id="259f9-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="259f9-130">行标题和列标题的背景色。</span><span class="sxs-lookup"><span data-stu-id="259f9-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="259f9-131">列标题所用的字体。</span><span class="sxs-lookup"><span data-stu-id="259f9-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="259f9-132">网格的列标题的前景色，包括列标题文本和加/减标志符号 (在显示多个相关表时展开行) 。</span><span class="sxs-lookup"><span data-stu-id="259f9-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="259f9-133">数据网格中所有链接的文本颜色，包括指向子表的链接、关系名称，等等。</span><span class="sxs-lookup"><span data-stu-id="259f9-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="259f9-134">在子表中，这是父行的背景色。</span><span class="sxs-lookup"><span data-stu-id="259f9-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="259f9-135">在子表中，这是父行的前景色。</span><span class="sxs-lookup"><span data-stu-id="259f9-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="259f9-136">通过枚举确定是否在父行中显示表和列的名称 <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> 。</span><span class="sxs-lookup"><span data-stu-id="259f9-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="259f9-137">网格中列的默认宽度（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="259f9-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="259f9-138">在重置和属性之前设置此属性 <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> (单独或通过 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法) ，否则属性将不起作用。</span><span class="sxs-lookup"><span data-stu-id="259f9-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="259f9-139">不能将属性设置为小于0的值。</span><span class="sxs-lookup"><span data-stu-id="259f9-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="259f9-140">网格中行的行高 (以像素为单位) 。</span><span class="sxs-lookup"><span data-stu-id="259f9-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="259f9-141">在重置和属性之前设置此属性 <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> (单独或通过 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法) ，否则属性将不起作用。</span><span class="sxs-lookup"><span data-stu-id="259f9-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="259f9-142">不能将属性设置为小于0的值。</span><span class="sxs-lookup"><span data-stu-id="259f9-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="259f9-143">网格行标题的宽度。</span><span class="sxs-lookup"><span data-stu-id="259f9-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="259f9-144">选择行或单元格时，这是背景色。</span><span class="sxs-lookup"><span data-stu-id="259f9-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="259f9-145">选择行或单元格时，这是前景色。</span><span class="sxs-lookup"><span data-stu-id="259f9-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="259f9-146">请记住，在自定义控件的颜色时，可能会由于颜色选择不佳 (例如，红色和绿色) ，使控件不可访问。</span><span class="sxs-lookup"><span data-stu-id="259f9-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="259f9-147">使用 " **系统颜色** " 调色板中的可用颜色来避免此问题。</span><span class="sxs-lookup"><span data-stu-id="259f9-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="259f9-148">下面的过程假设窗体具有 <xref:System.Windows.Forms.DataGrid> 绑定到数据表的控件。</span><span class="sxs-lookup"><span data-stu-id="259f9-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="259f9-149">有关详细信息，请参阅将 [Windows 窗体 DataGrid 控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。</span><span class="sxs-lookup"><span data-stu-id="259f9-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="259f9-150">以编程方式设置数据表的表和列样式</span><span class="sxs-lookup"><span data-stu-id="259f9-150">To set the table and column style of a data table programmatically</span></span>  
  
1. <span data-ttu-id="259f9-151">创建新的表样式并设置其属性。</span><span class="sxs-lookup"><span data-stu-id="259f9-151">Create a new table style and set its properties.</span></span>  
  
2. <span data-ttu-id="259f9-152">创建列样式并设置其属性。</span><span class="sxs-lookup"><span data-stu-id="259f9-152">Create a column style and set its properties.</span></span>  
  
3. <span data-ttu-id="259f9-153">将列样式添加到表样式的列样式集合。</span><span class="sxs-lookup"><span data-stu-id="259f9-153">Add the column style to the table style's column styles collection.</span></span>  
  
4. <span data-ttu-id="259f9-154">将表样式添加到数据网格的表样式集合。</span><span class="sxs-lookup"><span data-stu-id="259f9-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5. <span data-ttu-id="259f9-155">在下面的示例中，创建新的实例 <xref:System.Windows.Forms.DataGridTableStyle> 并设置其 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="259f9-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6. <span data-ttu-id="259f9-156">创建 **GridColumnStyle** 的新实例，并将其 **MappingName** (和某些其他布局和显示属性) 。</span><span class="sxs-lookup"><span data-stu-id="259f9-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7. <span data-ttu-id="259f9-157">对于要创建的每个列样式，重复步骤2到6。</span><span class="sxs-lookup"><span data-stu-id="259f9-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="259f9-158">下面的示例演示如何 <xref:System.Windows.Forms.DataGridTextBoxColumn> 创建，因为要在列中显示一个名称。</span><span class="sxs-lookup"><span data-stu-id="259f9-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="259f9-159">此外，您还可以将该列样式添加到 <xref:System.Windows.Forms.GridColumnStylesCollection> 表样式的中，并将该表样式添加到 <xref:System.Windows.Forms.GridTableStylesCollection> 数据网格的中。</span><span class="sxs-lookup"><span data-stu-id="259f9-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName
       ' to the name of a DataColumn in the DataTable.
       ' Set the HeaderText and Width properties.
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to
       ' the GridTableStylesCollection.
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName
       // to the name of a DataColumn in the DataTable.
       // Set the HeaderText and Width properties.
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to
       // the GridTableStylesCollection.
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName
          // to the name of a DataColumn in the DataTable.
          // Set the HeaderText and Width properties.
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to
          // the GridTableStylesCollection.
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="259f9-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="259f9-160">See also</span></span>

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="259f9-161">如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列</span><span class="sxs-lookup"><span data-stu-id="259f9-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="259f9-162">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="259f9-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
