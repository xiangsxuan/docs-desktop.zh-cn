---
title: DataGridView 控件中的虚拟模式
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: 0d82f0fc9946e5b61ea171f2f5d2ab5690db0c71
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973159"
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的虚拟模式
使用虚拟模式，你可以管理 <xref:System.Windows.Forms.DataGridView> 控件和自定义数据缓存之间的交互。 若要实现虚拟模式，请将 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 属性设置为， `true` 并处理本主题中描述的一个或多个事件。 通常至少会处理 `CellValueNeeded` 事件，这使控件能够在数据缓存中查找值。  
  
## <a name="bound-mode-and-virtual-mode"></a>绑定模式和虚拟模式  
 仅当需要补充或替换绑定模式时，才需要虚拟模式。 在绑定模式下，你可以设置 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 属性，控件将自动从指定的源加载数据并将用户更改提交给它。 您可以控制显示哪些绑定列，并且数据源本身通常处理排序等操作。  
  
## <a name="supplementing-bound-mode"></a>补充绑定模式  
 您可以通过显示未绑定的列以及绑定列来补充绑定模式。 这有时称为 "混合模式"，可用于显示计算值或用户界面 (UI) 控件等。  
  
 由于未绑定的列在数据源外部，因此数据源的排序操作将忽略它们。 因此，在混合模式下启用排序时，必须在本地缓存中管理未绑定的数据，并实现虚拟模式，使 <xref:System.Windows.Forms.DataGridView> 控件能够与之进行交互。  
  
 有关使用虚拟模式来维护未绑定列中的值的详细信息，请参阅 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> 属性和 <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> 类引用主题中的示例。  
  
## <a name="replacing-bound-mode"></a>替换绑定模式  
 如果绑定模式无法满足性能需求，可以通过虚拟模式事件处理程序来管理自定义缓存中的所有数据。 例如，可以使用虚拟模式实现实时数据加载机制，该机制仅检索网络数据库中的数据，以获得最佳性能。 如果在慢速网络连接上使用大量数据，或者在 RAM 或存储空间有限的客户端计算机上工作，则此方案特别有用。  
  
 有关在实时方案中使用虚拟模式的详细信息，请参阅 [Windows 窗体 DataGridView 控件中的使用实时数据加载实现虚拟模式](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)。  
  
## <a name="virtual-mode-events"></a>Virtual-Mode 事件  
 如果数据为只读，则 `CellValueNeeded` 事件可能是需要处理的唯一事件。 利用其他虚拟模式事件，您可以启用特定功能，如用户编辑、行添加和删除以及行级事务。  
  
 一些标准 <xref:System.Windows.Forms.DataGridView> 事件 (如用户添加或删除行时发生的事件，或者单元值的编辑、分析、验证或格式化) 在虚拟模式下非常有用。 您还可以处理事件，使您能够维护通常不会存储在绑定数据源中的值，如单元工具提示文本、单元格和行错误文本、单元格和行的快捷菜单数据以及行高度数据。  
  
 若要详细了解如何实现虚拟模式来管理具有行级提交范围的读/写数据，请参阅 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。  
  
 有关使用单元级提交范围实现虚拟模式的示例，请参阅 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 属性参考主题。  
  
 仅当属性设置为时，才会发生以下事件 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> `true` 。  
  
|事件|描述|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|由控件用于从数据缓存中检索要显示的单元值。 此事件仅在未绑定列中的单元格时发生。|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|由控件用于将单元格的用户输入提交到数据缓存。 此事件仅在未绑定列中的单元格时发生。<br /><br /> <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A>在事件处理程序外更改缓存的值时调用方法 <xref:System.Windows.Forms.DataGridView.CellValuePushed> ，以确保当前值显示在控件中，并应用当前有效的任何自动调整大小模式。|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|由控件用来指示数据缓存中的新行需要。|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|由控件用来确定某行是否有任何未提交的更改。|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|由控件用来指示行应还原为其缓存的值。|  
  
 以下事件在虚拟模式下非常有用，但不管属性设置如何，都可以使用这些事件 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 。  
  
|事件|说明|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|由控件用来指示删除或添加行的时间，从而使您可以相应地更新数据缓存。|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|由控件用于设置显示的单元格值的格式，并用于分析和验证用户输入。|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|当 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 设置属性或属性为时，由控件用来检索单元工具提示文本 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> `true` 。<br /><br /> 仅当属性值为时，才会显示单元工具提示 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> `true` 。|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|当 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 设置属性或属性为时，由控件用来检索单元或行错误文本 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> `true` 。<br /><br /> 在 <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> 更改单元或行错误文本时调用方法或方法，以确保在控件中显示当前值。<br /><br /> 当 <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> 和 <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> 属性值为时，将显示单元格和行错误标志符号 `true` 。|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|<xref:System.Windows.Forms.ContextMenuStrip>当控件 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 属性已设置或 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 属性为时，由控件用来检索单元或行 `true` 。|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|由控件用来检索或存储数据缓存中的行高信息。 在 <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> 事件处理程序外更改缓存行高度信息时调用方法 <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> ，以确保在控件的显示中使用当前值。|  
  
## <a name="best-practices-in-virtual-mode"></a>虚拟模式下的最佳做法  
 如果要实现虚拟模式，以便有效地处理大量数据，则还需要确保你能够有效地处理 <xref:System.Windows.Forms.DataGridView> 控件本身。 有关有效使用单元格样式、自动调整大小、选择和行共享的详细信息，请参阅 [缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Windows 窗体 DataGridView 控件中的性能优化](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)
- [在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
