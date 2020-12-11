---
title: 禁用 DataGridView 控件中的按钮列中的按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 691781a43005d66e13029ab8110eb7f9daacc35f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970072"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a>如何：禁用 Windows 窗体 DataGridView 控件的按钮列中的按钮
<xref:System.Windows.Forms.DataGridView> 控件包括 <xref:System.Windows.Forms.DataGridViewButtonCell> 类，其用于显示具有与按钮类似的用户界面 (UI) 的单元格。 但是，<xref:System.Windows.Forms.DataGridViewButtonCell> 不提供禁用单元格所显示按钮外观的方法。  
  
 以下代码示例演示如何自定义 <xref:System.Windows.Forms.DataGridViewButtonCell> 类以显示可以显示为禁用的按钮。 此示例定义了一个新的单元格类型，即从 <xref:System.Windows.Forms.DataGridViewButtonCell> 派生的 `DataGridViewDisableButtonCell`。 此单元格类型提供了一种新 `Enabled` 属性，可设置为 `false` 以拖动单元格中已禁用的按钮。 此示例还定义了一个新的列类型，即显示 `DataGridViewDisableButtonCell` 对象的 `DataGridViewDisableButtonColumn`。 为了演示此新单元格和列类型，父级 <xref:System.Windows.Forms.DataGridView> 中的每个 <xref:System.Windows.Forms.DataGridViewCheckBoxCell> 的当前值确定了相同行中 `DataGridViewDisableButtonCell` 的 `Enabled` 属性是否是 `true` 或 `false`。  
  
> [!NOTE]
> 当从 <xref:System.Windows.Forms.DataGridViewCell> 或 <xref:System.Windows.Forms.DataGridViewColumn> 进行派生并将新属性添加到派生的类时，请确保重写 `Clone` 方法以在克隆操作过程中复制新属性。 还应调用基类的 `Clone` 方法，以便将基类的属性复制到新的单元格或列。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 the System、System.Drawing、System.Windows.Forms 和 System.Windows.Forms.VisualStyles 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- [自定义 Windows 窗体 DataGridView 控件](customizing-the-windows-forms-datagridview-control.md)
- [DataGridView 控件体系结构](datagridview-control-architecture-windows-forms.md)
- [Windows 窗体 DataGridView 控件中的列类型](column-types-in-the-windows-forms-datagridview-control.md)
