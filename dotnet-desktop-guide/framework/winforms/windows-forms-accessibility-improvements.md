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
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a>.NET Core 3.0 Windows 窗体控件中的辅助功能改进

Windows 窗体将继续改进它与辅助功能技术的合作方式，以便更好地支持 Windows 窗体客户。 这些改进包括以下更改：

- 与辅助功能客户端应用程序（包括讲述人）交互的各个方面的变化。
- 辅助功能层次结构中的更改（通过 UI 自动化树改进导航）。
- 键盘导航中的更改。

> [!IMPORTANT]
> 在 .NET Core 3.0 及更高版本中，.NET Framework 4.8 .NET Framework 4.7.1 中所做的辅助功能更改包含在 .NET Core 和更高版本中，默认情况下启用。 .NET Framework 支持的兼容性开关，应用程序可以选择禁用新的辅助功能行为。 另一方面，.NET Core 不支持这些设置，并且不允许应用程序选择退出辅助功能行为。
  
从 .NET Core 3.0 开始，Windows 窗体的应用程序受益于 .NET Framework 4.7.1-4.8) 中引入的所有新的辅助 (功能，无需其他配置。

## <a name="listbox-accessibility-support"></a>ListBox 辅助功能支持

以下更改适用于 <xref:System.Windows.Forms.ListBox> 控件：

- 启用了对控件的 UI 自动化支持 `ListBox` 。
- `ListBox`通过添加到项并增强辅助功能支持（通过添加 <xref:System.Windows.Automation.ScrollItemPattern> 到 `ListBox` 项，并增强辅助功能事件的处理和讲述人导航）， (caps lock 导航不正确，并且不会) 无意中引发控件以外的导航。

## <a name="checkedlistbox-accessibility-support"></a>CheckedListBox 辅助功能支持

以下更改适用于 <xref:System.Windows.Forms.CheckedListBox> 控件：

- 更正 `CheckedListBox` 了项的辅助功能属性提供的界限。
- 改善了整体 `ListBox` 和 `CheckedListBox` 可访问性：更正了属性值和事件模型。

## <a name="combobox-accessibility-support"></a>ComboBox 辅助功能支持

以下更改适用于 <xref:System.Windows.Forms.ComboBox> 控件：

- 更新了获取项的 `ComboBox` 辅助功能对象的过程，以启用项的 id，而不是从项中获取哈希代码，这在 <xref:System.Object.GetHashCode%2A> 重写函数时可能是不安全的。

## <a name="datagridview-accessibility-support"></a>DataGridView 辅助功能支持

以下更改适用于 <xref:System.Windows.Forms.DataGridView> 控件：

- 已 `DataGridView.Bounds` 通过列、行、单元格和相应标头的辅助功能属性进行了更正，并改进了边框计算的性能。 所有可访问性界限均正确地表示，同时考虑整个控件的边界及其视区。
- 更正 `Value.IsReadOnly` 了为可访问的客户端应用程序提供的属性值。 现在，属性显示了 `IsReadOnly` 单元格的正确状态。
- 修复了在 <xref:System.Windows.Forms.DataGridView.CellParsing> 第一个单元格更改时引发的事件的问题。 可以更改单元值，而不会出现任何问题，包括第一次 `DataGridView` 控件交互。
- 改善了 `DataGridView` 使用 Windows 高对比度主题时的背景色对比度。 `DataGridView`使用 HC # 1、HC # 2 和 HC 黑色主题时，更改了默认背景色。

## <a name="propertygrid-accessibility-support"></a>PropertyGrid 辅助功能支持

以下更改适用于 <xref:System.Windows.Forms.PropertyGrid> 控件：

- 已 `PropertyGrid.Bounds` 由网格项的辅助功能属性进行了更正，并改进了边框计算的性能。 现在，所有可访问性界限都可正确地表示整个控件的边界及其视区。
- 更正了 subcontrols 的可访问名称和说明，使其不包括控件类型名称和避免对控件类型名称进行双重公告。

## <a name="toolstrip-accessibility-support"></a>ToolStrip 辅助功能支持

以下更改适用于 <xref:System.Windows.Forms.ToolStrip> 控件：

- 改进了通过 `ToolStrip` 、 `MenuStrip` 和项的导航 `StatusStrip` 。 更正后的 `ToolStrip` `MenuStrip` shift tab 导航，按下 shift 键上箭头时反向循环菜单项，这将导航到底部菜单元素。
- 改善了 `MenuStrip` 可访问的导航、更正了菜单的子菜单的可访问控件类型，以使 "menu" 类型的子菜单而不是 "MenuItem"。

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a>PrintPreviewControl 和 PrintPreviewDialog 辅助功能支持

以下更改适用于打印控件：

- 改进的可访问导航 (包括) 通过菜单项的讲述人导航。
- 改进了高对比度主题支持，使控件元素更具比较。

## <a name="stringcollectioneditor-accessibility-support"></a>StringCollectionEditor 辅助功能支持

Windows 窗体设计器现在使用字符串集合编辑器以及改进的辅助功能支持。

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a>MonthCalendar 辅助功能支持 (在 .NET Core 3.1 中可用) 

以下更改适用于 <xref:System.Windows.Forms.MonthCalendar> 控件：

- 添加了 UI 自动化服务器提供程序以对 `MonthCalendar` Ui 自动化网格模式和表模式提供程序进行控制、添加。
- 将 _表_ 可访问控件类型更改为 _日历_ 可访问性控件类型， `MonthCalendar` 但如果控件前面有一个定义控件可访问名称的标签控件，则这种情况除外 `MonthCalendar` ，在此特定情况下，可访问控件类型变为 _表_。
- 改善了控制所选日期的公告 `MonthCalendar` 。
- 改善了 `MonthCalendar` 对屏幕阅读器和其他辅助工具的控制支持。 此时，用户可以使用仅键盘输入导航控件元素，并与这些元素进行交互。 使用讲述人，使用 CAP + 箭头键导航控件元素，使用 CAP + Enter 来调用元素默认操作。
- 跨子元素的箭头键导航改进了 `MonthCalendar` 聚焦框：讲述人的蓝色聚焦框。
- 提高了对控件元素的命中测试操作的可访问性， `MonthCalendar` 以允许 `MonthCalendar` 通过提供的坐标获取子辅助性元素。

## <a name="tooltips-accessibility-available-in-net-core-31"></a>.NET Core 3.1) 中提供工具提示辅助功能 (

- 添加了通过屏幕读取器应用程序（例如 NVDA 和讲述人）来公告工具提示文本的功能。 屏幕阅读器应用程序现在可以公布配置为显示工具提示的任何 Windows 窗体控件的键盘或鼠标工具提示文本。

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a>对 DataGridView、PropertyGrid、ListBox、ComboBox、ToolStrip 和其他控件的 UI 自动化支持

在运行时为控件启用 UI 自动化支持，但在设计时不使用。 有关 UI 自动化的概述，请参阅 [UI 自动化概述](/dotnet/framework/ui-automation/ui-automation-overview)。

## <a name="see-also"></a>另请参阅

- [辅助功能最佳实践](/dotnet/framework/ui-automation/accessibility-best-practices)。
