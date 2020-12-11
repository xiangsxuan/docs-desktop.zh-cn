---
title: 如何：使用设计器将快捷菜单附加到 TreeNode
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971257"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>如何：使用设计器将快捷菜单附加到 TreeNode
Windows 窗体 <xref:System.Windows.Forms.TreeView> 控件显示节点的层次结构，这类似于 windows 操作系统中的 Windows 资源管理器功能的左窗格中显示的文件和文件夹。 通过设置 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性，您可以在用户右键单击控件时为用户提供上下文相关的操作 <xref:System.Windows.Forms.TreeView> 。 通过 <xref:System.Windows.Forms.ContextMenuStrip> 将组件与各个 <xref:System.Windows.Forms.TreeNode> 项关联，你可以向控件添加自定义的快捷菜单功能级别 <xref:System.Windows.Forms.TreeView> 。

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>在设计时将快捷菜单与 TreeNode 关联

1. 向 <xref:System.Windows.Forms.TreeView> 窗体添加一个控件，并根据需要将节点添加到 <xref:System.Windows.Forms.TreeView> 。 有关详细信息，请参阅 [如何：在 Windows 窗体 TreeView 控件中添加和删除节点](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)。

2. 将 <xref:System.Windows.Forms.ContextMenuStrip> 组件添加到窗体，然后将菜单项添加到表示要在运行时提供的节点级操作的快捷菜单。 有关详细信息，请参阅 [如何：向 ContextMenuStrip 添加菜单项](how-to-add-menu-items-to-a-contextmenustrip.md)。

3. 重新打开该控件的 " **TreeNodeEditor** " 对话框 <xref:System.Windows.Forms.TreeView> ，选择要编辑的节点，并将其 <xref:System.Windows.Forms.ContextMenuStrip> 属性设置为添加的快捷菜单。

4. 如果设置此属性，则当您右键单击该节点时，将显示快捷菜单。

     此外，您还需要编写代码来处理 <xref:System.Windows.Forms.ToolStripItem.Click> 这些菜单项的事件。

## <a name="see-also"></a>另请参阅

- [TreeView 控件](treeview-control-windows-forms.md)
- [TreeView 控件概述](treeview-control-overview-windows-forms.md)
- [ContextMenuStrip 控件](contextmenustrip-control.md)
