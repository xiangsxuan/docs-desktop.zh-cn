---
title: 设置 TreeView 控件的图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: e3d7fc35c6d9f70822cdd0b69dd12f3d469f4ffa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970975"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>如何：设置 Windows 窗体 TreeView 控件的图标
Windows 窗体 <xref:System.Windows.Forms.TreeView> 控件可以显示每个节点旁的图标。 图标位于节点文本的紧左侧。 若要显示这些图标，您必须将树视图与控件相关联 <xref:System.Windows.Forms.ImageList> 。 有关图像列表的详细信息，请参阅 [Imagelist 组件](imagelist-component-windows-forms.md) 和 [如何：通过 Windows 窗体 ImageList 组件添加或删除图像](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。  
  
> [!NOTE]
> Microsoft .NET Framework 版本1.1 中的 bug 可防止在 <xref:System.Windows.Forms.TreeView> 应用程序调用时图像显示在节点上 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 。 若要解决此错误，请 <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 在 `Main` 调用后立即在方法中调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 。 此 bug 已在 .NET Framework 2.0 中解决。  
  
### <a name="to-display-images-in-a-tree-view"></a>在树视图中显示图像  
  
1. 将 <xref:System.Windows.Forms.TreeView> 控件的 <xref:System.Windows.Forms.TreeView.ImageList%2A> 属性设置为要使用的现有 <xref:System.Windows.Forms.ImageList> 控件。  
  
     这些属性可以在设计器中设置属性窗口或代码中。  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. 设置节点的 <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 和 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 属性。 <xref:System.Windows.Forms.TreeNode.ImageIndex%2A>属性确定为节点的正常和已展开状态显示的图像， <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 属性确定为节点的选定状态显示的图像。  
  
     这些属性可以在代码中设置，也可以在 TreeNode 编辑器中设置。 若要打开 "树节点编辑器"，请单击省略号按钮 ( ![ Visual Studio 属性窗口中的省略号按钮 ( ") "。 ](./media/visual-studio-ellipsis-button.png)) 上的属性旁的 "属性窗口"。 <xref:System.Windows.Forms.TreeView.Nodes%2A>  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a>另请参阅

- [TreeView 控件概述](treeview-control-overview-windows-forms.md)
- [如何：添加和删除 Windows 窗体 TreeView 控件中的节点](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [如何：循环访问 Windows 窗体 TreeView 控件的所有节点](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [如何：确定被单击的 TreeView 节点](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）](add-custom-information-to-a-treeview-or-listview-control-wf.md)
