---
title: 启用 DataGridView 控件中的列重新排序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: 681489cdb874677079e2577140040921e587d21e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971178"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a>如何：启用 Windows 窗体 DataGridView 控件中列的重新排序
如果你启用了 <xref:System.Windows.Forms.DataGridView> 控件中的列重新排序，用户则可通过用鼠标拖动列标题来将列移动到新位置。 在 <xref:System.Windows.Forms.DataGridView> 控件中，<xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 属性值确定用户是否可以将列移动到不同的位置。  
  
 Visual Studio 中对此任务提供支持。  另请参阅 [如何：使用设计器在 Windows 窗体 DataGridView 控件中启用列重新排序](enable-column-reordering-in-the-datagrid-using-the-designer.md)。  
  
### <a name="to-enable-column-reordering-programmatically"></a>以编程方式启用列重新排序  
  
- 将 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 属性设置为 `true`。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
- 对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [Windows 窗体 DataGridView 控件中的基本列、行和单元格功能](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [如何：冻结 Windows 窗体 DataGridView 控件中的列](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
