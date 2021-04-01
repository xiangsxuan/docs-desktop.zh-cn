---
title: DataGrid 控件中的默认键盘和鼠标行为
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid [WPF], keyboard behavior
- DataGrid [WPF], mouse behavior
- keyboard behavior [WPF], DataGrid
- mouse behavior [WPF], DataGrid
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
ms.openlocfilehash: a518c6123b21ae62742071a0b26c6a09fa272b17
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970948"
---
# <a name="default-keyboard-and-mouse-behavior-in-the-datagrid-control"></a>DataGrid 控件中的默认键盘和鼠标行为
本主题介绍用户如何 <xref:System.Windows.Controls.DataGrid> 使用键盘和鼠标与控件交互。  
  
 与的典型交互 <xref:System.Windows.Controls.DataGrid> 包括导航、选择和编辑。 选择行为受 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 和属性的影响 <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> 。 导致本主题中描述的行为的默认值为 <xref:System.Windows.Controls.DataGridSelectionMode.Extended?displayProperty=nameWithType> 和 <xref:System.Windows.Controls.DataGridSelectionUnit.FullRow?displayProperty=nameWithType> 。 更改这些值可能会导致行为与所述行为不同。 当单元格处于编辑模式时，编辑控件可能会重写的标准键盘行为 <xref:System.Windows.Controls.DataGrid> 。  
  
## <a name="default-keyboard-behavior"></a>默认键盘行为  
 下表列出了的默认键盘行为 <xref:System.Windows.Controls.DataGrid> 。  
  
|键或键组合|说明|  
|----------------------------|-----------------|  
|向下键|将焦点移动到当前单元格下方的单元格。 如果焦点位于最后一行，则按向下键不会执行任何操作。|  
|向上键|将焦点移动到当前单元格上方的单元格。 如果焦点位于第一行，则按向上键将不执行任何操作。|  
|向左键|将焦点移动到行中的上一个单元格。 如果焦点位于行中的第一个单元格，则按向左键将不执行任何操作。|  
|向右键|将焦点移动到行中的下一个单元格。 如果焦点位于行的最后一个单元格中，则按向右箭头不执行任何操作。|  
|Home|将焦点移动到当前行中的第一个单元格。|  
|End|将焦点移动到当前行中的最后一个单元格。|  
|Page Down|如果未对行进行分组，则将控件向下滚动显示完全显示的行数。 将焦点移到最后一个完全显示的行，而不更改列。<br /><br /> 如果对行进行分组，则将焦点移到中的最后一行， <xref:System.Windows.Controls.DataGrid> 而不更改列。|  
|Page Up|如果行未分组，则将控件向上滚动显示完全显示的行数。 将焦点移到第一个显示的行，但不更改列。<br /><br /> 如果对行进行分组，则将焦点移到中的第一行（ <xref:System.Windows.Controls.DataGrid> 不更改列）。|  
|Tab|将焦点移动到当前行中的下一个单元格。 如果焦点位于行的最后一个单元格中，则将焦点移到下一行的第一个单元格。 如果焦点位于控件中的最后一个单元格，则将焦点移动到父容器的 tab 键顺序中的下一个控件。<br /><br /> 如果当前单元格处于编辑模式，并且按 TAB 将导致焦点离开当前行，则对该行所做的任何更改都将在焦点更改之前提交。|  
|Shift+Tab|将焦点移动到当前行中的上一个单元格。 如果焦点已在该行的第一个单元格中，则将焦点移到上一行中的最后一个单元格。 如果焦点位于控件中的第一个单元格，则将焦点按父容器的 tab 键顺序移到上一个控件。<br /><br /> 如果当前单元格处于编辑模式，并且按 TAB 将导致焦点离开当前行，则对该行所做的任何更改都将在焦点更改之前提交。|  
|CTRL + 向下箭头|将焦点移动到当前列中的最后一个单元格。|  
|CTRL + 向上箭头|将焦点移动到当前列中的第一个单元格。|  
|Ctrl+向右键|将焦点移动到当前行中的最后一个单元格。|  
|Ctrl+向左键|将焦点移动到当前行中的第一个单元格。|  
|Ctrl+Home|将焦点移到控件中的第一个单元格。|  
|Ctrl+End|将焦点移到控件中的最后一个单元格。|  
|Ctrl+PAGE DOWN|与 PAGE DOWN 相同。|  
|Ctrl+PAGE UP|与 PAGE UP 相同。|  
|F2|如果 <xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=nameWithType> 属性为 `false` ，并且 <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=nameWithType> 属性是当前列的属性，则将 `false` 当前单元格置于单元编辑模式下。|  
|Enter|提交对当前单元格和行所做的任何更改，并将焦点移动到当前单元格正下方的单元格。 如果焦点位于最后一行，则提交所有更改，而不移动焦点。|  
|ESC|如果控件处于编辑模式，则取消编辑并恢复在控件中所做的任何更改。 如果基础数据源实现 <xref:System.ComponentModel.IEditableObject> ，则再次按 ESC 将取消整行的编辑模式。|  
|Backspace|编辑单元格时删除光标前的字符。|  
|DELETE|编辑单元格时删除光标后的字符。|  
|Ctrl+Enter|提交对当前单元格所做的任何更改，而不移动焦点。|  
|CTRL + A|如果 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 设置为 <xref:System.Windows.Controls.DataGridSelectionMode.Extended> ，则选择中的所有行 <xref:System.Windows.Controls.DataGrid> 。|  
  
## <a name="selection-keys"></a>选择键  
 如果将 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 属性设置为 <xref:System.Windows.Controls.DataGridSelectionMode.Extended> ，则导航行为不会更改，但在按下 SHIFT 键的同时使用键盘进行导航时 (包括 CTRL + SHIFT) 会修改多行选定内容。 导航开始之前，控件将当前行标记为定位行。 在按 SHIFT 键的同时导航时，所选内容包含定位点行与当前行之间的所有行。  
  
 以下选择键将修改多行选择。  
  
- SHIFT + 向下键  
  
- SHIFT + 向上键  
  
- SHIFT + Page Down  
  
- SHIFT + PAGE UP  
  
- Ctrl+Shift+向下键  
  
- Ctrl+Shift+向上键  
  
- Ctrl+Shift+Home  
  
- Ctrl+Shift+End  
  
## <a name="default-mouse-behavior"></a>默认鼠标行为  
 下表列出了的默认鼠标行为 <xref:System.Windows.Controls.DataGrid> 。  
  
|鼠标操作|说明|  
|------------------|-----------------|  
|单击未选定的行|使单击的行成为当前行，单击的单元格将当前单元格。|  
|单击当前单元|将当前的单元格置于编辑模式。|  
|拖动列标题单元|如果 <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=nameWithType> 属性为 `true` ，并且 <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=nameWithType> 属性是当前列的属性，则 `true` 移动该列，使其可以放置在新位置。|  
|拖动列标题分隔符|如果 <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> 属性为， `true` 并且属性为 <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> 当前列的属性，则 `true` 调整列的大小。|  
|双击列标题分隔符|如果 <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> 属性为 `true` ，并且属性为 <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> 当前列的属性，则 `true` 使用 <xref:System.Windows.Controls.DataGridLength.Auto%2A> 大小调整模式自动调整列的大小。|  
|单击列标题单元|如果 <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=nameWithType> 属性为 `true` ，并且 <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=nameWithType> 属性为当前列的属性，则对 `true` 列进行排序。<br /><br /> 单击已排序的列的标题将反转该列的排序方向。<br /><br /> 按住 SHIFT 键的同时单击多个列标题将按单击顺序按多个列进行排序。|  
|按住 CTRL 并单击行|如果 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 设置为，则将 <xref:System.Windows.Controls.DataGridSelectionMode.Extended> 修改不连续的多行选择。<br /><br /> 如果已选择行，则取消选择该行。|  
|按住 SHIFT 的同时单击行|如果 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 设置为，则将 <xref:System.Windows.Controls.DataGridSelectionMode.Extended> 修改连续的多行选择。|  
|单击行组标题|展开或折叠组。|  
|单击左上角的 "全选" 按钮 <xref:System.Windows.Controls.DataGrid>|如果 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 设置为 <xref:System.Windows.Controls.DataGridSelectionMode.Extended> ，则选择中的所有行 <xref:System.Windows.Controls.DataGrid> 。|  
  
## <a name="mouse-selection"></a>鼠标选择  
 如果将 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 属性设置为 <xref:System.Windows.Controls.DataGridSelectionMode.Extended> ，则在按 CTRL 或 SHIFT 键的同时单击行将修改多行选定内容。  
  
 按下 CTRL 键的同时单击某一行时，该行将更改其选择状态，而其他所有行都保留其当前选择状态。 这样做是为了选择不相邻的行。  
  
 当你在按下 SHIFT 键的同时单击某一行时，所选内容包括当前行和位于单击之前当前行位置的定位行之间的所有行。 按下 SHIFT 键的同时单击会更改当前行，而不是定位点行。 执行此操作可选择相邻行的范围。  
  
 可以组合 CTRL + SHIFT 来选择相邻行的非相邻范围。 为此，请使用 SHIFT + 单击选择第一个范围，如前文所述。 选择第一个范围的行后，使用 CTRL + 单击选择下一个范围中的第一行，然后按 CTRL + SHIFT 并单击下一个范围中的最后一行。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>
