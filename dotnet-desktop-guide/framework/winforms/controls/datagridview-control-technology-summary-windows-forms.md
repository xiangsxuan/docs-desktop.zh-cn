---
title: DataGridView 控件技术摘要
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: 1b620cabb756fadb8468fc75879025131e4bffd8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970114"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a><span data-ttu-id="abba5-102">DataGridView 控件技术摘要（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="abba5-102">DataGridView Control Technology Summary (Windows Forms)</span></span>

<span data-ttu-id="abba5-103">本主题概述了 `DataGridView` 控件及支持其使用的类的相关信息。</span><span class="sxs-lookup"><span data-stu-id="abba5-103">This topic summarizes information about the `DataGridView` control and the classes that support its use.</span></span>  
  
 <span data-ttu-id="abba5-104">以表格格式显示数据是您可能经常要执行的任务。</span><span class="sxs-lookup"><span data-stu-id="abba5-104">Displaying data in a tabular format is a task you are likely to perform frequently.</span></span> <span data-ttu-id="abba5-105">`DataGridView`控件设计为在网格中显示数据的完整解决方案。</span><span class="sxs-lookup"><span data-stu-id="abba5-105">The `DataGridView` control is designed to be a complete solution for presenting data in a grid.</span></span>  
  
## <a name="keywords"></a><span data-ttu-id="abba5-106">关键字</span><span class="sxs-lookup"><span data-stu-id="abba5-106">Keywords</span></span>  

 <span data-ttu-id="abba5-107">DataGridView、BindingSource、表、单元格、数据绑定、虚拟模式</span><span class="sxs-lookup"><span data-stu-id="abba5-107">DataGridView, BindingSource, table, cell, data binding, virtual mode</span></span>  
  
## <a name="namespaces"></a><span data-ttu-id="abba5-108">命名空间</span><span class="sxs-lookup"><span data-stu-id="abba5-108">Namespaces</span></span>  

 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a><span data-ttu-id="abba5-109">相关技术</span><span class="sxs-lookup"><span data-stu-id="abba5-109">Related Technologies</span></span>  

 `BindingSource`  
  
## <a name="background"></a><span data-ttu-id="abba5-110">背景</span><span class="sxs-lookup"><span data-stu-id="abba5-110">Background</span></span>  

 <span data-ttu-id="abba5-111">用户界面 (UI) 设计器经常发现向用户显示表格数据是必要的。</span><span class="sxs-lookup"><span data-stu-id="abba5-111">User interface (UI) designers frequently find it necessary to display tabular data to users.</span></span> <span data-ttu-id="abba5-112">.NET Framework 提供了几种在表或网格中显示数据的方式。</span><span class="sxs-lookup"><span data-stu-id="abba5-112">The .NET Framework provides several ways to show data in a table or grid.</span></span> <span data-ttu-id="abba5-113">`DataGridView`控件表示此技术对 Windows 窗体应用程序的最新演变。</span><span class="sxs-lookup"><span data-stu-id="abba5-113">The `DataGridView` control represents the latest evolution of this technology for Windows Forms applications.</span></span>  
  
 <span data-ttu-id="abba5-114">`DataGridView`控件可以显示数据存储中的数据行。</span><span class="sxs-lookup"><span data-stu-id="abba5-114">The `DataGridView` control can display rows of data from a data store.</span></span> <span data-ttu-id="abba5-115">支持多种类型的数据存储。</span><span class="sxs-lookup"><span data-stu-id="abba5-115">Many types of data stores are supported.</span></span> <span data-ttu-id="abba5-116">数据存储可以保存简单的非类型化数据（如一维数组），也可以保存类型化数据，如 <xref:System.Data.DataSet> 。</span><span class="sxs-lookup"><span data-stu-id="abba5-116">The data store can hold simple, untyped data, such as a one-dimensional array, or it can hold typed data, such as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="abba5-117">有关详细信息，请参阅 [如何：将数据绑定到 Windows 窗体 DataGridView 控件](how-to-bind-data-to-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="abba5-117">For more information, see [How to: Bind Data to the Windows Forms DataGridView Control](how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="abba5-118">`DataGridView` 控件提供一种以表格格式显示数据的功能强大且灵活的方法。</span><span class="sxs-lookup"><span data-stu-id="abba5-118">The `DataGridView` control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="abba5-119">可以使用控件显示小型到非常大的数据集的只读或可编辑视图。</span><span class="sxs-lookup"><span data-stu-id="abba5-119">You can use the control to show read-only or editable views of small to very large sets of data.</span></span>  
  
 <span data-ttu-id="abba5-120">你可以 `DataGridView` 通过多种方式扩展该控件，以将自定义行为构建到你的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="abba5-120">You can extend the `DataGridView` control in several ways to build custom behavior into your applications.</span></span> <span data-ttu-id="abba5-121">例如，可以以编程方式指定自己的排序算法，并且可以创建自己的单元格类型。</span><span class="sxs-lookup"><span data-stu-id="abba5-121">For example, you can programmatically specify your own sorting algorithms, and you can create your own types of cells.</span></span> <span data-ttu-id="abba5-122">可以通过在多个属性之间进行选择来轻松地自定义 `DataGridView` 控件的外观。</span><span class="sxs-lookup"><span data-stu-id="abba5-122">You can easily customize the appearance of the `DataGridView` control by choosing among several properties.</span></span> <span data-ttu-id="abba5-123">许多类型的数据存储区都可以用作数据源，也可以在 `DataGridView` 没有绑定数据源的情况下操作控件。</span><span class="sxs-lookup"><span data-stu-id="abba5-123">Many types of data stores can be used as a data source, or the `DataGridView` control can operate without a data source bound to it.</span></span>  
  
## <a name="implementing-datagridview-classes"></a><span data-ttu-id="abba5-124">实现 DataGridView 类</span><span class="sxs-lookup"><span data-stu-id="abba5-124">Implementing DataGridView Classes</span></span>  

 <span data-ttu-id="abba5-125">可以通过多种方式利用 `DataGridView` 控件的扩展性功能。</span><span class="sxs-lookup"><span data-stu-id="abba5-125">There are several ways for you to take advantage of the `DataGridView` control's extensibility features.</span></span> <span data-ttu-id="abba5-126">您可以通过事件和属性来自定义控件的许多方面，但某些自定义要求您创建从现有类派生的新类 `DataGridView` 。</span><span class="sxs-lookup"><span data-stu-id="abba5-126">You can customize many aspects of the control through events and properties, but some customizations require you to create new classes derived from existing `DataGridView` classes.</span></span>  
  
 <span data-ttu-id="abba5-127">最常使用的基类有 `DataGridViewCell` 和 `DataGridViewColumn` 。</span><span class="sxs-lookup"><span data-stu-id="abba5-127">The most typically used base classes are `DataGridViewCell` and `DataGridViewColumn`.</span></span> <span data-ttu-id="abba5-128">你可以从 `DataGridViewCell` 或其任意子类派生你自己的单元格类。</span><span class="sxs-lookup"><span data-stu-id="abba5-128">You can derive your own cell class from `DataGridViewCell` or any of its child classes.</span></span> <span data-ttu-id="abba5-129">虽然您可以向任何列添加任何单元格类型，但在默认情况下，您通常还会从 `DataGridViewColumn` 该自定义单元格类型的单元格派生一个伴随列类。</span><span class="sxs-lookup"><span data-stu-id="abba5-129">Although you can add any cell type to any column, you will typically also derive a companion column class from `DataGridViewColumn` that hosts cells of your custom cell type by default.</span></span>  
  
 <span data-ttu-id="abba5-130">您可以 `IDataGridViewEditingCell` 在派生的 cell 类中实现接口，以创建具有编辑功能但未在编辑模式下承载控件的单元类型。</span><span class="sxs-lookup"><span data-stu-id="abba5-130">You can implement the `IDataGridViewEditingCell` interface in your derived cell class to create a cell type that has editing functionality but does not host a control in editing mode.</span></span> <span data-ttu-id="abba5-131">若要创建可在编辑模式中承载的控件，可以在派生自的类中实现该 `IDataGridViewEditingControl` 接口 <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="abba5-131">To create a control that you can host in a cell in editing mode, you can implement the `IDataGridViewEditingControl` interface in a class derived from <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="abba5-132">有关详细信息，请参阅 [如何：自定义 Windows 窗体 DataGridView 控件中的单元格和列，方法是扩展其行为和外观](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) ，以及 [如何：在 Windows 窗体 DataGridView 单元格中承载控件](how-to-host-controls-in-windows-forms-datagridview-cells.md)。</span><span class="sxs-lookup"><span data-stu-id="abba5-132">For more information, see [How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) and [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
## <a name="datagridview-classes-at-a-glance"></a><span data-ttu-id="abba5-133">DataGridView 类一览</span><span class="sxs-lookup"><span data-stu-id="abba5-133">DataGridView Classes at a Glance</span></span>  

 <xref:System.Windows.Forms>  
  
|<span data-ttu-id="abba5-134">技术范围</span><span class="sxs-lookup"><span data-stu-id="abba5-134">Technology Area</span></span>|<span data-ttu-id="abba5-135">类/接口/配置元素</span><span class="sxs-lookup"><span data-stu-id="abba5-135">Classes/interfaces/configuration elements</span></span>|  
|---------------------|-------------------------------------------------|  
|<span data-ttu-id="abba5-136">数据绑定</span><span class="sxs-lookup"><span data-stu-id="abba5-136">Data Binding</span></span>|<xref:System.Windows.Forms.BindingSource>|  
|<span data-ttu-id="abba5-137">数据显示</span><span class="sxs-lookup"><span data-stu-id="abba5-137">Data Presentation</span></span>|<xref:System.Windows.Forms.DataGridView><br /><br /> <span data-ttu-id="abba5-138"><xref:System.Windows.Forms.DataGridViewCell> 和派生类</span><span class="sxs-lookup"><span data-stu-id="abba5-138"><xref:System.Windows.Forms.DataGridViewCell> and derived classes</span></span><br /><br /> <span data-ttu-id="abba5-139"><xref:System.Windows.Forms.DataGridViewRow> 和派生类</span><span class="sxs-lookup"><span data-stu-id="abba5-139"><xref:System.Windows.Forms.DataGridViewRow> and derived classes</span></span><br /><br /> <span data-ttu-id="abba5-140"><xref:System.Windows.Forms.DataGridViewColumn> 和派生类</span><span class="sxs-lookup"><span data-stu-id="abba5-140"><xref:System.Windows.Forms.DataGridViewColumn> and derived classes</span></span><br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<span data-ttu-id="abba5-141"><xref:System.Windows.Forms.DataGridView> 扩展性</span><span class="sxs-lookup"><span data-stu-id="abba5-141"><xref:System.Windows.Forms.DataGridView> Extensibility</span></span>|<span data-ttu-id="abba5-142"><xref:System.Windows.Forms.DataGridViewCell> 和派生类</span><span class="sxs-lookup"><span data-stu-id="abba5-142"><xref:System.Windows.Forms.DataGridViewCell> and derived classes</span></span><br /><br /> <span data-ttu-id="abba5-143"><xref:System.Windows.Forms.DataGridViewColumn> 和派生类</span><span class="sxs-lookup"><span data-stu-id="abba5-143"><xref:System.Windows.Forms.DataGridViewColumn> and derived classes</span></span><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a><span data-ttu-id="abba5-144">新增功能</span><span class="sxs-lookup"><span data-stu-id="abba5-144">What's New</span></span>  

 <span data-ttu-id="abba5-145"><xref:System.Windows.Forms.DataGridView>控件旨在作为使用 Windows 窗体显示表格数据的完整解决方案。</span><span class="sxs-lookup"><span data-stu-id="abba5-145">The <xref:System.Windows.Forms.DataGridView> control is designed to be a complete solution for displaying tabular data with Windows Forms.</span></span> <span data-ttu-id="abba5-146">在 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGrid> 创作新应用程序时，应考虑在其他解决方案（例如）上使用控件。</span><span class="sxs-lookup"><span data-stu-id="abba5-146">You should consider using the <xref:System.Windows.Forms.DataGridView> control before other solutions, such as <xref:System.Windows.Forms.DataGrid>, when you are authoring a new application.</span></span> <span data-ttu-id="abba5-147">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="abba5-147">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="abba5-148"><xref:System.Windows.Forms.DataGridView>控件可以与组件紧密配合工作 <xref:System.Windows.Forms.BindingSource> 。</span><span class="sxs-lookup"><span data-stu-id="abba5-148">The <xref:System.Windows.Forms.DataGridView> control can work in close conjunction with the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="abba5-149">此组件设计为窗体的主数据源。</span><span class="sxs-lookup"><span data-stu-id="abba5-149">This component is designed to be the primary data source of a form.</span></span> <span data-ttu-id="abba5-150">它可以管理 <xref:System.Windows.Forms.DataGridView> 控件与其数据源之间的交互，而不考虑数据源类型。</span><span class="sxs-lookup"><span data-stu-id="abba5-150">It can manage the interaction between a <xref:System.Windows.Forms.DataGridView> control and its data source, regardless of the data source type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abba5-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abba5-151">See also</span></span>

- [<span data-ttu-id="abba5-152">DataGridView 控件概述</span><span class="sxs-lookup"><span data-stu-id="abba5-152">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="abba5-153">DataGridView 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="abba5-153">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="abba5-154">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="abba5-154">Protecting Connection Information</span></span>](/dotnet/framework/data/adonet/protecting-connection-information)
