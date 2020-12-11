---
title: DataGridView 控件中的默认功能
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970110"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的默认功能
Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件可为用户提供大量的默认功能。  
  
## <a name="default-functionality"></a>默认功能  
 默认情况下， <xref:System.Windows.Forms.DataGridView> 控件：  
  
- 当表垂直滚动时，自动显示列标题和行标题保持可见。  
  
- 有一个行标题，其中包含当前行的选择指示器。  
  
- 在第一个单元格中有一个选择矩形。  
  
- 具有当用户双击列分隔符时可自动调整大小的列。  
  
- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>从应用程序的方法调用方法时，自动支持 WINDOWS XP 和 Windows Server 2003 家族上的视觉样式 `Main` 。  
  
 此外，还 <xref:System.Windows.Forms.DataGridView> 可以在默认情况下编辑控件的内容：  
  
- 如果用户在单元格中双击或按 F2，则控件会自动将该单元格置于编辑模式，并在用户键入内容时更新该单元格的内容。  
  
- 如果用户滚动到网格的末尾，用户将看到用于添加新记录的行。 当用户单击此行时，将使用默认值将一个新行添加到 <xref:System.Windows.Forms.DataGridView> 控件中。 当用户按 ESC 键时，此新行将消失。  
  
- 如果用户单击行标题，则会选择整个行。  
  
 通过设置控件的 <xref:System.Windows.Forms.DataGridView> 属性将控件绑定到数据源时 <xref:System.Windows.Forms.DataGridView.DataSource%2A> ，控件：  
  
- 自动使用数据源的列的名称作为列标题文本。  
  
- 用数据源的内容进行填充。 <xref:System.Windows.Forms.DataGridView> 将为数据源中的每个列自动创建列。  
  
- 为表中的每个可见行创建一行。  
  
- 用户单击列标题时，将基于基础数据自动对行进行排序。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView 控件](datagridview-control-windows-forms.md)
