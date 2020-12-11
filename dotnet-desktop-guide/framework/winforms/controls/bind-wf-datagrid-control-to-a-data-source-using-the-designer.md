---
title: 使用设计器将 DataGrid 控件绑定到数据源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: 67e1e99f404875b9945d934ef54dea3449ef6b26
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970715"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="603fa-102">如何：使用设计器将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="603fa-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="603fa-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="603fa-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="603fa-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="603fa-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

 <span data-ttu-id="603fa-105">Windows 窗体 <xref:System.Windows.Forms.DataGrid> 控件专门用于显示数据源中的信息。</span><span class="sxs-lookup"><span data-stu-id="603fa-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="603fa-106">您可以通过设置和属性在设计时绑定 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 控件 <xref:System.Windows.Forms.DataGrid.DataMember%2A> ，或在运行时通过调用方法来绑定控件 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 。</span><span class="sxs-lookup"><span data-stu-id="603fa-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="603fa-107">尽管可以显示来自多种数据源的数据，但最常见的数据源是数据集和数据视图。</span><span class="sxs-lookup"><span data-stu-id="603fa-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>

 <span data-ttu-id="603fa-108">如果数据源在设计时可用（例如，如果窗体包含数据集或数据视图的实例），则可以在设计时将网格绑定到数据源。</span><span class="sxs-lookup"><span data-stu-id="603fa-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="603fa-109">然后，可以在网格中预览数据的外观。</span><span class="sxs-lookup"><span data-stu-id="603fa-109">You can then preview what the data will look like in the grid.</span></span>

 <span data-ttu-id="603fa-110">你还可以在运行时以编程方式绑定网格。</span><span class="sxs-lookup"><span data-stu-id="603fa-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="603fa-111">如果要基于在运行时获取的信息设置数据源，此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="603fa-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="603fa-112">例如，应用程序可能会让用户指定要查看的表的名称。</span><span class="sxs-lookup"><span data-stu-id="603fa-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="603fa-113">在设计时不存在数据源的情况下，也是必需的。</span><span class="sxs-lookup"><span data-stu-id="603fa-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="603fa-114">这包括数据源（如数组、集合、非类型化数据集和数据读取器）。</span><span class="sxs-lookup"><span data-stu-id="603fa-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>

 <span data-ttu-id="603fa-115">下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="603fa-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="603fa-116">有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="603fa-116">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="603fa-117">在 Visual Studio 2005 中， <xref:System.Windows.Forms.DataGrid> 默认情况下控件不在 **工具箱** 中。</span><span class="sxs-lookup"><span data-stu-id="603fa-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="603fa-118">有关添加它的信息，请参阅 [如何：向工具箱添加项](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="603fa-118">For information about adding it, see [How to: Add Items to the Toolbox](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span> <span data-ttu-id="603fa-119">此外，在 Visual Studio 2005 中，可以使用 " **数据源** " 窗口进行设计时数据绑定。</span><span class="sxs-lookup"><span data-stu-id="603fa-119">Additionally in Visual Studio 2005, you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="603fa-120">有关详细信息，请参阅 [在 Visual Studio 中将控件绑定到数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="603fa-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>

## <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="603fa-121">将 DataGrid 控件数据绑定到设计器中的单个表</span><span class="sxs-lookup"><span data-stu-id="603fa-121">To data-bind the DataGrid control to a single table in the designer</span></span>

1. <span data-ttu-id="603fa-122">将控件的 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 属性设置为包含要绑定到的数据项的对象。</span><span class="sxs-lookup"><span data-stu-id="603fa-122">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="603fa-123">如果数据源是一个数据集，则将 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 属性设置为要绑定到的表的名称。</span><span class="sxs-lookup"><span data-stu-id="603fa-123">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>

3. <span data-ttu-id="603fa-124">如果数据源是基于数据集表的数据集或数据视图，请将代码添加到窗体中以填充数据集。</span><span class="sxs-lookup"><span data-stu-id="603fa-124">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>

     <span data-ttu-id="603fa-125">你使用的确切代码取决于数据集获取数据的位置。</span><span class="sxs-lookup"><span data-stu-id="603fa-125">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="603fa-126">如果直接从数据库填充数据集，则通常调用 `Fill` 数据适配器的方法，如以下代码示例所示，该示例将填充名为的数据集 `DsCategories1` ：</span><span class="sxs-lookup"><span data-stu-id="603fa-126">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>

    ```vb
    sqlDataAdapter1.Fill(DsCategories1)
    ```

    ```csharp
    sqlDataAdapter1.Fill(DsCategories1);
    ```

    ```cpp
    sqlDataAdapter1->Fill(dsCategories1);
    ```

4. <span data-ttu-id="603fa-127"> (可选) 将相应的表样式和列样式添加到网格。</span><span class="sxs-lookup"><span data-stu-id="603fa-127">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>

     <span data-ttu-id="603fa-128">如果没有表样式，您将看到该表，但其格式设置和所有列都可见。</span><span class="sxs-lookup"><span data-stu-id="603fa-128">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>

## <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="603fa-129">在设计器中将 DataGrid 控件数据绑定到数据集中的多个表</span><span class="sxs-lookup"><span data-stu-id="603fa-129">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>

1. <span data-ttu-id="603fa-130">将控件的 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 属性设置为包含要绑定到的数据项的对象。</span><span class="sxs-lookup"><span data-stu-id="603fa-130">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="603fa-131">如果数据集包含相关表 (也就是说，如果它包含关系对象) ，则将属性设置 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 为父表的名称。</span><span class="sxs-lookup"><span data-stu-id="603fa-131">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>

3. <span data-ttu-id="603fa-132">编写代码以填充数据集。</span><span class="sxs-lookup"><span data-stu-id="603fa-132">Write code to fill the dataset.</span></span>

## <a name="see-also"></a><span data-ttu-id="603fa-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="603fa-133">See also</span></span>

- [<span data-ttu-id="603fa-134">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="603fa-134">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="603fa-135">如何：向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="603fa-135">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="603fa-136">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="603fa-136">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="603fa-137">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="603fa-137">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="603fa-138">在 Visual Studio 中访问数据</span><span class="sxs-lookup"><span data-stu-id="603fa-138">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
