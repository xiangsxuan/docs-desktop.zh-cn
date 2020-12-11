---
title: 如何：向 TreeView 或 ListView 控件添加自定义信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
ms.openlocfilehash: 284bd666d236b765821139a76decd8fedc29b760
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970737"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a>如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）

可以在控件中 Windows 窗体 <xref:System.Windows.Forms.TreeView> 控件或派生项中创建派生节点 <xref:System.Windows.Forms.ListView> 。 通过派生可添加任何所需字段，以及添加处理这些字段的自定义方法和构造函数。 此功能的用途之一是将 Customer 对象附加到每个树节点或列表项。 此处的示例适用于 <xref:System.Windows.Forms.TreeView> 控件，但相同的方法可用于 <xref:System.Windows.Forms.ListView> 控件。  
  
### <a name="to-derive-a-tree-node"></a>派生树节点  
  
- 创建一个从类派生的新节点类 <xref:System.Windows.Forms.TreeNode> ，该类具有一个用于记录文件路径的自定义字段。  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### <a name="to-use-a-derived-tree-node"></a>使用派生的树节点  
  
1. 新的派生树节点可用作函数调用的参数。  
  
     在下例中，为文本文件位置设置的路径是 My Documents 文件夹。 这样做是出于一个假定，即假定大多数运行 Windows 操作系统的计算机都包含此目录。 这还使得具有最低系统访问级别的用户能够安全运行应用程序。  
  
    ```vb  
    ' You should replace the bold text file
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
    ```  
  
    ```csharp  
    // You should replace the bold text file
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\TextFile.txt") );  
    ```  
  
    ```cpp  
    // You should replace the bold text file
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2. 如果传递的是树节点，并且它被类型化为 <xref:System.Windows.Forms.TreeNode> 类，则需要强制转换为派生类。 强制转换是从一种对象类型到另一种对象类型的显式转换。 有关强制转换的详细信息，请参阅 [隐式和显式转换](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions) (Visual Basic) 、 [强制转换和类型转换](/dotnet/csharp/programming-guide/types/casting-and-type-conversions) (Visual c # ) 或 [Cast 运算符： ( # B5 ](/cpp/cpp/cast-operator-parens) (Visual C++) 。  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",
             myNode->FilePath));  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅

- [TreeView 控件](treeview-control-windows-forms.md)
- [ListView 控件](listview-control-windows-forms.md)
