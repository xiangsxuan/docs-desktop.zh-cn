---
title: 使用设计器创建 DataGridView 控件中的列 Read-Only
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 2dd3f8bfcad39ca3d530c79a6e6a8170585f7adf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971084"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器将 Windows 窗体 DataGridView 控件中的列设为只读
默认情况下，用户可以修改显示在 Windows 窗体控件中的文本和数字数据 <xref:System.Windows.Forms.DataGridView> 。 如果要显示不用于修改的数据，则必须将包含数据的列设置为只读。 有关如何使控件完全成为只读控件的信息，请参阅 [如何：使用设计器防止 Windows 窗体 DataGridView 控件中添加和删除行](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)。

 下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.DataGridView> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

## <a name="to-make-a-column-read-only-by-using-the-designer"></a>使用设计器使列成为只读的

1. 单击 ![ 控件右上角 (小型黑色箭头) 的设计器操作标志符号 ](./media/designer-actions-glyph.gif) <xref:System.Windows.Forms.DataGridView> ，然后选择 " **编辑列**"。

2. 从 " **选定的列** " 列表中选择一列。

3. 在 " **列属性** " 网格中，将 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 属性设置为 `true` 。

    > [!NOTE]
    > 您还可以通过在 "**添加列**" 对话框中选中 "**只读**" 复选框来添加列，以使其成为只读列。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [如何：使用设计器防止在 Windows 窗体 DataGridView 控件中添加和删除行](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
