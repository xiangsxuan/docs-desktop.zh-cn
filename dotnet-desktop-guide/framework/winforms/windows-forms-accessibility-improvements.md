---
title: Windows 窗体辅助功能改进
description: 了解 .NET Core Windows 窗体在与 .NET Framework Windows 窗体相比尝试改进辅助功能的方式。
ms.date: 04/20/2020
helpviewer_keywords:
- Windows Forms accessibility
- accessibility
author: M-Lipin
ms.openlocfilehash: 4dc477cebf35435ff2122ce21644135848985d07
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970515"
---
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a><span data-ttu-id="6eb5d-103">.NET Core 3.0 Windows 窗体控件中的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="6eb5d-103">Accessibility improvements in Windows Forms controls for .NET Core 3.0</span></span>

<span data-ttu-id="6eb5d-104">Windows 窗体将继续改进它与辅助功能技术的合作方式，以便更好地支持 Windows 窗体客户。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-104">Windows Forms is continuing to improve how it works with accessibility technologies to better support Windows Forms customers.</span></span> <span data-ttu-id="6eb5d-105">这些改进包括以下更改：</span><span class="sxs-lookup"><span data-stu-id="6eb5d-105">These improvements include the following changes:</span></span>

- <span data-ttu-id="6eb5d-106">与辅助功能客户端应用程序（包括讲述人）交互的各个方面的变化。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-106">Changes in various areas of interaction with accessibility client applications, including Narrator.</span></span>
- <span data-ttu-id="6eb5d-107">辅助功能层次结构中的更改（通过 UI 自动化树改进导航）。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-107">Changes in the Accessible hierarchy (improving navigation through the UI Automation tree).</span></span>
- <span data-ttu-id="6eb5d-108">键盘导航中的更改。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-108">Changes in keyboard navigation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6eb5d-109">在 .NET Core 3.0 及更高版本中，.NET Framework 4.8 .NET Framework 4.7.1 中所做的辅助功能更改包含在 .NET Core 和更高版本中，默认情况下启用。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-109">Accessibility changes made in .NET Framework 4.7.1 through .NET Framework 4.8 are included in .NET Core 3.0 and above, and are enabled by default.</span></span> <span data-ttu-id="6eb5d-110">.NET Framework 支持的兼容性开关，应用程序可以选择禁用新的辅助功能行为。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-110">The .NET Framework supported compatibility switches that allowed applications to opt out of the new accessibility behavior.</span></span> <span data-ttu-id="6eb5d-111">另一方面，.NET Core 不支持这些设置，并且不允许应用程序选择退出辅助功能行为。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-111">On the other hand, .NET Core doesn't support these settings and doesn't allow applications to opt out of accessibility behavior.</span></span>
  
<span data-ttu-id="6eb5d-112">从 .NET Core 3.0 开始，Windows 窗体的应用程序受益于 .NET Framework 4.7.1-4.8) 中引入的所有新的辅助 (功能，无需其他配置。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-112">Starting with .NET Core 3.0, Windows Forms applications benefit from all the new accessibility features (introduced in .NET Framework 4.7.1 - 4.8) without additional configuration.</span></span>

## <a name="listbox-accessibility-support"></a><span data-ttu-id="6eb5d-113">ListBox 辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="6eb5d-113">ListBox Accessibility support</span></span>

<span data-ttu-id="6eb5d-114">以下更改适用于 <xref:System.Windows.Forms.ListBox> 控件：</span><span class="sxs-lookup"><span data-stu-id="6eb5d-114">The following changes apply to the <xref:System.Windows.Forms.ListBox> control:</span></span>

- <span data-ttu-id="6eb5d-115">启用了对控件的 UI 自动化支持 `ListBox` 。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-115">Enabled UI Automation support for `ListBox` control.</span></span>
- <span data-ttu-id="6eb5d-116">`ListBox`通过添加到项并增强辅助功能支持（通过添加 <xref:System.Windows.Automation.ScrollItemPattern> 到 `ListBox` 项，并增强辅助功能事件的处理和讲述人导航）， (caps lock 导航不正确，并且不会) 无意中引发控件以外的导航。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-116">Improved `ListBox` accessibility support by adding the <xref:System.Windows.Automation.ScrollItemPattern> to `ListBox` items and by enhancing the accessibility event raising and handling and Narrator navigation through the items (caps lock navigation isn't correct and doesn't throw the navigation outside the control unintentionally).</span></span>

## <a name="checkedlistbox-accessibility-support"></a><span data-ttu-id="6eb5d-117">CheckedListBox 辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="6eb5d-117">CheckedListBox Accessibility support</span></span>

<span data-ttu-id="6eb5d-118">以下更改适用于 <xref:System.Windows.Forms.CheckedListBox> 控件：</span><span class="sxs-lookup"><span data-stu-id="6eb5d-118">The following changes apply to the <xref:System.Windows.Forms.CheckedListBox> control:</span></span>

- <span data-ttu-id="6eb5d-119">更正 `CheckedListBox` 了项的辅助功能属性提供的界限。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-119">Corrected `CheckedListBox` Bounds provided by accessibility properties for entries.</span></span>
- <span data-ttu-id="6eb5d-120">改善了整体 `ListBox` 和 `CheckedListBox` 可访问性：更正了属性值和事件模型。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-120">Improved overall `ListBox` and `CheckedListBox` accessibility: corrected property values and event model.</span></span>

## <a name="combobox-accessibility-support"></a><span data-ttu-id="6eb5d-121">ComboBox 辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="6eb5d-121">ComboBox Accessibility support</span></span>

<span data-ttu-id="6eb5d-122">以下更改适用于 <xref:System.Windows.Forms.ComboBox> 控件：</span><span class="sxs-lookup"><span data-stu-id="6eb5d-122">The following changes apply to the <xref:System.Windows.Forms.ComboBox> control:</span></span>

- <span data-ttu-id="6eb5d-123">更新了获取项的 `ComboBox` 辅助功能对象的过程，以启用项的 id，而不是从项中获取哈希代码，这在 <xref:System.Object.GetHashCode%2A> 重写函数时可能是不安全的。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-123">Updated the process of getting `ComboBox` items' accessibility objects to enable generating IDs for items instead of getting hash codes from items, which may be unsafe in case the <xref:System.Object.GetHashCode%2A> function is overridden.</span></span>

## <a name="datagridview-accessibility-support"></a><span data-ttu-id="6eb5d-124">DataGridView 辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="6eb5d-124">DataGridView Accessibility support</span></span>

<span data-ttu-id="6eb5d-125">以下更改适用于 <xref:System.Windows.Forms.DataGridView> 控件：</span><span class="sxs-lookup"><span data-stu-id="6eb5d-125">The following changes apply to the <xref:System.Windows.Forms.DataGridView> control:</span></span>

- <span data-ttu-id="6eb5d-126">已 `DataGridView.Bounds` 通过列、行、单元格和相应标头的辅助功能属性进行了更正，并改进了边框计算的性能。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-126">Corrected `DataGridView.Bounds` provided by accessibility properties for columns, rows, cells and corresponding headers, improved performance of bounding rectangle calculation.</span></span> <span data-ttu-id="6eb5d-127">所有可访问性界限均正确地表示，同时考虑整个控件的边界及其视区。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-127">All accessibility bounds are represented correctly taking into account the bounds of entire control, along with its viewport.</span></span>
- <span data-ttu-id="6eb5d-128">更正 `Value.IsReadOnly` 了为可访问的客户端应用程序提供的属性值。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-128">Corrected `Value.IsReadOnly` property value providing for accessible client applications.</span></span> <span data-ttu-id="6eb5d-129">现在，属性显示了 `IsReadOnly` 单元格的正确状态。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-129">The property now shows correct `IsReadOnly` status for cells.</span></span>
- <span data-ttu-id="6eb5d-130">修复了在 <xref:System.Windows.Forms.DataGridView.CellParsing> 第一个单元格更改时引发的事件的问题。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-130">Fixed the issue with <xref:System.Windows.Forms.DataGridView.CellParsing> event raising for the first cell change.</span></span> <span data-ttu-id="6eb5d-131">可以更改单元值，而不会出现任何问题，包括第一次 `DataGridView` 控件交互。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-131">Cell value can be changed without any issues including the first `DataGridView` control interaction.</span></span>
- <span data-ttu-id="6eb5d-132">改善了 `DataGridView` 使用 Windows 高对比度主题时的背景色对比度。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-132">Improved `DataGridView` background color contrast when using Windows High Contrast themes.</span></span> <span data-ttu-id="6eb5d-133">`DataGridView`使用 HC # 1、HC # 2 和 HC 黑色主题时，更改了默认背景色。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-133">Changed `DataGridView` default back color when using HC#1, HC#2, and HC Black themes.</span></span>

## <a name="propertygrid-accessibility-support"></a><span data-ttu-id="6eb5d-134">PropertyGrid 辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="6eb5d-134">PropertyGrid Accessibility support</span></span>

<span data-ttu-id="6eb5d-135">以下更改适用于 <xref:System.Windows.Forms.PropertyGrid> 控件：</span><span class="sxs-lookup"><span data-stu-id="6eb5d-135">The following changes apply to the <xref:System.Windows.Forms.PropertyGrid> control:</span></span>

- <span data-ttu-id="6eb5d-136">已 `PropertyGrid.Bounds` 由网格项的辅助功能属性进行了更正，并改进了边框计算的性能。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-136">Corrected `PropertyGrid.Bounds` provided by accessibility properties for grid entries, improved performance of bounding rectangle calculation.</span></span> <span data-ttu-id="6eb5d-137">现在，所有可访问性界限都可正确地表示整个控件的边界及其视区。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-137">For now all accessibility bounds are represented correctly taking into account the bounds of entire control, along with its viewport.</span></span>
- <span data-ttu-id="6eb5d-138">更正了 subcontrols 的可访问名称和说明，使其不包括控件类型名称和避免对控件类型名称进行双重公告。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-138">Corrected accessible names and descriptions of subcontrols to not include control type names and to avoid double announcement for control type names.</span></span>

## <a name="toolstrip-accessibility-support"></a><span data-ttu-id="6eb5d-139">ToolStrip 辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="6eb5d-139">ToolStrip Accessibility support</span></span>

<span data-ttu-id="6eb5d-140">以下更改适用于 <xref:System.Windows.Forms.ToolStrip> 控件：</span><span class="sxs-lookup"><span data-stu-id="6eb5d-140">The following changes apply to the <xref:System.Windows.Forms.ToolStrip> control:</span></span>

- <span data-ttu-id="6eb5d-141">改进了通过 `ToolStrip` 、 `MenuStrip` 和项的导航 `StatusStrip` 。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-141">Improved navigation through `ToolStrip`, `MenuStrip`, and `StatusStrip` items.</span></span> <span data-ttu-id="6eb5d-142">更正后的 `ToolStrip` `MenuStrip` shift tab 导航，按下 shift 键上箭头时反向循环菜单项，这将导航到底部菜单元素。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-142">Corrected `ToolStrip` and `MenuStrip` shift-tab navigation, back-looping the menu items when shift-tab up-arrow is pressed, which navigates to the bottom menu element.</span></span>
- <span data-ttu-id="6eb5d-143">改善了 `MenuStrip` 可访问的导航、更正了菜单的子菜单的可访问控件类型，以使 "menu" 类型的子菜单而不是 "MenuItem"。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-143">Improved `MenuStrip` accessible navigation, corrected menu accessible control types for submenus to make submenus of type 'Menu' instead of 'MenuItem'.</span></span>

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a><span data-ttu-id="6eb5d-144">PrintPreviewControl 和 PrintPreviewDialog 辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="6eb5d-144">PrintPreviewControl and PrintPreviewDialog Accessibility support</span></span>

<span data-ttu-id="6eb5d-145">以下更改适用于打印控件：</span><span class="sxs-lookup"><span data-stu-id="6eb5d-145">The following changes apply to the print controls:</span></span>

- <span data-ttu-id="6eb5d-146">改进的可访问导航 (包括) 通过菜单项的讲述人导航。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-146">Improved accessible navigation (including Narrator navigation) through menu items.</span></span>
- <span data-ttu-id="6eb5d-147">改进了高对比度主题支持，使控件元素更具比较。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-147">Improved High Contrast themes support and made the control element more contrasted.</span></span>

## <a name="stringcollectioneditor-accessibility-support"></a><span data-ttu-id="6eb5d-148">StringCollectionEditor 辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="6eb5d-148">StringCollectionEditor Accessibility support</span></span>

<span data-ttu-id="6eb5d-149">Windows 窗体设计器现在使用字符串集合编辑器以及改进的辅助功能支持。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-149">Windows Forms designer now uses the string collection editor with improved accessibility support.</span></span>

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a><span data-ttu-id="6eb5d-150">MonthCalendar 辅助功能支持 (在 .NET Core 3.1 中可用) </span><span class="sxs-lookup"><span data-stu-id="6eb5d-150">MonthCalendar Accessibility support (available in .NET Core 3.1)</span></span>

<span data-ttu-id="6eb5d-151">以下更改适用于 <xref:System.Windows.Forms.MonthCalendar> 控件：</span><span class="sxs-lookup"><span data-stu-id="6eb5d-151">The following changes apply to the <xref:System.Windows.Forms.MonthCalendar> control:</span></span>

- <span data-ttu-id="6eb5d-152">添加了 UI 自动化服务器提供程序以对 `MonthCalendar` Ui 自动化网格模式和表模式提供程序进行控制、添加。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-152">Added UI Automation server providers to `MonthCalendar` control, added UI Automation Grid pattern and Table pattern providers.</span></span>
- <span data-ttu-id="6eb5d-153">将 _表_ 可访问控件类型更改为 _日历_ 可访问性控件类型， `MonthCalendar` 但如果控件前面有一个定义控件可访问名称的标签控件，则这种情况除外 `MonthCalendar` ，在此特定情况下，可访问控件类型变为 _表_。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-153">Changed _table_ accessible control type to _calendar_ accessible control type for `MonthCalendar` except the case when the control has a preceding label control that defines `MonthCalendar` control accessible name, in this specific case accessible control type becomes _table_.</span></span>
- <span data-ttu-id="6eb5d-154">改善了控制所选日期的公告 `MonthCalendar` 。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-154">Improved announcement of selected date for `MonthCalendar` control.</span></span>
- <span data-ttu-id="6eb5d-155">改善了 `MonthCalendar` 对屏幕阅读器和其他辅助工具的控制支持。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-155">Improved `MonthCalendar` control support for screen readers and other accessibility tools.</span></span> <span data-ttu-id="6eb5d-156">此时，用户可以使用仅键盘输入导航控件元素，并与这些元素进行交互。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-156">At this moment, users can navigate the control elements and interact with these elements using keyboard-only input.</span></span> <span data-ttu-id="6eb5d-157">使用讲述人，使用 CAP + 箭头键导航控件元素，使用 CAP + Enter 来调用元素默认操作。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-157">With Narrator, use CAPS + arrow keys to navigation through the control elements and CAPS + Enter to invoke element default action.</span></span>
- <span data-ttu-id="6eb5d-158">跨子元素的箭头键导航改进了 `MonthCalendar` 聚焦框：讲述人的蓝色聚焦框。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-158">Improved arrow key navigation across `MonthCalendar` child elements with a focusing rectangle: blue focus rectangle for Narrator.</span></span>
- <span data-ttu-id="6eb5d-159">提高了对控件元素的命中测试操作的可访问性， `MonthCalendar` 以允许 `MonthCalendar` 通过提供的坐标获取子辅助性元素。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-159">Improved accessibility for hit test action for `MonthCalendar` control elements to allow getting `MonthCalendar` child accessible element by provided coordinates.</span></span>

## <a name="tooltips-accessibility-available-in-net-core-31"></a><span data-ttu-id="6eb5d-160">.NET Core 3.1) 中提供工具提示辅助功能 (</span><span class="sxs-lookup"><span data-stu-id="6eb5d-160">ToolTips accessibility (available in .NET Core 3.1)</span></span>

- <span data-ttu-id="6eb5d-161">添加了通过屏幕读取器应用程序（例如 NVDA 和讲述人）来公告工具提示文本的功能。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-161">Added ability to announce a tooltip text by screen reader applications such as NVDA and Narrator.</span></span> <span data-ttu-id="6eb5d-162">屏幕阅读器应用程序现在可以公布配置为显示工具提示的任何 Windows 窗体控件的键盘或鼠标工具提示文本。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-162">Screen reader application can now announce the text of keyboard or mouse tooltip of any Windows Forms control that configured to show tooltips.</span></span>

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a><span data-ttu-id="6eb5d-163">对 DataGridView、PropertyGrid、ListBox、ComboBox、ToolStrip 和其他控件的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="6eb5d-163">UI automation support for DataGridView, PropertyGrid, ListBox, ComboBox, ToolStrip, and other controls</span></span>

<span data-ttu-id="6eb5d-164">在运行时为控件启用 UI 自动化支持，但在设计时不使用。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-164">UI Automation support is enabled for controls at runtime but isn't used during design time.</span></span> <span data-ttu-id="6eb5d-165">有关 UI 自动化的概述，请参阅 [UI 自动化概述](/dotnet/framework/ui-automation/ui-automation-overview)。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-165">For an overview of UI automation, see the [UI Automation Overview](/dotnet/framework/ui-automation/ui-automation-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="6eb5d-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6eb5d-166">See also</span></span>

- <span data-ttu-id="6eb5d-167">[辅助功能最佳实践](/dotnet/framework/ui-automation/accessibility-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="6eb5d-167">[Accessibility Best Practices](/dotnet/framework/ui-automation/accessibility-best-practices).</span></span>
