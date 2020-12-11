---
title: 使用设计器冻结 DataGridView 控件中的列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: 554d5eaa55401bdafc455c2dfb20d7c5d214a9be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971303"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器冻结 Windows 窗体 DataGridView 控件中的列

用户查看 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中显示的数据时，有时需要频繁地引用单个列或列集。 例如，当你显示包含多个列的客户信息表时，你可以在任何时候显示客户名称，同时允许其他列在可见区域外滚动。

 若要实现此行为，可冻结控件中的列。 冻结列时，也将冻结其左侧（在从右到左的语言脚本中为右侧）的所有列。 冻结的列保持不变，而所有其他列可以滚动。 如果启用了列重新排序，冻结的列被视为一组不同于未冻结的列。 用户可重新定位任一组中的列，但不能将列从一个组移到另一组。

 下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.DataGridView> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

## <a name="to-freeze-a-column-using-the-designer"></a>使用设计器冻结列

1. 单击 ![ 控件右上角 (小型黑色箭头) 的设计器操作标志符号 ](./media/designer-actions-glyph.gif) <xref:System.Windows.Forms.DataGridView> ，然后选择 " **编辑列**"。

2. 从 " **选定的列** " 列表中选择一列。

3. 在 " **列属性** " 网格中，将 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> 属性设置为 `true` 。

    > [!NOTE]
    > 您还可以通过在 "**添加列**" 对话框中选择 **冻结** 框来添加该列。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [如何：使用设计器在 Windows 窗体 DataGridView 控件中启用列重新排序](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- [如何：为全球化在 Windows 窗体中按从右到左的顺序显示文本](/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
