---
title: 更改 DataGridView 控件中的边框和网格线样式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: 918102a87ee29a3d3b78d6e6eedce57237135a51
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971560"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a>如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线的样式
在 <xref:System.Windows.Forms.DataGridView> 控件中，您可以自定义控件的边框和网格线的外观，以改善用户体验。 除了控件中单元格的边框样式外，还可以修改网格线颜色和控件边框样式。 对于普通单元格、行标题单元格和列标题单元，还可以应用不同的单元格边框样式。  
  
> [!NOTE]
> 网格线颜色仅与 <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single> 枚举的、 <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal> 和 <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> 值 <xref:System.Windows.Forms.DataGridViewCellBorderStyle> 以及枚举的 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> 值 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> 一起使用。 这些枚举的其他值使用操作系统指定的颜色。 此外，当通过方法在 Windows XP 和 Windows Server 2003 家族上启用视觉样式时 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> ， <xref:System.Windows.Forms.DataGridView.GridColor%2A> 不使用属性值。  
  
### <a name="to-change-the-gridline-color-programmatically"></a>以编程方式更改网格线颜色  
  
- 设置 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 属性。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a>以编程方式更改整个 DataGridView 控件的边框样式  
  
- 将 <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> 属性设置为 <xref:System.Windows.Forms.BorderStyle> 枚举值之一。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a>以编程方式更改 DataGridView 单元格的边框样式  
  
- 设置 <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>、 <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>和 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> 属性。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
- 对 <xref:System?displayProperty=nameWithType><xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Drawing?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [Windows 窗体 DataGridView 控件中的基本格式设置和样式设置](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
