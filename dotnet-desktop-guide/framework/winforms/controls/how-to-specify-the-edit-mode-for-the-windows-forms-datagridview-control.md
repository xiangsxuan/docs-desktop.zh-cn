---
title: 指定 DataGridView 控件的编辑模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972546"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>如何：指定 Windows 窗体 DataGridView 控件的编辑模式
默认情况下，用户可以 <xref:System.Windows.Forms.DataGridView> 通过键入或按 F2 来编辑当前文本框单元格的内容。 如果满足以下所有条件，则会将单元格置于编辑模式：  
  
- 基础数据源支持编辑。  
  
- <xref:System.Windows.Forms.DataGridView>控件已启用。  
  
- <xref:System.Windows.Forms.DataGridView.EditMode%2A> 属性值不为 <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>。  
  
- `ReadOnly`单元格、行、列和控件的属性均设置为 `false` 。  
  
 在编辑模式下，用户可以更改单元值并按 ENTER 来提交更改，或按 ESC 将单元恢复到其原始值。  
  
 你可以配置 <xref:System.Windows.Forms.DataGridView> 控件，使单元格成为当前单元格后进入编辑模式。 在这种情况下，ENTER 和 ESC 键的行为是不变的，但在提交或还原值后，该单元格仍处于编辑模式。 你还可以配置控件，以便仅当用户在单元格中输入时，或仅当用户按下 F2 时单元格进入编辑模式。 最后，你可以防止单元格进入编辑模式，除非调用 <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> 方法。  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>更改 DataGridView 控件的编辑模式  
  
- 将 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> 属性设置为相应的 <xref:System.Windows.Forms.DataGridViewEditMode> 枚举。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
- 对 <xref:System> 和 <xref:System.Windows.Forms> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Windows 窗体 DataGridView 控件中的数据输入](data-entry-in-the-windows-forms-datagridview-control.md)
