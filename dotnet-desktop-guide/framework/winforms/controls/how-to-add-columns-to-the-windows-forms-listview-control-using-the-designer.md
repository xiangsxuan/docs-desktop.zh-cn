---
title: 使用设计器向 ListView 控件添加列
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 627f8627aac861877a05c13def07427199807754
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971514"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>如何：使用设计器向 Windows 窗体 ListView 控件添加列

<xref:System.Windows.Forms.ListView>当在 **详细信息** 视图中时，Windows 窗体控件可以显示每个列表项的多个列。 您可以使用这些列显示有关每个列表项的多种类型的信息。 例如，文件列表可以显示文件的名称、文件类型、大小和文件的上次修改日期。 有关创建列后对其进行填充的信息，请参阅 [如何：用 Windows 窗体 ListView 控件在列中显示子项](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)。

下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.ListView> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

### <a name="to-add-columns-in-the-designer"></a>在设计器中添加列

1. 在 " **属性** " 窗口中，将控件的 <xref:System.Windows.Forms.ListView.View%2A> 属性设置为 <xref:System.Windows.Forms.View.Details> 。

2. 在 "**属性**" 窗口中，单击 **省略号** 按钮， (![ Visual Studio 属性窗口中的省略号按钮 ( ") "。在 ](./media/visual-studio-ellipsis-button.png) 属性旁) 。 <xref:System.Windows.Forms.ListView.Columns%2A>

     此时将显示 " **ColumnHeader 集合编辑器** "。

3. 使用 " **添加** " 按钮添加新列。 然后，可以选择列标题，并将其文本设置 (列的标题) 、文本对齐方式和宽度。

## <a name="see-also"></a>另请参阅

- [ListView 控件概述](listview-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 ListView 控件添加和移除项](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [如何：使用 Windows 窗体 ListView 控件在列中显示子项](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [如何：显示 Windows 窗体 ListView 控件的图标](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）](add-custom-information-to-a-treeview-or-listview-control-wf.md)
