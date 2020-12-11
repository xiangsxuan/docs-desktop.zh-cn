---
title: 对 DataGridView 控件中的数据进行排序
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972922"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a>对 Windows 窗体 DataGridView 控件中的数据进行排序

默认情况下，用户可以通过单击文本框列的标题来对控件中的数据进行排序， <xref:System.Windows.Forms.DataGridView> (或在文本框单元格集中于 .NET Framework 4.7.2 和更高版本) 时按 F3。 您可以修改 <xref:System.Windows.Forms.DataGridViewColumn.SortMode> 特定列的属性，以允许用户在执行此操作时按其他列类型进行排序。 还可以通过编程方式按任何列或多个列对数据进行排序。

## <a name="in-this-section"></a>在本节中

[Windows 窗体 DataGridView 控件中的列排序模式](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
描述用于对控件中的数据进行排序的选项。

[如何：设置 Windows 窗体 DataGridView 控件中列的排序模式](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
介绍如何使用户能够按默认情况下不可排序的列排序。

[如何：自定义 Windows 窗体 DataGridView 控件中的排序方式](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
描述如何以编程方式对数据进行排序，以及如何使用 <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> 事件或通过实现接口自定义排序 <xref:System.Collections.IComparer> 。

## <a name="reference"></a>参考

<xref:System.Windows.Forms.DataGridView>  
提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
提供方法的参考文档 <xref:System.Windows.Forms.DataGridView.Sort%2A> 。

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
提供属性的参考文档 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 。

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
提供枚举的参考文档 <xref:System.Windows.Forms.DataGridViewColumnSortMode> 。

## <a name="see-also"></a>另请参阅

- [DataGridView 控件](datagridview-control-windows-forms.md)
- [Windows 窗体 DataGridView 控件中的列类型](column-types-in-the-windows-forms-datagridview-control.md)
