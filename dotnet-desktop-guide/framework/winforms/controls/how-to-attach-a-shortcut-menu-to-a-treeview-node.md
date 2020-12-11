---
title: 如何：将快捷菜单附加到 TreeView 节点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: f818cccb3103866af993f1aff527a9c1a7c82109
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971256"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a>如何：将快捷菜单附加到 TreeView 节点
Windows 窗体 <xref:System.Windows.Forms.TreeView> 控件显示节点的层次结构，类似于在 Windows 资源管理器的左窗格中显示的文件和文件夹。 通过设置 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性，您可以在用户右键单击控件时为用户提供上下文相关的操作 <xref:System.Windows.Forms.TreeView> 。 通过 <xref:System.Windows.Forms.ContextMenuStrip> 将组件与各个 <xref:System.Windows.Forms.TreeNode> 项关联，你可以向控件添加自定义的快捷菜单功能级别 <xref:System.Windows.Forms.TreeView> 。  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a>以编程方式将快捷菜单与 TreeNode 关联  
  
1. <xref:System.Windows.Forms.TreeView>使用适当的属性设置实例化控件，创建根 <xref:System.Windows.Forms.TreeNode> ，然后添加子节点。  
  
2. 实例化 <xref:System.Windows.Forms.ContextMenuStrip> 组件，然后 <xref:System.Windows.Forms.ToolStripMenuItem> 为要在运行时提供的每个操作添加。  
  
3. 将相应的的 <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> 属性设置 <xref:System.Windows.Forms.TreeNode> 为你创建的快捷菜单。  
  
4. 如果设置此属性，则当您右键单击该节点时，将显示快捷菜单。  
  
 下面的代码示例创建一个基本 <xref:System.Windows.Forms.TreeView> 的，并 <xref:System.Windows.Forms.ContextMenuStrip> 与 <xref:System.Windows.Forms.TreeNode> 的根关联 <xref:System.Windows.Forms.TreeView> 。 您将需要自定义菜单选项，使其适合 <xref:System.Windows.Forms.TreeView> 您正在开发的用户。 此外，您还需要编写代码来处理 <xref:System.Windows.Forms.ToolStripItem.Click> 这些菜单项的事件。  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ContextMenuStrip>
- [TreeView 控件](treeview-control-windows-forms.md)
