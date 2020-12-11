---
title: 在 DataGridView 控件中调整列和行的大小
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 8f8394a837ccc11c469f9ad4feeb60464d0014fe
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972011"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a>调整 Windows 窗体 DataGridView 控件中列和行的大小
`DataGridView`控件提供了很多用于自定义其列和行的大小调整行为的选项。 通常， `DataGridView` 单元不会根据其内容调整大小。 相反，它们会剪裁大于该单元的任何显示值。 如果内容显示为字符串，则单元格会在工具提示中显示它。  
  
 默认情况下，用户可以使用鼠标拖动行、列和标题分隔符来显示详细信息。 用户还可以双击分隔线，根据其内容自动调整关联的行、列或标题带区的大小。  
  
 `DataGridView`控件提供属性、方法和事件，使您可以自定义或禁用所有这些用户定向行为。 此外，可以以编程方式调整行、列和标头的大小以适应其内容，也可以将其配置为在其内容更改时自动调整其大小。 您还可以将列配置为按您指定的比例将控件的可用宽度自动划分。  
  
## <a name="in-this-section"></a>本节内容  
 [Windows 窗体 DataGridView 控件中的大小调整选项](sizing-options-in-the-windows-forms-datagridview-control.md)  
 介绍用于调整行、列和标头大小的选项。 还提供了有关大小调整的属性和方法的详细信息，并介绍了常见的使用方案。  
  
 [Windows 窗体 DataGridView 控件中的列填充模式](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 详细说明列填充模式，并提供可用于试验列填充模式和其他模式的演示代码。  
  
 [如何：设置 Windows 窗体 DataGridView 控件的大小调整模式](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 描述如何为常见用途配置大小调整模式。  
  
 [如何：以编程方式调整单元格的大小来适应 Windows 窗体 DataGridView 控件中的内容](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 提供可用于试验编程大小的演示代码。  
  
 [如何：自动调整单元格的大小来适应 Windows 窗体 DataGridView 控件中的内容变化](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 提供了可用于尝试自动调整大小模式的演示代码。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.DataGridView>  
 提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。  
  
## <a name="see-also"></a>另请参阅

- [DataGridView 控件](datagridview-control-windows-forms.md)
