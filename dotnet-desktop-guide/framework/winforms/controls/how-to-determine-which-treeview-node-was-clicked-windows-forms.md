---
title: 如何：确定被单击的 TreeView 节点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
ms.openlocfilehash: d960eaae2aa479e0be74e9a5e4fdbfec8ff411c1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971847"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>如何：确定被单击的 TreeView 节点（Windows 窗体）
使用 Windows 窗体 <xref:System.Windows.Forms.TreeView> 控件时，一个常见的任务是确定单击了哪个节点，并做出相应的响应。  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>确定单击的 TreeView 节点  
  
1. 使用 <xref:System.EventArgs> 对象返回对已单击节点对象的引用。  
  
2. 通过检查 <xref:System.Windows.Forms.TreeViewEventArgs> 类（其中包含与事件相关的数据）来确定单击了哪个节点。  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    > 作为替代方法，可以使用 <xref:System.Windows.Forms.MouseEventArgs> <xref:System.Windows.Forms.Control.MouseDown> 或 <xref:System.Windows.Forms.Control.MouseUp> 事件的来获取所 <xref:System.Drawing.Point.X%2A> <xref:System.Drawing.Point.Y%2A> 单击的的和坐标值 <xref:System.Drawing.Point> 。 然后，使用 <xref:System.Windows.Forms.TreeView> 控件的 <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> 方法来确定单击了哪个节点。  
  
## <a name="see-also"></a>另请参阅

- [TreeView 控件](treeview-control-windows-forms.md)
