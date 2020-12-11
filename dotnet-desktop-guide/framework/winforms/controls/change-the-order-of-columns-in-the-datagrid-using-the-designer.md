---
title: 使用设计器更改 DataGridView 控件中列的顺序
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 7540203fb1c0465caeb045275734d1a7c6f25ee8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970713"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器更改 Windows 窗体 DataGridView 控件中列的顺序

将 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件绑定到数据源时，自动生成的列的显示顺序由数据源决定。 如果此顺序不是你喜欢的顺序，则可以使用设计器更改列的顺序。 你可能还需要向控件添加未绑定的列并更改其显示顺序。 有关如何以编程方式更改列顺序的信息，请参阅 [如何：更改 Windows 窗体 DataGridView 控件中列的顺序](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)。

下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.DataGridView> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

## <a name="to-change-the-column-order-using-the-designer"></a>使用设计器更改列顺序

1. 单击 ![ 控件右上角 (小型黑色箭头) 的设计器操作标志符号 ](./media/designer-actions-glyph.gif) <xref:System.Windows.Forms.DataGridView> ，然后选择 " **编辑列**"。

2. 从 " **选定的列** " 列表中选择一列。

3. 单击 " **所选列** " 列表右侧的向上或向下箭头，直到所选列处于所需的位置。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- [如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
