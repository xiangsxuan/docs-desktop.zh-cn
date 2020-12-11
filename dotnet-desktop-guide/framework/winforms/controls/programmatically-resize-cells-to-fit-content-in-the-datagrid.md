---
title: 以编程方式调整单元格大小以适应 DataGridView 控件中的内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: df3b378a8ba358fa0bfe549a7901b3d59d53f556
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972830"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a>如何：以编程方式调整单元格的大小来适应 Windows 窗体 DataGridView 控件中的内容
可使用 <xref:System.Windows.Forms.DataGridView> 控件方法调整行、列和标头大小，以便它们显示其完整值而无截断。 可在选择时使用这些方法调整 <xref:System.Windows.Forms.DataGridView> 元素的大小。 或者，可配置控件以在内容更改时自动调整这些元素的大小。 但是，在处理大型数据集或数据频繁更改时，这可能效率很低。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件中的调整大小选项](sizing-options-in-the-windows-forms-datagridview-control.md)。  
  
 通常，只有在从数据源加载新数据或用户已编辑值时，才以编程方式调整 <xref:System.Windows.Forms.DataGridView> 元素以适合它的内容。 此操作可用于优化性能，但当想要用户使用鼠标手动调整行和列的大小时，它也非常有用。  
  
 以下代码示例演示可用于以编程方式调整大小的选项。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [调整 Windows 窗体 DataGridView 控件中列和行的大小](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的大小调整选项](sizing-options-in-the-windows-forms-datagridview-control.md)
- [如何：自动调整单元格的大小来适应 Windows 窗体 DataGridView 控件中的内容变化](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
