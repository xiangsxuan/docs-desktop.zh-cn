---
title: 自定义 DataGridView 控件中单元格的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970149"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观
您可以通过处理控件的事件来自定义任意单元格的外观 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.CellPainting> 。 你可以 <xref:System.Windows.Forms.DataGridView> <xref:System.Drawing.Graphics> 从的属性中提取控件的 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> 。 这样 <xref:System.Drawing.Graphics> ，你就可以影响整个控件的外观 <xref:System.Windows.Forms.DataGridView> ，但你通常只想影响当前正在绘制的单元格的外观。 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>的属性 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> 使你能够将绘制操作限制为当前正在绘制的单元格。  
  
 在下面的代码示例中，您将 `ContactName` 使用 <xref:System.Windows.Forms.DataGridView> 控件的配色方案绘制列中的所有单元格。 在中绘制每个单元格的文本内容 <xref:System.Drawing.Color.Crimson%2A> ，并以与 <xref:System.Windows.Forms.DataGridView> 控件的属性相同的颜色绘制嵌入矩形 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 一个 <xref:System.Windows.Forms.DataGridView> 名为的控件 `dataGridView1` ，其 `ContactName` 列如 Northwind 示例数据库的 Customers 表中的列。  
  
- 对 System、System.Windows.Forms 和 System.Drawing 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [自定义 Windows 窗体 DataGridView 控件](customizing-the-windows-forms-datagridview-control.md)
