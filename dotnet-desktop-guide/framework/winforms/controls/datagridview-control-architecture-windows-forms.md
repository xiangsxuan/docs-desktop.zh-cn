---
title: DataGridView 控件体系结构
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970129"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="76408-102">DataGridView 控件体系结构（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="76408-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="76408-103"><xref:System.Windows.Forms.DataGridView>控件及其相关的类设计为用于显示和编辑表格数据的灵活、可扩展的系统。</span><span class="sxs-lookup"><span data-stu-id="76408-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="76408-104">这些类都包含在 <xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间中，它们都是用 "DataGridView" 前缀命名的。</span><span class="sxs-lookup"><span data-stu-id="76408-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="76408-105">体系结构元素</span><span class="sxs-lookup"><span data-stu-id="76408-105">Architecture Elements</span></span>  
 <span data-ttu-id="76408-106">主 <xref:System.Windows.Forms.DataGridView> 伴生类派生自 <xref:System.Windows.Forms.DataGridViewElement> 。</span><span class="sxs-lookup"><span data-stu-id="76408-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="76408-107">以下对象模型说明了 <xref:System.Windows.Forms.DataGridViewElement> 继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="76408-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![显示 DataGridViewElement 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="76408-109"><xref:System.Windows.Forms.DataGridViewElement>类提供对父控件的引用 <xref:System.Windows.Forms.DataGridView> 并具有 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 属性，该属性包含一个值，该值表示枚举中的值的组合 <xref:System.Windows.Forms.DataGridViewElementStates> 。</span><span class="sxs-lookup"><span data-stu-id="76408-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="76408-110">以下部分 <xref:System.Windows.Forms.DataGridView> 更详细地介绍了伴生类。</span><span class="sxs-lookup"><span data-stu-id="76408-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="76408-111">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="76408-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="76408-112"><xref:System.Windows.Forms.DataGridViewElementStates> 枚举包含以下值：</span><span class="sxs-lookup"><span data-stu-id="76408-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="76408-113">此枚举的值可以与按位逻辑运算符组合在一起，因此 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 属性可以同时表示多个状态。</span><span class="sxs-lookup"><span data-stu-id="76408-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="76408-114">例如， <xref:System.Windows.Forms.DataGridViewElement> 可以同时为 <xref:System.Windows.Forms.DataGridViewElementStates.Frozen> 、 <xref:System.Windows.Forms.DataGridViewElementStates.Selected> 和 <xref:System.Windows.Forms.DataGridViewElementStates.Visible> 。</span><span class="sxs-lookup"><span data-stu-id="76408-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="76408-115">单元和带区</span><span class="sxs-lookup"><span data-stu-id="76408-115">Cells and Bands</span></span>  
 <span data-ttu-id="76408-116"><xref:System.Windows.Forms.DataGridView>控件包含两种基本类型的对象：单元格和带区。</span><span class="sxs-lookup"><span data-stu-id="76408-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="76408-117">所有单元均派生自 <xref:System.Windows.Forms.DataGridViewCell> 基类。</span><span class="sxs-lookup"><span data-stu-id="76408-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="76408-118">两种类型的带区 <xref:System.Windows.Forms.DataGridViewColumn> 和 <xref:System.Windows.Forms.DataGridViewRow> 都派生自 <xref:System.Windows.Forms.DataGridViewBand> 基类。</span><span class="sxs-lookup"><span data-stu-id="76408-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="76408-119"><xref:System.Windows.Forms.DataGridView>控件与多个类互操作，但最常遇到的是 <xref:System.Windows.Forms.DataGridViewCell> 、 <xref:System.Windows.Forms.DataGridViewColumn> 和 <xref:System.Windows.Forms.DataGridViewRow> 。</span><span class="sxs-lookup"><span data-stu-id="76408-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="76408-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="76408-120">DataGridViewCell</span></span>  
 <span data-ttu-id="76408-121">单元是的交互的基本单位 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="76408-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="76408-122">显示在单元格中居中，数据输入通常通过单元格执行。</span><span class="sxs-lookup"><span data-stu-id="76408-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="76408-123">您可以通过使用类的集合来访问单元 <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> <xref:System.Windows.Forms.DataGridViewRow> ，您可以通过使用控件的集合来访问所选单元 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="76408-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="76408-124">以下对象模型说明了这种用法，并显示了 <xref:System.Windows.Forms.DataGridViewCell> 继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="76408-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![显示 DataGridViewCell 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="76408-126"><xref:System.Windows.Forms.DataGridViewCell>类型是一个抽象基类，所有单元类型都派生自该基类。</span><span class="sxs-lookup"><span data-stu-id="76408-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="76408-127"><xref:System.Windows.Forms.DataGridViewCell> 及其派生类型不 Windows 窗体控件，而某些宿主 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="76408-127"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="76408-128">单元支持的所有编辑功能通常由寄宿控件处理。</span><span class="sxs-lookup"><span data-stu-id="76408-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="76408-129"><xref:System.Windows.Forms.DataGridViewCell> 对象不以与 Windows 窗体控件相同的方式来控制其自身的外观和绘制功能。</span><span class="sxs-lookup"><span data-stu-id="76408-129"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="76408-130">相反， <xref:System.Windows.Forms.DataGridView> 负责其对象的外观 <xref:System.Windows.Forms.DataGridViewCell> 。</span><span class="sxs-lookup"><span data-stu-id="76408-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="76408-131">通过与 <xref:System.Windows.Forms.DataGridView> 控件的属性和事件交互，可以显著影响单元格的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="76408-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="76408-132">如果对超出控件功能的自定义项有特殊要求 <xref:System.Windows.Forms.DataGridView> ，则可以实现自己的派生自 <xref:System.Windows.Forms.DataGridViewCell> 或其子类之一的类。</span><span class="sxs-lookup"><span data-stu-id="76408-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="76408-133">以下列表显示派生自的类 <xref:System.Windows.Forms.DataGridViewCell> ：</span><span class="sxs-lookup"><span data-stu-id="76408-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- <span data-ttu-id="76408-134">自定义单元类型</span><span class="sxs-lookup"><span data-stu-id="76408-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="76408-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="76408-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="76408-136"><xref:System.Windows.Forms.DataGridView>控件的附加数据存储的架构在 <xref:System.Windows.Forms.DataGridView> 控件的列中表示。</span><span class="sxs-lookup"><span data-stu-id="76408-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="76408-137">您可以 <xref:System.Windows.Forms.DataGridView> 通过使用集合来访问控件的列 <xref:System.Windows.Forms.DataGridView.Columns%2A> 。</span><span class="sxs-lookup"><span data-stu-id="76408-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="76408-138">您可以通过使用集合来访问所选列 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 。</span><span class="sxs-lookup"><span data-stu-id="76408-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="76408-139">以下对象模型说明了这种用法，并显示了 <xref:System.Windows.Forms.DataGridViewColumn> 继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="76408-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![显示 DataGridViewColumn 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="76408-141">某些键单元类型具有相应的列类型。</span><span class="sxs-lookup"><span data-stu-id="76408-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="76408-142">这些类派生自 <xref:System.Windows.Forms.DataGridViewColumn> 基类。</span><span class="sxs-lookup"><span data-stu-id="76408-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="76408-143">以下列表显示派生自的类 <xref:System.Windows.Forms.DataGridViewColumn> ：</span><span class="sxs-lookup"><span data-stu-id="76408-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- <span data-ttu-id="76408-144">自定义列类型</span><span class="sxs-lookup"><span data-stu-id="76408-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="76408-145">DataGridView 编辑控件</span><span class="sxs-lookup"><span data-stu-id="76408-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="76408-146">支持高级编辑功能的单元通常使用派生自 Windows 窗体控件的托管控件。</span><span class="sxs-lookup"><span data-stu-id="76408-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="76408-147">这些控件还实现 <xref:System.Windows.Forms.IDataGridViewEditingControl> 接口。</span><span class="sxs-lookup"><span data-stu-id="76408-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="76408-148">以下对象模型说明了这些控件的用法。</span><span class="sxs-lookup"><span data-stu-id="76408-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![显示 DataGridView 编辑控件对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="76408-150">以下编辑控件与控件一起提供 <xref:System.Windows.Forms.DataGridView> ：</span><span class="sxs-lookup"><span data-stu-id="76408-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="76408-151">有关创建自己的编辑控件的信息，请参阅 [如何：在 Windows 窗体 DataGridView 单元格中承载控件](how-to-host-controls-in-windows-forms-datagridview-cells.md)。</span><span class="sxs-lookup"><span data-stu-id="76408-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="76408-152">下表说明了单元类型、列类型和编辑控件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="76408-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="76408-153">单元类型</span><span class="sxs-lookup"><span data-stu-id="76408-153">Cell type</span></span>|<span data-ttu-id="76408-154">托管控件</span><span class="sxs-lookup"><span data-stu-id="76408-154">Hosted control</span></span>|<span data-ttu-id="76408-155">列类型</span><span class="sxs-lookup"><span data-stu-id="76408-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="76408-156">不适用</span><span class="sxs-lookup"><span data-stu-id="76408-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="76408-157">不适用</span><span class="sxs-lookup"><span data-stu-id="76408-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="76408-158">不适用</span><span class="sxs-lookup"><span data-stu-id="76408-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="76408-159">不适用</span><span class="sxs-lookup"><span data-stu-id="76408-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="76408-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="76408-160">DataGridViewRow</span></span>  
 <span data-ttu-id="76408-161"><xref:System.Windows.Forms.DataGridViewRow>类显示控件所附加到的数据存储区中的记录的数据字段 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="76408-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="76408-162">您可以 <xref:System.Windows.Forms.DataGridView> 通过使用集合来访问控件的行 <xref:System.Windows.Forms.DataGridView.Rows%2A> 。</span><span class="sxs-lookup"><span data-stu-id="76408-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="76408-163">您可以通过使用集合来访问所选行 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 。</span><span class="sxs-lookup"><span data-stu-id="76408-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="76408-164">以下对象模型说明了这种用法，并显示了 <xref:System.Windows.Forms.DataGridViewRow> 继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="76408-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![显示 DataGridViewRow 对象模型层次结构的关系图。](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="76408-166">你可以从类派生你自己的类型 <xref:System.Windows.Forms.DataGridViewRow> ，但通常不需要这样做。</span><span class="sxs-lookup"><span data-stu-id="76408-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="76408-167"><xref:System.Windows.Forms.DataGridView>控件具有几个与行相关的事件和属性，用于自定义其 <xref:System.Windows.Forms.DataGridViewRow> 对象的行为。</span><span class="sxs-lookup"><span data-stu-id="76408-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="76408-168">如果启用 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 属性，则添加新行的特殊行将显示为最后一行。</span><span class="sxs-lookup"><span data-stu-id="76408-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="76408-169">该行是集合的一部分 <xref:System.Windows.Forms.DataGridView.Rows%2A> ，但它具有可能需要注意的特殊功能。</span><span class="sxs-lookup"><span data-stu-id="76408-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="76408-170">有关详细信息，请参阅在 [Windows 窗体 DataGridView 控件中使用新记录行](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="76408-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76408-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76408-171">See also</span></span>

- [<span data-ttu-id="76408-172">DataGridView 控件概述</span><span class="sxs-lookup"><span data-stu-id="76408-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="76408-173">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="76408-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="76408-174">在 Windows 窗体 DataGridView 控件中使用新记录行</span><span class="sxs-lookup"><span data-stu-id="76408-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
