---
title: 具有内置所有者描述支持的控件
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: a3c7b9eb2b7b19c8fe57cc656df64d0d0fdc4fdb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970173"
---
# <a name="controls-with-built-in-owner-drawing-support"></a>具有内置所有者描述支持的控件
Windows 窗体中的所有者描述（也称为自定义绘图）是一种更改特定控件的可视外观的技术。  
  
> [!NOTE]
> 本主题中的 "控件" 一词用于表示从或派生的类 <xref:System.Windows.Forms.Control> <xref:System.ComponentModel.Component> 。  
  
 通常，Windows 通过使用属性设置（例如）来自动处理绘制， <xref:System.Windows.Forms.Control.BackColor%2A> 以确定控件的外观。 使用所有者描述，可接管绘制进程，更改无法使用属性更改的外观元素。 例如，许多控件都允许设置文本的显示颜色，但仅限于一种颜色。 通过所有者描述，可执行诸如用黑色和红色分别显示部分文本等操作。  
  
 实际上，所有者描述类似于在窗体上绘制图形。 例如，您可以在窗体事件的处理程序中使用图形方法 <xref:System.Windows.Forms.Control.Paint> 来模拟 `ListBox` 控件，但您必须编写自己的代码来处理所有用户交互。 借助所有者描述，该控件可使用代码来绘制其内容，但仍保留其所有固有功能。 可使用图形方法绘制控件中的每一项，或在每一项的其他方面使用默认外观时自定义每一项的某些方面。  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Windows 窗体控件中的所有者描述  
 若要在支持所有者描述的控件中执行此功能，通常需设置一个属性并处理一个或多个事件。  
  
 支持所有者描述的大多数控件都具有 `OwnerDraw` 或 `DrawMode` 属性，用于指示控件对自身进行绘制时是否引发其绘制相关事件。  
  
 不具有 `OwnerDraw` 或 `DrawMode` 属性的控件包括 `DataGridView` 控件（提供自动发生的绘制事件）和 `ToolStrip` 事件（使用具有其自身绘制相关事件的外部呈现类绘制而成）。  
  
 有许多不同类型的绘制事件，但通常发生的典型绘制事件是在控件中绘制单个项。 事件处理程序接收一个 `EventArgs` 对象，其中包含与要绘制的项以及可用于绘制该项的工具有关的信息。 例如，此对象通常包含其父集合中的项的索引号， <xref:System.Drawing.Rectangle> 即指示该项的显示边界的，以及 <xref:System.Drawing.Graphics> 用于调用 paint 方法的对象。 对于某些事件，`EventArgs` 对象提供有关项和方法的附加信息，默认情况下可调用这些方法来绘制该项的某些方面，例如背景和聚焦框。  
  
 若要创建包含所有者描述的自定义项的可重用控件，请创建一个派生自控件类（支持所有者描述）的新类。 不需要对绘制事件进行处理，只需在新类中包含所有者描述代码，并替代相应的 `On`*EventName* 方法。 在这种情况下，务必调用基类 `On`*EventName* 方法，以便使用该控件的用户能够处理所有者描述事件并提供其他自定义内容。  
  
 以下 Windows 窗体控件在所有版本的 .NET Framework 中都支持所有者描述：  
  
- <xref:System.Windows.Forms.ListBox>  
  
- <xref:System.Windows.Forms.ComboBox>  
  
- <xref:System.Windows.Forms.MenuItem><xref:System.Windows.Forms.MainMenu>和) 使用的 <xref:System.Windows.Forms.ContextMenu> (  
  
- <xref:System.Windows.Forms.TabControl>  
  
 以下控件仅支持 .NET Framework 2.0 中的所有者描述：  
  
- <xref:System.Windows.Forms.ToolTip>  
  
- <xref:System.Windows.Forms.ListView>  
  
- <xref:System.Windows.Forms.TreeView>  
  
 以下控件支持所有者描述，并且是 .NET Framework 2.0 中的新增内容：  
  
- <xref:System.Windows.Forms.DataGridView>  
  
- <xref:System.Windows.Forms.ToolStrip>  
  
 以下各节进一步详述了以上每个控件。  
  
### <a name="listbox-and-combobox-controls"></a>ListBox 和 ComboBox 控件  
 <xref:System.Windows.Forms.ListBox>利用和 <xref:System.Windows.Forms.ComboBox> 控件，您可以在控件中绘制所有项，无论是在同一大小还是在不同大小。  
  
> [!NOTE]
> 尽管 <xref:System.Windows.Forms.CheckedListBox> 控件是从控件派生的 <xref:System.Windows.Forms.ListBox> ，但它不支持所有者描述。  
  
 若要以相同大小绘制每个项，请将 `DrawMode` 属性设置为 <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> 并处理 `DrawItem` 事件。  
  
 若要使用不同的大小绘制每个项，请将 `DrawMode` 属性设置为 <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> ，并处理 `MeasureItem` 和 `DrawItem` 事件。 使用 `MeasureItem` 事件可在项发生 `DrawItem` 事件之前指示该项的大小。  
  
 有关详细信息（包括代码示例），请参阅以下主题：  
  
- <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
- [如何：在 ComboBox 控件中创建大小可变的文本](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>MenuItem 组件  
 <xref:System.Windows.Forms.MenuItem>组件表示或组件中的单个菜单项 <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 。  
  
 若要绘制 <xref:System.Windows.Forms.MenuItem> ，请将其 `OwnerDraw` 属性设置为， `true` 并处理其 `DrawItem` 事件。 若要在发生 `DrawItem` 事件之前自定义菜单项的大小，请处理该项的 `MeasureItem` 事件。  
  
 有关详细信息（包括代码示例），请参阅以下参考主题：  
  
- <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a>TabControl 控件  
 <xref:System.Windows.Forms.TabControl>控件使您可以在控件中绘制各个选项卡。 所有者描述只影响选项卡; <xref:System.Windows.Forms.TabPage> 内容不受影响。  
  
 若要在中绘制每个选项卡 <xref:System.Windows.Forms.TabControl> ，请将 `DrawMode` 属性设置为 <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> 并处理 `DrawItem` 事件。 如果选项卡在控件中可见，则对于每个选项卡，此事件只发生一次。  
  
 有关详细信息（包括代码示例），请参阅以下参考主题：  
  
- <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a>ToolTip 组件  
 <xref:System.Windows.Forms.ToolTip>组件使您可以在显示时绘制整个工具提示。  
  
 若要绘制 <xref:System.Windows.Forms.ToolTip> ，请将其 `OwnerDraw` 属性设置为， `true` 并处理其 `Draw` 事件。 若要在事件发生之前自定义的大小 <xref:System.Windows.Forms.ToolTip> `Draw` ，请处理 `Popup` 事件，并 <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> 在事件处理程序中设置属性。  
  
 有关详细信息（包括代码示例），请参阅以下参考主题：  
  
- <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a>ListView 控件  
 <xref:System.Windows.Forms.ListView>控件使您可以在控件中绘制各个项、子项和列标题。  
  
 若要在控件中启用所有者描述，请将 `OwnerDraw` 属性设置为 `true`。  
  
 若要绘制控件中的每个项，请处理 `DrawItem` 事件。  
  
 若要在属性设置为时绘制控件中的每个子项或列标题 <xref:System.Windows.Forms.ListView.View%2A> <xref:System.Windows.Forms.View.Details> ，请处理 `DrawSubItem` 和 `DrawColumnHeader` 事件。  
  
 有关详细信息（包括代码示例），请参阅以下参考主题：  
  
- <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a>TreeView 控件  
 <xref:System.Windows.Forms.TreeView>控件使您可以在控件中绘制各个节点。  
  
 若要仅绘制每个节点中显示的文本，请将 `DrawMode` 属性设置为 <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> ，并处理 `DrawNode` 事件以绘制文本。  
  
 若要绘制每个节点的所有元素，请将 `DrawMode` 属性设置为， <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> 并处理 `DrawNode` 事件以绘制您需要的任何元素，例如文本、图标、复选框、加号和减号以及连接节点的线条。  
  
 有关详细信息（包括代码示例），请参阅以下参考主题：  
  
- <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a>DataGridView 控件  
 <xref:System.Windows.Forms.DataGridView>控件使您可以在控件中绘制单个单元和行。  
  
 若要绘制各个单元格，请处理 `CellPainting` 事件。  
  
 若要绘制各个行或行的元素，请择一/同时处理 `RowPrePaint` 和 `RowPostPaint` 事件。 `RowPrePaint` 事件发生在绘制行中的单元格之前，`RowPostPaint` 事件发生在绘制单元格之后。 可同时处理这两个事件和 `CellPainting` 事件以分别绘制行背景、各个单元格和行前景，或者可在需要的位置提供特定自定义内容并对行中的其他元素使用默认显示。  
  
 有关详细信息（包括代码示例），请参阅以下主题：  
  
- <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
- <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
- <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
- [如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
- [如何：自定义 Windows 窗体 DataGridView 控件中行的外观](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>ToolStrip 控件  
 <xref:System.Windows.Forms.ToolStrip> 使用派生控件可自定义其外观的任何方面。  
  
 若要为控件提供自定义呈现 <xref:System.Windows.Forms.ToolStrip> ，请将 `Renderer` <xref:System.Windows.Forms.ToolStrip> 、、或的属性设置 <xref:System.Windows.Forms.ToolStripManager> <xref:System.Windows.Forms.ToolStripPanel> <xref:System.Windows.Forms.ToolStripContentPanel> 为 `ToolStripRenderer` 对象，并处理类提供的多个绘制事件中的一个或多个 `ToolStripRenderer` 。 或者，将 `Renderer` 属性设置为从、或派生的类的实例 `ToolStripRenderer` ， <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 该实例 <xref:System.Windows.Forms.ToolStripSystemRenderer> 实现或重写特定的 `On` *事件名称* 方法。  
  
 有关详细信息（包括代码示例），请参阅以下主题：  
  
- <xref:System.Windows.Forms.ToolStripRenderer>  
  
- [如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
- [如何：自定义绘制 ToolStrip 控件](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>另请参阅

- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
