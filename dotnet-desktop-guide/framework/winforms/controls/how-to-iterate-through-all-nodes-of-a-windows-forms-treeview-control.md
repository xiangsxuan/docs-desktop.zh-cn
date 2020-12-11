---
title: 遍历 TreeView 控件的所有节点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], iterating through nodes
- tree nodes in TreeView control [Windows Forms], iterating through
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
ms.openlocfilehash: fd3d8c4659f0dad3b9566cc7946f35957a19f6f9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972517"
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a>如何：循环访问 Windows 窗体 TreeView 控件的所有节点

检查 Windows 窗体控件中的每个节点有时很有用，以便对 <xref:System.Windows.Forms.TreeView> 节点值执行某些计算。 使用循环访问每个树集合中每个节点的递归过程（C# 和 C++ 中为递归方法）可完成此操作。  
  
 <xref:System.Windows.Forms.TreeNode>树视图中的每个对象都具有可用于在树视图中导航的属性： <xref:System.Windows.Forms.TreeNode.FirstNode%2A> 、 <xref:System.Windows.Forms.TreeNode.LastNode%2A> 、 <xref:System.Windows.Forms.TreeNode.NextNode%2A> 、 <xref:System.Windows.Forms.TreeNode.PrevNode%2A> 和 <xref:System.Windows.Forms.TreeNode.Parent%2A> 。 属性的值 <xref:System.Windows.Forms.TreeNode.Parent%2A> 为当前节点的父节点。 当前节点的子节点（如果有）将在其属性中列出 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 。 <xref:System.Windows.Forms.TreeView>控件本身具有 <xref:System.Windows.Forms.TreeView.TopNode%2A> 属性，该属性是整个树视图的根节点。  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a>循环访问 TreeView 控件的所有节点  
  
1. 创建测试每个节点的递归过程（C# 和 C++ 中为递归方法）。  
  
2. 调用该过程。  
  
     下面的示例演示如何打印每个 <xref:System.Windows.Forms.TreeNode> 对象的 <xref:System.Windows.Forms.TreeNode.Text%2A> 属性：  
  
    ```vb  
    Private Sub PrintRecursive(ByVal n As TreeNode)  
       System.Diagnostics.Debug.WriteLine(n.Text)  
       MessageBox.Show(n.Text)  
       Dim aNode As TreeNode  
       For Each aNode In n.Nodes  
          PrintRecursive(aNode)  
       Next  
    End Sub  
  
    ' Call the procedure using the top nodes of the treeview.  
    Private Sub CallRecursive(ByVal aTreeView As TreeView)  
       Dim n As TreeNode  
       For Each n In aTreeView.Nodes  
          PrintRecursive(n)  
       Next  
    End Sub  
    ```  
  
    ```csharp  
    private void PrintRecursive(TreeNode treeNode)  
    {  
       // Print the node.  
       System.Diagnostics.Debug.WriteLine(treeNode.Text);  
       MessageBox.Show(treeNode.Text);  
       // Print each node recursively.  
       foreach (TreeNode tn in treeNode.Nodes)  
       {  
          PrintRecursive(tn);  
       }  
    }  
  
    // Call the procedure using the TreeView.  
    private void CallRecursive(TreeView treeView)  
    {  
       // Print each node recursively.  
       TreeNodeCollection nodes = treeView.Nodes;  
       foreach (TreeNode n in nodes)  
       {  
          PrintRecursive(n);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void PrintRecursive( TreeNode^ treeNode )  
       {  
          // Print the node.  
          System::Diagnostics::Debug::WriteLine( treeNode->Text );  
          MessageBox::Show( treeNode->Text );  
  
          // Print each node recursively.  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(treeNode->Nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ tn = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( tn );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
  
       // Call the procedure using the TreeView.  
       void CallRecursive( TreeView^ treeView )  
       {  
          // Print each node recursively.  
          TreeNodeCollection^ nodes = treeView->Nodes;  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ n = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( n );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅

- [TreeView 控件](treeview-control-windows-forms.md)
- [递归过程](/dotnet/visual-basic/programming-guide/language-features/procedures/recursive-procedures)
