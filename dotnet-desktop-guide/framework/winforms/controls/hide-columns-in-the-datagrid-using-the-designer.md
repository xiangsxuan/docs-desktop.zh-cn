---
title: 使用设计器在 DataGridView 控件中隐藏列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: c5344e10a69d86b1733f5462f9c2df0f0e71b8d5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971517"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列
有时，你会想仅显示在 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中可用的某些列。 例如，你可能希望向具有管理凭据的用户显示员工薪金列，同时将其与其他用户隐藏。 或者，您可能想要将该控件绑定到包含多个列的数据源，其中只包含您要显示的部分列。 在这种情况下，通常会删除不想要显示的列，而不是隐藏它们。 有关详细信息，请参阅 [如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和删除列](add-and-remove-columns-in-the-datagrid-using-the-designer.md)。

 下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.DataGridView> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

## <a name="to-hide-a-column-using-the-designer"></a>使用设计器隐藏列

1. 单击 ![ 控件右上角 (小型黑色箭头) 的设计器操作标志符号 ](./media/designer-actions-glyph.gif) <xref:System.Windows.Forms.DataGridView> ，然后选择 " **编辑列**"。

2. 从 " **选定的列** " 列表中选择一列。

3. 在 " **列属性** " 网格中，将 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 属性设置为 `false` 。

    > [!NOTE]
    > 还可以通过清除 "**添加列**" 对话框中的 "**可见**" 复选框来添加列。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
