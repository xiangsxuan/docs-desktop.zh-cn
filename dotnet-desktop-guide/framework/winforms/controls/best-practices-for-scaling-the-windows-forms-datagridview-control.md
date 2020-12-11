---
title: 缩放 DataGridView 控件的最佳做法
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 63500a79def89510b4bc7a436abc4620a7265a79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971564"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>缩放 Windows 窗体 DataGridView 控件的最佳做法

<xref:System.Windows.Forms.DataGridView>控件旨在提供最大的可伸缩性。 如果需要显示大量数据，则应遵循本主题中所述的指导原则，以避免消耗大量内存或降低用户界面)  (UI 的响应能力。 本主题讨论下列问题：

- 有效使用单元格样式

- 有效使用快捷菜单

- 有效使用自动调整大小

- 有效使用选定的单元格、行和列集合

- 使用共享行

- 阻止不共享行

如果有特殊的性能需求，可以实现虚拟模式，并提供您自己的数据管理操作。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件中的数据显示模式](data-display-modes-in-the-windows-forms-datagridview-control.md)。

## <a name="using-cell-styles-efficiently"></a>有效使用单元格样式

每个单元格、行和列都可以有自己的样式信息。 样式信息存储在 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象中。 为许多单个元素创建单元样式对象 <xref:System.Windows.Forms.DataGridView> 可能效率低下，在处理大量数据时尤其如此。 若要避免性能影响，请遵循以下准则：

- 避免设置单个或对象的单元格样式属性 <xref:System.Windows.Forms.DataGridViewCell> <xref:System.Windows.Forms.DataGridViewRow> 。 这包括由属性指定的行对象 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 。 从行模板克隆的每个新行都将接收自己的模板单元格样式对象副本。 为了获得最大的可伸缩性，请在级别设置单元格样式属性 <xref:System.Windows.Forms.DataGridView> 。 例如，设置 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 属性而非 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> 属性。

- 如果某些单元格需要默认格式设置以外的其他格式，请 <xref:System.Windows.Forms.DataGridViewCellStyle> 在单元格组、行或列之间使用同一个实例。 避免直接 <xref:System.Windows.Forms.DataGridViewCellStyle> 在单独的单元格、行和列上设置类型的属性。 有关单元格样式共享的示例，请参阅 [如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。 还可以通过处理事件处理程序，避免在单独设置单元格样式时出现性能损失 <xref:System.Windows.Forms.DataGridView.CellFormatting> 。 有关示例，请参阅 [如何：自定义 Windows 窗体 DataGridView 控件中的数据格式](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。

- 确定单元格样式时，请使用 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> 属性，而不是 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> 属性。 <xref:System.Windows.Forms.DataGridViewCell.Style%2A>如果尚未使用属性，则访问属性会创建类的新实例 <xref:System.Windows.Forms.DataGridViewCellStyle> 。 此外，如果某些样式是从行、列或控件继承的，则此对象可能不包含该单元格的完整样式信息。 有关单元样式继承的详细信息，请参阅 [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。

## <a name="using-shortcut-menus-efficiently"></a>有效使用快捷菜单

每个单元格、行和列都可以有自己的快捷菜单。 控件中的快捷菜单由 <xref:System.Windows.Forms.DataGridView> 控件表示 <xref:System.Windows.Forms.ContextMenuStrip> 。 与单元格样式对象一样，为多个单个元素创建快捷菜单 <xref:System.Windows.Forms.DataGridView> 会对性能产生负面影响。 若要避免这种惩罚，请遵循以下准则：

- 避免为个别单元和行创建快捷菜单。 这包括行模板，在将新行添加到控件中时，会将该模板与快捷菜单一起克隆。 为了实现最大的可伸缩性，只使用控件的 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性为整个控件指定一个快捷菜单。

- 如果需要多个行或单元格的多个快捷菜单，请处理 <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> 或 <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> 事件。 这些事件使你可以自行管理快捷菜单对象，从而优化性能。

## <a name="using-automatic-resizing-efficiently"></a>有效使用自动调整大小

可以自动调整行、列和标头的大小，作为单元格内容的更改，以便显示单元格的全部内容而不进行剪辑。 更改大小调整模式还可以调整行、列和标头的大小。 若要确定正确的大小， <xref:System.Windows.Forms.DataGridView> 控件必须检查每个必须容纳的单元格的值。 处理大型数据集时，如果自动调整大小，则此分析可能会对控件的性能产生负面影响。 若要避免性能损失，请遵循以下准则：

- 避免对包含大量行的控件使用自动调整大小 <xref:System.Windows.Forms.DataGridView> 。 如果使用自动调整大小，则仅基于显示的行调整大小。 同时，只使用虚拟模式下显示的行。

  - 对于行和列，请使用 `DisplayedCells` `DisplayedCellsExceptHeaders` <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode> 、和枚举的或字段 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode> <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> 。

  - 对于行标题，请使用 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> 枚举的或 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> 字段 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> 。

- 为了实现最大的可伸缩性，请关闭自动调整大小并使用以编程方式调整大小。

有关详细信息，请参阅 [Windows 窗体 DataGridView 控件中的调整大小选项](sizing-options-in-the-windows-forms-datagridview-control.md)。

## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>有效使用选定的单元格、行和列集合

此 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 集合不能有效地执行大范围选择。 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>尽管和 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 集合的行数比典型控件中的单元更少，并且列数少于行数，但和集合也可能效率低下 <xref:System.Windows.Forms.DataGridView> 。 若要避免在使用这些集合时出现性能损失，请使用以下准则：

- 若要确定在访问集合内容之前是否选择了中的所有单元格 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> ，请检查方法的返回值 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 。 但请注意，此方法可能导致行成为非共享行。 有关更多信息，请参见下一节。

- 避免使用 <xref:System.Collections.ICollection.Count%2A> 的属性 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> 来确定所选单元格的数目。 请改用 <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> 方法并传入 <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> 值。 同样，使用 <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> 方法来确定所选元素的数目，而不是访问所选的行和列集合。

- 避免基于单元格的选择模式。 相反，请将 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 属性设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType> 。

## <a name="using-shared-rows"></a>使用共享行

在 <xref:System.Windows.Forms.DataGridView> 控件中通过共享行实现有效的内存使用。 行将共享类的实例，从而尽可能多地共享有关其外观和行为的信息 <xref:System.Windows.Forms.DataGridViewRow> 。

共享行实例可节省内存，而行可以轻松成为不共享的。 例如，每当用户直接与某个单元交互时，它的行就会成为非共享行。 由于无法避免这种情况，本主题中的准则仅在处理大量数据时才有用，且仅当用户在每次运行程序时与数据的相对较小部分交互时才有用。

如果某行的 <xref:System.Windows.Forms.DataGridView> 任何单元格包含值，则不能在未绑定控件中共享该行。 当 <xref:System.Windows.Forms.DataGridView> 控件绑定到外部数据源时，或者当您实现虚拟模式并提供自己的数据源时，单元值将存储在控件之外而不是单元对象中，从而允许共享行。

仅当行对象的所有单元格的状态都可以根据行的状态和包含单元格的列的状态确定时，才能共享该行对象。 如果更改某个单元的状态，使其无法再从其行和列的状态推导出来，则该行将无法共享。

例如，在以下任何情况下，都不能共享行：

- 该行包含选定列中的单个选定单元格。

- 该行包含一个具有 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 或属性集的单元格 <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> 。

- 该行包含 <xref:System.Windows.Forms.DataGridViewComboBoxCell> 具有其 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> 属性集的。

在绑定模式或虚拟模式下，你可以通过处理和事件提供单个单元格的工具提示和快捷菜单 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> 。

<xref:System.Windows.Forms.DataGridView>每当向添加行时，控件都将自动尝试使用共享行 <xref:System.Windows.Forms.DataGridViewRowCollection> 。 使用以下准则来确保行共享：

- 避免调用 `Add(Object[])` 方法的重载 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 和集合的方法的 `Insert(Object[])` 重载 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 。 这些重载自动创建非共享行。

- 请确保 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> 在以下情况下可以共享属性中指定的行：

  - 调用方法的 `Add()` 或 `Add(Int32)` 重载时， <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 或集合的 `Insert(Int32,Int32)` 方法的重载时 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 。

  - 增大属性的值时 <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> 。

  - 设置属性时 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> 。

- 请确保 `indexSource` 在调用 <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A> 集合的、、 <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A> <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A> 和方法时，可以共享参数 <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> 指示的行 <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 。

- 请确保在调用 `Add(DataGridViewRow)` 方法的重载 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 、 <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> 方法、 `Insert(Int32,DataGridViewRow)` 方法的重载 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> 以及集合的 <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> 方法 <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 时可以共享指定的一行或多行。

若要确定某个行是否共享，请使用 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> 方法检索行对象，然后检查该对象的 <xref:System.Windows.Forms.DataGridViewBand.Index%2A> 属性。 共享行的 <xref:System.Windows.Forms.DataGridViewBand.Index%2A> 属性值始终为–1。

## <a name="preventing-rows-from-becoming-unshared"></a>阻止不共享行

由于代码或用户操作的原因，共享行可能会成为非共享行。 为了避免对性能产生影响，应避免使行成为非共享行。 在应用程序开发过程中，可以处理 <xref:System.Windows.Forms.DataGridView.RowUnshared> 事件，以确定何时行成为非共享行。 当调试行共享问题时，这很有用。

若要防止行成为非共享行，请使用以下准则：

- 避免 <xref:System.Windows.Forms.DataGridView.Rows%2A> 使用循环为集合编制索引或循环访问集合 `foreach` 。 通常不需要直接访问行。 <xref:System.Windows.Forms.DataGridView> 对行操作的方法采用行索引参数而不是行实例。 此外，与行相关的事件的处理程序接收具有行属性的事件参数对象，您可以使用该行属性来操作行，而不会导致这些行成为非共享行。

- 如果需要访问行对象，请使用 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> 方法并传入行的实际索引。 但请注意，修改通过此方法检索到的共享行对象将修改共享此对象的所有行。 但新记录的行不会与其他行共享，因此，在您修改任何其他行时，它不会受到影响。 另请注意，共享行所表示的不同行可能具有不同的快捷菜单。 若要从共享行实例中检索正确的快捷菜单，请使用 <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> 方法并传入行的实际索引。 如果改为访问共享行的 <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> 属性，它将使用共享行索引-1，并且将不会检索正确的快捷菜单。

- 避免为集合编制索引 <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> 。 直接访问单元将导致其父行成为非共享行，并实例化一个新的 <xref:System.Windows.Forms.DataGridViewRow> 。 与单元格相关的事件的处理程序接收具有单元属性的事件参数对象，您可以使用这些属性来操作单元，而不会导致行成为非共享行。 你还可以使用 <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> 属性来检索当前单元格的行索引和列索引，而无需直接访问该单元。

- 避免基于单元格的选择模式。 这些模式会导致行成为非共享行。 相反，请将 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 属性设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType> 。

- 不要处理 <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> 事件。 这些事件会导致行成为非共享行。 此外，请不要调用 <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> 方法来引发这些事件。

- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType>当 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 属性值为、、或时，请勿访问该集合 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> 。 这将导致所有选定的行变为非共享状态。

- 不要调用 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> 方法。 此方法可能导致行成为非共享行。

- <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType>当属性值为时，请勿调用方法 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect> 。 这将导致所有行都不共享。

- <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> `false` 当其列中的相应属性设置为时，不要将单元格的或属性设置为 `true` 。 这将导致所有行都不共享。

- 不要访问 <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> 属性。 这将导致所有行都不共享。

- 不要调用方法的 `Sort(IComparer)` 重载 <xref:System.Windows.Forms.DataGridView.Sort%2A> 。 使用自定义比较器进行排序会导致所有行都不共享。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- [Windows 窗体 DataGridView 控件中的性能优化](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的虚拟模式](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的数据显示模式](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)
- [如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的大小调整选项](sizing-options-in-the-windows-forms-datagridview-control.md)
