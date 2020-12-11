---
title: GridView 概述
description: 了解 Windows Presentation Foundation ListView 控件的样式和模板。 修改 System.windows.controls.controltemplate>，为控件指定独特的外观。
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 02a2182ef1fc893107e434f431b9fbe0b3fbcd08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972955"
---
# <a name="gridview-overview"></a><span data-ttu-id="45f91-104">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="45f91-104">GridView Overview</span></span>
<span data-ttu-id="45f91-105"><xref:System.Windows.Controls.GridView> 视图模式是控件的一个视图模式 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-105"><xref:System.Windows.Controls.GridView> view mode is one of the view modes for a <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="45f91-106"><xref:System.Windows.Controls.GridView>类及其支持类使你和你的用户可以在通常使用按钮作为交互式列标题的表中查看项集合。</span><span class="sxs-lookup"><span data-stu-id="45f91-106">The <xref:System.Windows.Controls.GridView> class and its supporting classes enable you and your users to view item collections in a table that typically uses buttons as interactive column headers.</span></span> <span data-ttu-id="45f91-107">本主题介绍 <xref:System.Windows.Controls.GridView> 类并概述其用法。</span><span class="sxs-lookup"><span data-stu-id="45f91-107">This topic introduces the <xref:System.Windows.Controls.GridView> class and outlines its use.</span></span>  

<a name="DefiningaListViewthatusesGridViewView"></a>
## <a name="what-is-a-gridview-view"></a><span data-ttu-id="45f91-108">什么是 GridView 视图？</span><span class="sxs-lookup"><span data-stu-id="45f91-108">What Is a GridView View?</span></span>  
 <span data-ttu-id="45f91-109"><xref:System.Windows.Controls.GridView>视图模式通过将数据字段绑定到列并通过显示列标题来标识字段，来显示数据项的列表。</span><span class="sxs-lookup"><span data-stu-id="45f91-109">The <xref:System.Windows.Controls.GridView> view mode displays a list of data items by binding data fields to columns and by displaying a column header to identify the field.</span></span> <span data-ttu-id="45f91-110">默认 <xref:System.Windows.Controls.GridView> 样式实现按钮作为列标题。</span><span class="sxs-lookup"><span data-stu-id="45f91-110">The default <xref:System.Windows.Controls.GridView> style implements buttons as column headers.</span></span> <span data-ttu-id="45f91-111">通过使用列标题的按钮，你可以实现重要的用户交互功能;例如，用户可以单击列标题，按 <xref:System.Windows.Controls.GridView> 特定列的内容对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="45f91-111">By using buttons for column headers, you can implement important user interaction capabilities; for example, users can click the column header to sort <xref:System.Windows.Controls.GridView> data according to the contents of a specific column.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="45f91-112"><xref:System.Windows.Controls.GridView>用于列标题的按钮控件派生自 <xref:System.Windows.Controls.Primitives.ButtonBase> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-112">The button controls that <xref:System.Windows.Controls.GridView> uses for column headers are derived from <xref:System.Windows.Controls.Primitives.ButtonBase>.</span></span>  
  
 <span data-ttu-id="45f91-113">下图显示内容的 <xref:System.Windows.Controls.GridView> 视图 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-113">The following illustration shows a <xref:System.Windows.Controls.GridView> view of <xref:System.Windows.Controls.ListView> content.</span></span>  

 ![显示 ListView 内容的 GridView 视图的屏幕截图。](./media/gridview-overview/styled-listview-content.png)  
  
 <span data-ttu-id="45f91-115"><xref:System.Windows.Controls.GridView> 列由对象表示 <xref:System.Windows.Controls.GridViewColumn> ，这些对象可以根据其内容自动调整大小。</span><span class="sxs-lookup"><span data-stu-id="45f91-115"><xref:System.Windows.Controls.GridView> columns are represented by <xref:System.Windows.Controls.GridViewColumn> objects, which can automatically size to their content.</span></span> <span data-ttu-id="45f91-116">您也可以根据需要将显式设置 <xref:System.Windows.Controls.GridViewColumn> 为特定宽度。</span><span class="sxs-lookup"><span data-stu-id="45f91-116">Optionally, you can explicitly set a <xref:System.Windows.Controls.GridViewColumn> to a specific width.</span></span> <span data-ttu-id="45f91-117">可通过拖动列标题之间的手柄重设列的大小。</span><span class="sxs-lookup"><span data-stu-id="45f91-117">You can resize columns by dragging the gripper between column headers.</span></span> <span data-ttu-id="45f91-118">你还可以动态添加、移除、替换和重新排列列，因为此功能已内置于中 <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-118">You can also dynamically add, remove, replace, and reorder columns because this functionality is built into <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="45f91-119">但是， <xref:System.Windows.Controls.GridView> 不能直接更新它所显示的数据。</span><span class="sxs-lookup"><span data-stu-id="45f91-119">However, <xref:System.Windows.Controls.GridView> cannot directly update the data that it displays.</span></span>  
  
 <span data-ttu-id="45f91-120">下面的示例演示如何定义 <xref:System.Windows.Controls.GridView> 用于显示员工数据的。</span><span class="sxs-lookup"><span data-stu-id="45f91-120">The following example shows how to define a <xref:System.Windows.Controls.GridView> that displays employee data.</span></span> <span data-ttu-id="45f91-121">在此示例中， <xref:System.Windows.Controls.ListView> 将定义 `EmployeeInfoDataSource` 为 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-121">In this example, <xref:System.Windows.Controls.ListView> defines the `EmployeeInfoDataSource` as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>.</span></span> <span data-ttu-id="45f91-122">将 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> <xref:System.Windows.Controls.GridViewColumn> 内容绑定到数据类别的属性定义 `EmployeeInfoDataSource` 。</span><span class="sxs-lookup"><span data-stu-id="45f91-122">The property definitions of <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> bind <xref:System.Windows.Controls.GridViewColumn> content to `EmployeeInfoDataSource` data categories.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="45f91-123">下图显示了上一示例创建的表格。</span><span class="sxs-lookup"><span data-stu-id="45f91-123">The following illustration shows the table that the previous example creates.</span></span> <span data-ttu-id="45f91-124">GridView 控件显示 System.windows.controls.itemscontrol.itemssource 对象中的数据：</span><span class="sxs-lookup"><span data-stu-id="45f91-124">The GridView control displays data from an ItemsSource object:</span></span>

 ![显示带有 GridView 输出的 ListView 的屏幕截图。](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>
## <a name="gridview-layout-and-style"></a><span data-ttu-id="45f91-126">GridView 布局和样式</span><span class="sxs-lookup"><span data-stu-id="45f91-126">GridView Layout and Style</span></span>  
 <span data-ttu-id="45f91-127">的列单元格和列标题 <xref:System.Windows.Controls.GridViewColumn> 具有相同的宽度。</span><span class="sxs-lookup"><span data-stu-id="45f91-127">The column cells and the column header of a <xref:System.Windows.Controls.GridViewColumn> have the same width.</span></span> <span data-ttu-id="45f91-128">默认情况下，每一列都根据其内容来调整宽度大小。</span><span class="sxs-lookup"><span data-stu-id="45f91-128">By default, each column sizes its width to fit its content.</span></span> <span data-ttu-id="45f91-129">也可以选择将列设置为固定宽度。</span><span class="sxs-lookup"><span data-stu-id="45f91-129">Optionally, you can set a column to a fixed width.</span></span>  
  
 <span data-ttu-id="45f91-130">相关的数据内容显示在水平行中。</span><span class="sxs-lookup"><span data-stu-id="45f91-130">Related data content displays in horizontal rows.</span></span> <span data-ttu-id="45f91-131">例如，在上图中，每个员工的姓氏、名字和 ID 号显示为一组，因为它们显示在一个水平行中。</span><span class="sxs-lookup"><span data-stu-id="45f91-131">For example, in the previous illustration, each employee's last name, first name, and ID number are displayed as a set because they appear in a horizontal row.</span></span>  
  
<a name="DefiningandStylingColumnsinaGridView"></a>
### <a name="defining-and-styling-columns-in-a-gridview"></a><span data-ttu-id="45f91-132">在 GridView 中定义列并设置其样式</span><span class="sxs-lookup"><span data-stu-id="45f91-132">Defining and Styling Columns in a GridView</span></span>  
 <span data-ttu-id="45f91-133">定义要在中显示的数据字段时，请 <xref:System.Windows.Controls.GridViewColumn> 使用 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 、 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 或 <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="45f91-133">When defining the data field to display in a <xref:System.Windows.Controls.GridViewColumn>, use the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>, or <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> properties.</span></span> <span data-ttu-id="45f91-134"><xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性优先于任何一个模板属性。</span><span class="sxs-lookup"><span data-stu-id="45f91-134">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property takes precedence over either of the template properties.</span></span>  
  
 <span data-ttu-id="45f91-135">若要指定的列中的内容对齐方式 <xref:System.Windows.Controls.GridView> ，请定义 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-135">To specify the alignment of content in a column of a <xref:System.Windows.Controls.GridView>, define a <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.</span></span> <span data-ttu-id="45f91-136">不要将 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 和 <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> 属性用于 <xref:System.Windows.Controls.ListView> 通过使用显示的内容 <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-136">Do not use the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> and <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> properties for <xref:System.Windows.Controls.ListView> content that is displayed by using a <xref:System.Windows.Controls.GridView>.</span></span>  
  
 <span data-ttu-id="45f91-137">若要指定列标题的模板和样式属性，请使用 <xref:System.Windows.Controls.GridView> 、 <xref:System.Windows.Controls.GridViewColumn> 和 <xref:System.Windows.Controls.GridViewColumnHeader> 类。</span><span class="sxs-lookup"><span data-stu-id="45f91-137">To specify template and style properties for column headers, use the <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn>, and <xref:System.Windows.Controls.GridViewColumnHeader> classes.</span></span> <span data-ttu-id="45f91-138">有关详细信息，请参阅 [GridView 列标题的样式和模板概述](gridview-column-header-styles-and-templates-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="45f91-138">For more information, see [GridView Column Header Styles and Templates Overview](gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
<a name="AddingVisualElementstoaGridViewView"></a>
### <a name="adding-visual-elements-to-a-gridview"></a><span data-ttu-id="45f91-139">将可视元素添加到 GridView</span><span class="sxs-lookup"><span data-stu-id="45f91-139">Adding Visual Elements to a GridView</span></span>  
 <span data-ttu-id="45f91-140">若要将视觉元素（如 <xref:System.Windows.Controls.CheckBox> 和 <xref:System.Windows.Controls.Button> 控件）添加到 <xref:System.Windows.Controls.GridView> 视图模式，请使用模板或样式。</span><span class="sxs-lookup"><span data-stu-id="45f91-140">To add visual elements, such as <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.Button> controls, to a <xref:System.Windows.Controls.GridView> view mode, use templates or styles.</span></span>  
  
 <span data-ttu-id="45f91-141">如果将可视元素显式定义为数据项，则它在中只能出现一次 <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-141">If you explicitly define a visual element as a data item, it can appear only one time in a <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="45f91-142">之所以存在此限制，是因为元素只能有一个父级，因此，只能在可视化树中出现一次。</span><span class="sxs-lookup"><span data-stu-id="45f91-142">This limitation exists because an element can have only one parent and therefore, can appear only one time in the visual tree.</span></span>  
  
<a name="StylingRowsinaGridViewView"></a>
### <a name="styling-rows-in-a-gridview"></a><span data-ttu-id="45f91-143">设置 GridView 中的行的样式</span><span class="sxs-lookup"><span data-stu-id="45f91-143">Styling Rows in a GridView</span></span>  
 <span data-ttu-id="45f91-144">使用 <xref:System.Windows.Controls.GridViewRowPresenter> 和 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 类来设置和显示的行 <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-144">Use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> classes to format and display the rows of a <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="45f91-145">有关如何在视图模式下样式行的示例 <xref:System.Windows.Controls.GridView> ，请参阅在 [实现 GridView 的 ListView 中为行样式](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md)。</span><span class="sxs-lookup"><span data-stu-id="45f91-145">For an example of how to style rows in a <xref:System.Windows.Controls.GridView> view mode, see [Style a Row in a ListView That Implements a GridView](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).</span></span>  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a><span data-ttu-id="45f91-146">使用 ItemContainerStyle 时的对齐问题</span><span class="sxs-lookup"><span data-stu-id="45f91-146">Alignment Issues When You Use ItemContainerStyle</span></span>  
 <span data-ttu-id="45f91-147">若要防止列标题和单元格之间出现对齐问题，请不要设置属性或指定一个对中的项的宽度产生影响的模板 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-147">To prevent alignment issues between column headers and cells, do not set a property or specify a template that affects the width of an item in an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>.</span></span> <span data-ttu-id="45f91-148">例如，不要设置 <xref:System.Windows.FrameworkElement.Margin%2A> 属性，或指定 <xref:System.Windows.Controls.ControlTemplate> ，将添加 <xref:System.Windows.Controls.CheckBox> 到 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 在控件上定义的 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-148">For example, do not set the <xref:System.Windows.FrameworkElement.Margin%2A> property or specify a <xref:System.Windows.Controls.ControlTemplate> that adds a <xref:System.Windows.Controls.CheckBox> to an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> that is defined on a <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="45f91-149">而是在定义视图模式的类上直接指定影响列宽的属性和模板 <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-149">Instead, specify the properties and templates that affect column width directly on classes that define a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 <span data-ttu-id="45f91-150">例如，若要 <xref:System.Windows.Controls.CheckBox> 在视图模式下将添加到行中 <xref:System.Windows.Controls.GridView> ，请将添加 <xref:System.Windows.Controls.CheckBox> 到 <xref:System.Windows.DataTemplate> ，然后将 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 属性设置为 <xref:System.Windows.DataTemplate> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-150">For example, to add a <xref:System.Windows.Controls.CheckBox> to the rows in <xref:System.Windows.Controls.GridView> view mode, add the <xref:System.Windows.Controls.CheckBox> to a <xref:System.Windows.DataTemplate>, and then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property to that <xref:System.Windows.DataTemplate>.</span></span>  
  
<a name="InteractingwithaGridViewControl"></a>
## <a name="user-interactions-with-a-gridview"></a><span data-ttu-id="45f91-151">与 GridView 的用户交互</span><span class="sxs-lookup"><span data-stu-id="45f91-151">User Interactions with a GridView</span></span>  
 <span data-ttu-id="45f91-152"><xref:System.Windows.Controls.GridView>在应用程序中使用时，用户可以与进行交互，并修改的格式设置 <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-152">When you use a <xref:System.Windows.Controls.GridView> in your application, users can interact with and modify the formatting of the <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="45f91-153">例如，用户可以对列重新排序、重设列的大小、选择表中的项以及滚动查看内容。</span><span class="sxs-lookup"><span data-stu-id="45f91-153">For example, users can reorder columns, resize a column, select items in a table, and scroll through content.</span></span> <span data-ttu-id="45f91-154">还可定义当用户单击列标题按钮时响应的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="45f91-154">You can also define an event handler that responds when a user clicks the column header button.</span></span> <span data-ttu-id="45f91-155">事件处理程序可以执行一些操作，例如，根据列的内容对中显示的数据进行排序 <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-155">The event handler can perform operations like sorting the data that is displayed in the <xref:System.Windows.Controls.GridView> according to the contents of a column.</span></span>  
  
 <span data-ttu-id="45f91-156">以下列表更详细地讨论了使用 <xref:System.Windows.Controls.GridView> 进行用户交互的功能：</span><span class="sxs-lookup"><span data-stu-id="45f91-156">The following list discusses in more detail the capabilities of using <xref:System.Windows.Controls.GridView> for user interaction:</span></span>  
  
- <span data-ttu-id="45f91-157">**使用拖放方法对列重新排序。**</span><span class="sxs-lookup"><span data-stu-id="45f91-157">**Reorder columns by using the drag-and-drop method.**</span></span>  
  
     <span data-ttu-id="45f91-158">用户可以 <xref:System.Windows.Controls.GridView> 通过在列标题上按下鼠标左键，然后将该列拖到新位置，对中的列重新排序。</span><span class="sxs-lookup"><span data-stu-id="45f91-158">Users can reorder columns in a <xref:System.Windows.Controls.GridView> by pressing the left mouse button while it is over a column header and then dragging that column to a new position.</span></span> <span data-ttu-id="45f91-159">当用户拖动列标题时，将显示标题的浮动版本以及显示列的插入位置的黑色实线。</span><span class="sxs-lookup"><span data-stu-id="45f91-159">While the user drags the column header, a floating version of the header is displayed as well as a solid black line that shows where to insert the column.</span></span>  
  
     <span data-ttu-id="45f91-160">如果要修改标题的浮动版本的默认样式，请在 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 属性设置为时，指定要触发的类型的 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-160">If you want to modify the default style for the floating version of a header, specify a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.GridViewColumnHeader> type that is triggered when the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property is set to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span> <span data-ttu-id="45f91-161">有关详细信息，请参阅[为拖动的 GridView 列标题创建样式](how-to-create-a-style-for-a-dragged-gridview-column-header.md)。</span><span class="sxs-lookup"><span data-stu-id="45f91-161">For more information, see [Create a Style for a Dragged GridView Column Header](how-to-create-a-style-for-a-dragged-gridview-column-header.md).</span></span>  
  
- <span data-ttu-id="45f91-162">**根据列的内容重设其大小。**</span><span class="sxs-lookup"><span data-stu-id="45f91-162">**Resize a column to its content.**</span></span>  
  
     <span data-ttu-id="45f91-163">用户可双击列标题右侧的手柄来根据列的内容重设其大小。</span><span class="sxs-lookup"><span data-stu-id="45f91-163">Users can double-click the gripper to the right of a column header in order to resize a column to fit its content.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="45f91-164">可以将属性设置 <xref:System.Windows.Controls.GridViewColumn.Width%2A> 为， `Double.NaN` 以生成相同的效果。</span><span class="sxs-lookup"><span data-stu-id="45f91-164">You can set the <xref:System.Windows.Controls.GridViewColumn.Width%2A> property to `Double.NaN` to produce the same effect.</span></span>  
  
- <span data-ttu-id="45f91-165">**选择行项目。**</span><span class="sxs-lookup"><span data-stu-id="45f91-165">**Select row items.**</span></span>  
  
     <span data-ttu-id="45f91-166">用户可以选择中的一个或多个项 <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-166">Users can select one or more items in a <xref:System.Windows.Controls.GridView>.</span></span>  
  
     <span data-ttu-id="45f91-167">如果要更改 <xref:System.Windows.Style> 选定项的，请参阅 [使用触发器为 ListView 中的选定项进行样式](how-to-use-triggers-to-style-selected-items-in-a-listview.md)。</span><span class="sxs-lookup"><span data-stu-id="45f91-167">If you want to change the <xref:System.Windows.Style> of a selected item, see [Use Triggers to Style Selected Items in a ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).</span></span>  
  
- <span data-ttu-id="45f91-168">**滚动查看最初未显示在屏幕上的内容。**</span><span class="sxs-lookup"><span data-stu-id="45f91-168">**Scroll to view content that is not initially visible on the screen.**</span></span>  
  
     <span data-ttu-id="45f91-169">如果的大小不足 <xref:System.Windows.Controls.GridView> 以显示所有项，用户可以使用控件提供的滚动条水平或垂直滚动 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-169">If the size of the <xref:System.Windows.Controls.GridView> is not large enough to display all the items, users can scroll horizontally or vertically by using scrollbars, which are provided by a <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="45f91-170"><xref:System.Windows.Controls.Primitives.ScrollBar>如果所有内容在特定方向上都可见，则隐藏。</span><span class="sxs-lookup"><span data-stu-id="45f91-170">A <xref:System.Windows.Controls.Primitives.ScrollBar> is hidden if all the content is visible in a specific direction.</span></span> <span data-ttu-id="45f91-171">列标题不会随着垂直滚动条滚动，但可水平滚动。</span><span class="sxs-lookup"><span data-stu-id="45f91-171">Column headers do not scroll with a vertical scroll bar, but do scroll horizontally.</span></span>  
  
- <span data-ttu-id="45f91-172">**通过单击列标题按钮与列交互。**</span><span class="sxs-lookup"><span data-stu-id="45f91-172">**Interact with columns by clicking the column header buttons.**</span></span>  
  
     <span data-ttu-id="45f91-173">如果提供了排序算法，则当用户单击列标题按钮时，可以对列中显示的数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="45f91-173">When users click a column header button, they can sort the data that is displayed in the column if you have provided a sorting algorithm.</span></span>  
  
     <span data-ttu-id="45f91-174">您可以处理 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 列标题按钮的事件，以便提供排序算法等功能。</span><span class="sxs-lookup"><span data-stu-id="45f91-174">You can handle the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for column header buttons in order to provide functionality like a sorting algorithm.</span></span> <span data-ttu-id="45f91-175">若要处理 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 单个列标题的事件，请在上设置一个事件处理程序 <xref:System.Windows.Controls.GridViewColumnHeader> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-175">To handle the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for a single column header, set an event handler on the <xref:System.Windows.Controls.GridViewColumnHeader>.</span></span> <span data-ttu-id="45f91-176">若要设置用于处理所有列标题的事件的事件处理程序 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> ，请在控件上设置处理程序 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-176">To set an event handler that handles the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for all column headers, set the handler on the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
<a name="Obtaining_Other_Custom_Views"></a>
## <a name="obtaining-other-custom-views"></a><span data-ttu-id="45f91-177">获取其他自定义视图</span><span class="sxs-lookup"><span data-stu-id="45f91-177">Obtaining Other Custom Views</span></span>  
 <span data-ttu-id="45f91-178"><xref:System.Windows.Controls.GridView>派生自 <xref:System.Windows.Controls.ViewBase> 抽象类的类只是类的可能的视图模式之一 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-178">The <xref:System.Windows.Controls.GridView> class, which is derived from the <xref:System.Windows.Controls.ViewBase> abstract class, is just one of the possible view modes for the <xref:System.Windows.Controls.ListView> class.</span></span> <span data-ttu-id="45f91-179">您可以 <xref:System.Windows.Controls.ListView> 通过从类派生来为创建其他自定义视图 <xref:System.Windows.Controls.ViewBase> 。</span><span class="sxs-lookup"><span data-stu-id="45f91-179">You can create other custom views for <xref:System.Windows.Controls.ListView> by deriving from the <xref:System.Windows.Controls.ViewBase> class.</span></span> <span data-ttu-id="45f91-180">有关自定义视图模式的示例，请参阅[为 ListView 创建自定义视图模式](how-to-create-a-custom-view-mode-for-a-listview.md)。</span><span class="sxs-lookup"><span data-stu-id="45f91-180">For an example of a custom view mode, see [Create a Custom View Mode for a ListView](how-to-create-a-custom-view-mode-for-a-listview.md).</span></span>  
  
<a name="GridViewSupportingClasses"></a>
## <a name="gridview-supporting-classes"></a><span data-ttu-id="45f91-181">GridView 支持类</span><span class="sxs-lookup"><span data-stu-id="45f91-181">GridView Supporting Classes</span></span>  
 <span data-ttu-id="45f91-182">以下类支持 <xref:System.Windows.Controls.GridView> 视图模式。</span><span class="sxs-lookup"><span data-stu-id="45f91-182">The following classes support the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
- <xref:System.Windows.Controls.GridViewColumn>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GridViewRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewColumnCollection>  
  
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a><span data-ttu-id="45f91-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45f91-183">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Controls.GridViewColumn>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.ViewBase>
- [<span data-ttu-id="45f91-184">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="45f91-184">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="45f91-185">在标题获得单击时对 GridView 列进行排序</span><span class="sxs-lookup"><span data-stu-id="45f91-185">Sort a GridView Column When a Header Is Clicked</span></span>](how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="45f91-186">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="45f91-186">How-to Topics</span></span>](listview-how-to-topics.md)