---
title: 使用设计器在 TreeView 控件中添加和删除节点
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7edf09539719ec76fa3f650254c5c84ff0bc3af7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970738"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>如何：通过使用设计器添加和删除 Windows 窗体 TreeView 控件中的节点

由于 Windows 窗体 <xref:System.Windows.Forms.TreeView> 控件以分层方式显示节点，因此在添加节点时，必须注意其父节点。

下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.TreeView> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

### <a name="to-add-or-remove-nodes-in-the-designer"></a>在设计器中添加或删除节点

1. 选择 <xref:System.Windows.Forms.TreeView> 控件。

2. 在 "**属性**" 窗口中，**单击省略号按钮 (省略号** ![ 按钮 ( ") " 属性窗口中的 "Visual) Studio"。 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.TreeView.Nodes%2A>

     此时将显示 " **TreeNode 节点编辑器** "。

3. 若要添加节点，根节点必须存在;如果不存在，则必须先通过单击 " **添加根** " 按钮添加一个根。 然后，可以通过选择根节点或任何其他节点，然后单击 " **添加子级** " 按钮来添加子节点。

4. 若要删除节点，请选择要删除的节点，然后单击 " **删除** " 按钮。

## <a name="see-also"></a>另请参阅

- [TreeView 控件](treeview-control-windows-forms.md)
- [TreeView 控件概述](treeview-control-overview-windows-forms.md)
- [如何：设置 Windows 窗体 TreeView 控件的图标](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [如何：循环访问 Windows 窗体 TreeView 控件的所有节点](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [如何：确定被单击的 TreeView 节点](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）](add-custom-information-to-a-treeview-or-listview-control-wf.md)
