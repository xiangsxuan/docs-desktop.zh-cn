---
title: 在 DataGridView 控件的单元格中显示图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971195"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>如何：在 Windows 窗体 DataGridView 控件的单元格中显示图像
图片或图形是可以在数据行中显示的值之一。 通常，这些图形采用员工照片或公司徽标的形式。  
  
 在控件中显示数据时，合并图片非常简单 <xref:System.Windows.Forms.DataGridView> 。 <xref:System.Windows.Forms.DataGridView>控件本身处理类支持的任何图像格式 <xref:System.Drawing.Image> ，以及某些数据库使用的 OLE 图片格式。  
  
 如果 <xref:System.Windows.Forms.DataGridView> 控件的数据源具有一列图像，则控件将自动显示这些图像 <xref:System.Windows.Forms.DataGridView> 。  
  
 下面的代码示例演示如何从嵌入的资源中提取图标，并将其转换为位图，以在 image 列的每个单元格中显示。 有关将文本单元格值替换为相应图像的另一个示例，请参阅 [如何：自定义 Windows 窗体 DataGridView 控件中的数据格式](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
- 名为的嵌入图标资源 `tree.ico` 。  
  
- 对 <xref:System?displayProperty=nameWithType><xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Drawing?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- [Windows 窗体 DataGridView 控件中的基本列、行和单元格功能](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [如何：在 Windows 窗体 DataGridView 控件中自定义数据格式设置](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
