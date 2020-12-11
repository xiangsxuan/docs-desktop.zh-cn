---
title: 使用户能够将多个单元格从 DataGridView 控件复制到剪贴板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: 2bb74a1f0c59b28ab496ce9c89c1c1b5f9d8147b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971538"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a>如何：使用户能够将多个单元格从 Windows 窗体 DataGridView 控件复制到剪贴板
启用单元格复制时，其他应用程序可以通过 <xref:System.Windows.Forms.Clipboard> 轻松访问 <xref:System.Windows.Forms.DataGridView> 控件中的数据。 将选定单元格的值转换为字符串，并作为制表符分隔的文本值添加到剪贴板以粘贴到记事本和 Excel 等应用程序中，或作为 HTML 格式的表格粘贴到 Word 等应用程序中。  
  
 可以将单元复制格配置为：当用户选择整行或整列时，仅复制单元格的值、在剪贴板数据中包含行和列的标题文本，或仅包含标题文本。  
  
 根据选择模式，用户可以选择多个不相连的单元格组。 用户将单元格复制到剪贴板时，不会复制不带选定单元格的行和列。 所有其他行或列成为复制到剪贴板的数据表中的行和列。 将这些行或列中未选定的单元格作为空白占位符复制到剪贴板。  
  
### <a name="to-enable-cell-copying"></a>启用单元格复制  
  
- 设置 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> 属性。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a>示例  
 下面的完整代码示例演示如何将单元格复制到剪贴板。 此示例包含一个按钮，该按钮使用 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> 方法将选定的单元格复制到剪贴板，并在文本框中显示剪贴板内容。  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此代码需要：  
  
- 引用 N:System and N:System.Windows.Forms 程序集。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [Windows 窗体 DataGridView 控件的选项和剪贴板使用](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
