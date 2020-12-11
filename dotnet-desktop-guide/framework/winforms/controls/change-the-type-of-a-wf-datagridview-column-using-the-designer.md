---
title: 使用设计器更改 DataGridView 列的类型
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 470f350a4791a3db39d08ab7992d86eb7b2e270a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971557"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>如何：使用设计器更改 Windows 窗体 DataGridView 列的类型
有时，您将需要更改已添加到 Windows 窗体控件的列的类型 <xref:System.Windows.Forms.DataGridView> 。 例如，你可能想要修改在将控件绑定到数据源时自动生成的某些列的类型。 当所显示的表中的列包含对相关表中的行的外键时，这非常有用。 在这种情况下，您可能需要将显示这些外键的文本框列替换为组合框列，这些列显示了来自相关表的更有意义的值。

 下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.DataGridView> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

### <a name="to-change-the-type-of-a-column-using-the-designer"></a>使用设计器更改列的类型

1. 单击 ![ 控件右上角 (小型黑色箭头) 的设计器操作标志符号 ](./media/designer-actions-glyph.gif) <xref:System.Windows.Forms.DataGridView> ，然后选择 " **编辑列**"。

2. 从 " **选定的列** " 列表中选择一列。

3. 在 " **列属性** " 网格中，将 `ColumnType` 属性设置为新的列类型。

    > [!NOTE]
    > `ColumnType`属性是一个仅限设计时的属性，它指示表示列类型的类。 它不是列类中定义的实际属性。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
