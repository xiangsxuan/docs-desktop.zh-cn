---
title: 使用设计器使用 ListView 控件添加和移除项
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: cab40c556d9e5d21ce15bcd3d4da367bc08f33ab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970739"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>如何：通过使用设计器使用 Windows 窗体 ListView 控件添加和移除项

向 Windows 窗体控件添加项的过程 <xref:System.Windows.Forms.ListView> 主要包含指定项并为其分配属性。 可以随时添加或删除列表项。

下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.ListView> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

### <a name="to-add-or-remove-items-using-the-designer"></a>使用设计器添加或删除项

1. 选择 <xref:System.Windows.Forms.ListView> 控件。

2. 在 "**属性**" 窗口中，**单击省略号按钮 (省略号** ![ 按钮 ( ") " 属性窗口中的 "Visual) Studio"。 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Items%2A>

     此时将显示 " **ListViewItem 集合编辑器** "。

3. 若要添加项目，请单击 " **添加** " 按钮。 然后，可以设置新项的属性，如 <xref:System.Windows.Forms.ListView.Text%2A> 和 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 属性。

4. 若要删除某个项，请选择该项，然后单击 " **删除** " 按钮。

## <a name="see-also"></a>另请参阅

- [ListView 控件概述](listview-control-overview-windows-forms.md)
- [如何：向 Windows 窗体 ListView 控件中添加列](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [如何：使用 Windows 窗体 ListView 控件在列中显示子项](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [如何：显示 Windows 窗体 ListView 控件的图标](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [如何：对 Windows 窗体 ListView 控件中的项进行分组](how-to-group-items-in-a-windows-forms-listview-control.md)
