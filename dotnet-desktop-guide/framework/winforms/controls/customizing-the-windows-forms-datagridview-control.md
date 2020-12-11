---
title: 自定义 DataGridView 控件
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970146"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>自定义 Windows 窗体 DataGridView 控件
`DataGridView`控件提供了几个属性，您可以使用这些属性来调整其单元、行和列 (外观和基本行为) 。 不过，如果您的特殊需求超出了类的功能 <xref:System.Windows.Forms.DataGridViewCellStyle> ，则还可以通过创建自定义单元、列和行来实现控件的所有者绘图或扩展其功能。  
  
 若要自行绘制单元格和行，可以处理各种 `DataGridView` 绘制事件。 若要修改现有功能或提供新功能，您可以创建自己的类型，派生自现有的 `DataGridViewCell` 、 `DataGridViewColumn` 和 `DataGridViewRow` 类型。 还可以通过创建在单元格处于编辑模式时显示所选控件的派生类型，来提供新的编辑功能。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md)  
 描述如何处理事件以便 <xref:System.Windows.Forms.DataGridView.CellPainting> 手动绘制单元格。  
  
 [如何：自定义 Windows 窗体 DataGridView 控件中行的外观](customize-the-appearance-of-rows-in-the-datagrid.md)  
 描述如何处理 <xref:System.Windows.Forms.DataGridView.RowPrePaint> 和事件以便 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 使用跨多个列的自定义、渐变背景和内容绘制行。  
  
 [如何：通过扩展 Windows 窗体 DataGridView 控件中单元格和列的行为和外观对其进行自定义](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 介绍如何创建从和派生的自定义类型，以便在 `DataGridViewCell` `DataGridViewColumn` 鼠标指针停留在单元格时突出显示单元格。  
  
 [如何：禁用 Windows 窗体 DataGridView 控件的按钮列中的按钮](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 介绍如何创建从和派生的自定义类型 <xref:System.Windows.Forms.DataGridViewButtonCell> ，以便 <xref:System.Windows.Forms.DataGridViewButtonColumn> 在按钮列中显示禁用的按钮。  
  
 [如何：在 Windows 窗体 DataGridView 单元格中托管控件](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 描述如何实现 `IDataGridViewEditingControl` 接口以及如何创建从和派生的自定义类型，以便在 `DataGridViewCell` `DataGridViewColumn` <xref:System.Windows.Forms.DateTimePicker> 单元格处于编辑模式时显示控件。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.DataGridView>  
 提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 提供类的参考文档 <xref:System.Windows.Forms.DataGridViewCell> 。  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 提供类的参考文档 <xref:System.Windows.Forms.DataGridViewRow> 。  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 提供类的参考文档 <xref:System.Windows.Forms.DataGridViewColumn> 。  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 提供接口的参考文档 <xref:System.Windows.Forms.IDataGridViewEditingControl> 。  
  
## <a name="related-sections"></a>相关章节  
 [Windows 窗体 DataGridView 控件中的基本格式设置和样式设置](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 提供一些主题，描述如何修改该控件的基本外观和单元数据的显示格式。  
  
## <a name="see-also"></a>另请参阅

- [DataGridView 控件](datagridview-control-windows-forms.md)
- [Windows 窗体 DataGridView 控件中的列类型](column-types-in-the-windows-forms-datagridview-control.md)
