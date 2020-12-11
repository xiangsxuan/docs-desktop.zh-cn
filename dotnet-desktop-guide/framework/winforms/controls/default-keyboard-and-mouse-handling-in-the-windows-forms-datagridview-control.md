---
title: DataGridView 控件中的默认键盘和鼠标处理
ms.date: 02/13/2018
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
ms.openlocfilehash: 36defff02450b40265c9b6801380cab78eabe5f3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970107"
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的默认键盘和鼠标处理

下表介绍用户如何 <xref:System.Windows.Forms.DataGridView> 通过键盘和鼠标与控件进行交互。  
  
> [!NOTE]
> 若要自定义键盘行为，可以处理标准键盘事件，例如 <xref:System.Windows.Forms.Control.KeyDown> 。 但在编辑模式下，承载的编辑控件接收键盘输入，而不会对控件执行键盘事件 <xref:System.Windows.Forms.DataGridView> 。 若要处理编辑控件事件，请将处理程序附加到事件处理程序中的编辑控件 <xref:System.Windows.Forms.DataGridView.EditingControlShowing> 。 或者，你可以 <xref:System.Windows.Forms.DataGridView> 通过重写和方法自定义子类中的键盘行为 <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> 。  
  
## <a name="default-keyboard-handling"></a>默认键盘处理  
  
### <a name="basic-navigation-and-entry-keys"></a>基本导航和输入密钥  
  
|键或键组合|描述|  
|----------------------------|-----------------|  
|向下键|将焦点移动到当前单元格下方的单元格。 如果焦点位于最后一行，则不执行任何操作。|  
|向左键|将焦点移动到行中的上一个单元格。 如果焦点位于行的第一个单元格中，则不执行任何操作。|  
|向右键|将焦点移动到行中的下一个单元格。 如果焦点位于行的最后一个单元格中，则不执行任何操作。|  
|向上键|将焦点移动到当前单元格上方的单元格。 如果焦点位于第一行，则不执行任何操作。|  
|Home|将焦点移动到当前行中的第一个单元格。|  
|End|将焦点移动到当前行中的最后一个单元格。|  
|Page Down|将控件向下滚动显示完全显示的行数。 将焦点移到最后一个完全显示的行，而不更改列。|  
|Page Up|按完全显示的行数向上滚动控件。 将焦点移到第一个显示的行，但不更改列。|  
|Tab|如果 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 属性值为 `false` ，则将焦点移动到当前行中的下一个单元格。 如果焦点已在该行的最后一个单元格中，则将焦点移到下一行的第一个单元格。 如果焦点位于控件中的最后一个单元格，则将焦点移动到父容器的 tab 键顺序中的下一个控件。<br /><br /> 如果 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 属性值为 `true` ，则将焦点移到父容器的 tab 键顺序中的下一个控件。|  
|Shift+Tab|如果 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 属性值为 `false` ，则将焦点移动到当前行中的上一个单元格。 如果焦点已在该行的第一个单元格中，则将焦点移到上一行中的最后一个单元格。 如果焦点位于控件中的第一个单元格，则将焦点按父容器的 tab 键顺序移到上一个控件。<br /><br /> 如果 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 属性值为 `true` ，则将焦点按父容器的 tab 键顺序移到上一个控件。|  
|Ctrl+Tab|如果 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 属性值为 `false` ，则将焦点移到父容器的 tab 键顺序中的下一个控件。<br /><br /> 如果 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 属性值为 `true` ，则将焦点移动到当前行中的下一个单元格。 如果焦点已在该行的最后一个单元格中，则将焦点移到下一行的第一个单元格。 如果焦点位于控件中的最后一个单元格，则将焦点移动到父容器的 tab 键顺序中的下一个控件。|  
|Ctrl+Shift+Tab|如果 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 属性值为 `false` ，则将焦点按父容器的 tab 键顺序移到上一个控件。<br /><br /> 如果 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 属性值为 `true` ，则将焦点移动到当前行中的上一个单元格。 如果焦点已在该行的第一个单元格中，则将焦点移到上一行中的最后一个单元格。 如果焦点位于控件中的第一个单元格，则将焦点按父容器的 tab 键顺序移到上一个控件。|  
|CTRL + 箭头|将焦点移动到箭头方向上最远的单元格。|  
|Ctrl+Home|将焦点移到控件中的第一个单元格。|  
|Ctrl+End|将焦点移到控件中的最后一个单元格。|  
|CTRL + PAGE DOWN/UP|与 PAGE DOWN 或 PAGE UP 相同。|  
|F2|如果 <xref:System.Windows.Forms.DataGridView.EditMode%2A> 属性值为或，则将当前单元格置于单元编辑模式 <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2> 。|
|F3|如果属性值为，则对当前列进行排序 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> 。 这与单击当前列标题的方式相同。 自 .NET Framework 4.7.2 起可用。 若要启用此功能，应用程序必须以 .NET Framework 4.7.2 或更高版本为目标，或使用 AppContext 开关显式选择使用辅助功能改进。|  
|F4|如果当前单元格为 <xref:System.Windows.Forms.DataGridViewComboBoxCell> ，则将该单元格置于编辑模式并显示下拉列表。|  
|ALT + 向上/向下键|如果当前单元格为 <xref:System.Windows.Forms.DataGridViewComboBoxCell> ，则将该单元格置于编辑模式并显示下拉列表。|  
|SPACE|如果当前单元格是 <xref:System.Windows.Forms.DataGridViewButtonCell> 、 <xref:System.Windows.Forms.DataGridViewLinkCell> 或，则会 <xref:System.Windows.Forms.DataGridViewCheckBoxCell> 引发 <xref:System.Windows.Forms.DataGridView.CellClick> 和 <xref:System.Windows.Forms.DataGridView.CellContentClick> 事件。 如果当前单元格为 <xref:System.Windows.Forms.DataGridViewButtonCell> ，还按按钮。 如果当前单元格为 <xref:System.Windows.Forms.DataGridViewCheckBoxCell> ，还会更改检查状态。|  
|Enter|提交对当前单元格和行所做的任何更改，并将焦点移动到当前单元格正下方的单元格。 如果焦点位于最后一行，则提交所有更改，而不移动焦点。|  
|ESC|如果控件处于编辑模式，则取消编辑。 如果控件未处于编辑模式，则将还原对当前行所做的任何更改（如果控件绑定到支持编辑的数据源，或已使用行级提交范围实现了虚拟模式）。|  
|Backspace|编辑单元格时，删除插入点之前的字符。|  
|DELETE|编辑单元格时，删除插入点后的字符。|  
|Ctrl+Enter|提交对当前单元格所做的任何更改，而不移动焦点。 如果将控件绑定到支持编辑的数据源，或已使用行级提交范围实现了虚拟模式，还会提交对当前行所做的任何更改。|  
|Ctrl+0|<xref:System.DBNull.Value?displayProperty=nameWithType>如果可编辑单元格，则将值输入当前单元格。 默认情况下，单元值的显示值 <xref:System.DBNull> 为 <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> <xref:System.Windows.Forms.DataGridViewCellStyle> 当前单元格的有效属性的值。|  
  
### <a name="selection-keys"></a>选择键

 如果将 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 属性设置为 `false` <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> ，并且属性设置为，则 <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect> 使用导航键更改当前单元格会将所选内容更改为新单元。 SHIFT、CTRL 和 ALT 键不会影响此行为。  
  
 如果 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> 或 <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> ，则会发生相同的行为，但后面添加了以下内容。  
  
|键或键组合|描述|  
|----------------------------|-----------------|  
|SHIFT + 空格键|选择与单击行或列标题)  (相同的整行或列。|  
|导航键 (箭头键、PAGE UP/DOWN、HOME、END) |如果选择了一个完整的行或列，则将当前单元格更改为新的行或列会将所选内容移动到 (的新行或列，具体取决于选择模式) 。|  
  
 如果将 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 设置为 `false` 并 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 将设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 或 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> ，则通过使用键盘将当前单元格更改为新行或列时，会将所选内容移动到整个新行或列。 SHIFT、CTRL 和 ALT 键不会影响此行为。  
  
 如果 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 设置为 `true` ，则导航行为不会更改，但在按下 SHIFT 键的同时使用键盘进行导航 (包括 CTRL + SHIFT) 会修改多单元格选择。 导航开始之前，控件将当前单元标记为定位点单元。 在按 SHIFT 键的同时导航时，所选内容将包括定位点单元和当前单元格之间的所有单元格。 如果控件中的其他单元格已被选定，则将保持选中状态，但如果键盘导航暂时将其放在定位点单元和当前单元格之间，则它们可能会被取消选中。  
  
 如果将 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 设置为 `true` 并 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 将设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 或 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> ，则定位点单元和当前单元格的行为相同，但仅选择或取消选择整行或列。  
  
## <a name="default-mouse-handling"></a>默认鼠标处理
  
### <a name="basic-mouse-handling"></a>基本鼠标处理
  
> [!NOTE]
> 用鼠标左键单击某个单元格始终会更改当前单元格。 用鼠标右键单击某个单元格会打开快捷菜单（如果有）。  
  
|鼠标操作|描述|  
|------------------|-----------------|  
|鼠标左键向下键|使被单击的单元格成为当前单元格，并引发 <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> 事件。|  
|鼠标左键向上键|引发 <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType> 事件|  
|鼠标左键单击鼠标左键|引发 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> 事件|  
|按下鼠标左键，并拖动列标题单元格|如果 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 属性为 `true` ，则移动列，以便可以将其放入新位置。|  
  
### <a name="mouse-selection"></a>鼠标选择

 没有选择行为与鼠标中键或鼠标滚轮相关联。  
  
 如果 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 属性设置为， `false` 并且 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect> ，则会发生以下行为。  
  
|鼠标操作|描述|  
|------------------|-----------------|  
|单击鼠标左键|如果用户单击一个单元格，则仅选择当前单元格。 如果用户单击行标题或列标题，则没有选择行为。|  
|单击鼠标右键|显示快捷菜单（如果有）。|  
  
 当设置为或时，将出现相同的行为 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> ，但根据选择模式，单击行或列标题将选择整行或列，并将当前单元格设置为行或列中的第一个单元格。  
  
 如果 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 或 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> ，则单击行或列中的任意单元将选择整行或列。  
  
 如果 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 设置为 `true` ，则在按 CTRL 或 SHIFT 的同时单击某个单元将修改多个单元格的选择。  
  
 按下 CTRL 键的同时单击某个单元时，该单元格将更改其选择状态，而其他所有单元格都将保留其当前选择状态。  
  
 当你在按下 SHIFT 键的同时单击一个或一系列单元格时，所选内容包括当前单元格与第一次单击之前位于当前单元格位置的定位单元格之间的所有单元格。 单击并将指针拖动到多个单元格上时，定位点单元是在拖动操作开始时单击的单元格。 按下 SHIFT 键的同时单击会更改当前单元，而不是定位点单元。 如果控件中的其他单元格已选中，则该控件将保持选中状态，但如果鼠标导航暂时将其放在定位点单元和当前单元格之间，则它们可能会被取消选中。  
  
 如果将 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 设置为 `true` 并 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 将设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> 或 <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> ，则单击行标题或列标题将 (根据选择模式) ，当按下 SHIFT 键时，按下 SHIFT 将修改现有的整行或列选择。 否则，它将清除所选内容，并启动新的完整行或列选择。 但在按下 CTRL 键的同时单击行标题或列标题将在当前选定内容中添加或移除已单击的行或列，而不会修改当前所选内容。  
  
 如果将 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 设置为 `true` 并 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 将设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 或 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> ，则在按 SHIFT 或 CTRL 键的同时单击某个单元的行为方式与此相同，只不过只有完整的行和列才会受到影响。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView 控件](datagridview-control-windows-forms.md)
