---
title: 自定义 DataGridView 控件中的数据格式设置
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
ms.openlocfilehash: 6bc1a65b876df842df322db165dc08fcc0c931dc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971861"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a>如何：自定义 Windows 窗体 DataGridView 控件中的数据格式设置
下面的代码示例演示如何实现 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 事件的处理程序，该事件根据单元格的列和值更改单元格的显示方式。  
  
 包含负数的 `Balance` 列中的单元格的背景颜色设为红色。 也可将这些单元格的格式设置为货币，以显示负值两边的括号。 有关详细信息，请参阅[如何：设置 Windows 窗体 DataGridView 控件中的数据格式](how-to-format-data-in-the-windows-forms-datagridview-control.md)。  
  
 `Priority` 列中的单元格显示图像以代替对应文本单元格值。 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> 的 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 属性同时用于获取文本单元格的值以及设置相应的图像显示值。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
- 名为 `highPri.bmp`、`mediumPri.bmp` 和 `lowPri.bmp` 的 <xref:System.Drawing.Bitmap> 图像，这些图像与可执行文件驻留在相同的目录中。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [如何：在 Windows 窗体 DataGridView 控件中设置数据格式](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的数据格式设置](data-formatting-in-the-windows-forms-datagridview-control.md)
