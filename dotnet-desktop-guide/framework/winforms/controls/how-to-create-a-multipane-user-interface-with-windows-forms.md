---
title: 创建多窗格用户界面
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], examples
- ListView control [Windows Forms], examples
- RichTextBox control [Windows Forms], examples
- Panel control [Windows Forms], examples
- TreeView control [Windows Forms], examples
- Splitter control [Windows Forms], examples
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
ms.openlocfilehash: 4b168a6d566e20814d4403f90e157d80efe3bf12
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971875"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a>如何：使用 Windows 窗体创建多窗格用户界面
在下面的过程中，你将创建一个多窗格用户界面，该用户界面类似于在 Microsoft Outlook 中使用的用户界面，其中包含 **文件夹** 列表、 **邮件** 窗格和 **预览** 窗格。 这种方式是通过窗体的停靠控件主要实现的。  
  
 停靠控件时，可以确定控件所固定到的父容器的边缘。 因此，如果将属性设置 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 为 <xref:System.Windows.Forms.DockStyle.Right> ，则控件的右边缘将停靠在其父控件的右边缘。 此外，控件的停靠边缘的大小会调整，以匹配其容器控件的边缘。 有关此属性的工作原理的详细信息 <xref:System.Windows.Forms.SplitContainer.Dock%2A> ，请参阅 [如何：在 Windows 窗体上停靠控件](how-to-dock-controls-on-windows-forms.md)。  
  
 此过程侧重于对 <xref:System.Windows.Forms.SplitContainer> 窗体上的和其他控件进行排列，而不是添加功能以使应用程序模拟 Microsoft Outlook。  
  
 若要创建此用户界面，请将所有控件放在 <xref:System.Windows.Forms.SplitContainer> 控件内，其中包含 <xref:System.Windows.Forms.TreeView> 左侧面板中的控件。 控件的右侧面板 <xref:System.Windows.Forms.SplitContainer> 包含一个控件 <xref:System.Windows.Forms.SplitContainer> 上有控件的另一个控件 <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.RichTextBox> 。 这些 <xref:System.Windows.Forms.SplitContainer> 控件允许独立调整窗体上的其他控件的大小。 您可以调整此过程中的技术，以创建自己的自定义用户界面。  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a>以编程方式创建 Outlook 样式的用户界面  
  
1. 在窗体中，声明组成用户界面的每个控件。 对于本示例，请使用 <xref:System.Windows.Forms.TreeView> 、 <xref:System.Windows.Forms.ListView> 、 <xref:System.Windows.Forms.SplitContainer> 和 <xref:System.Windows.Forms.RichTextBox> 控件来模拟 Microsoft Outlook 用户界面。  
  
    ```vb  
    Private WithEvents treeView1 As System.Windows.Forms.TreeView  
    Private WithEvents listView1 As System.Windows.Forms.ListView  
    Private WithEvents richTextBox1 As System.Windows.Forms.RichTextBox  
    Private WithEvents splitContainer1 As _  
        System.Windows.Forms.SplitContainer  
    Private WithEvents splitContainer2 As _  
        System.Windows.Forms.SplitContainer  
    ```  
  
    ```csharp  
    private System.Windows.Forms.TreeView treeView1;  
    private System.Windows.Forms.ListView listView1;  
    private System.Windows.Forms.RichTextBox richTextBox1;  
    private System.Windows.Forms. SplitContainer splitContainer2;  
    private System.Windows.Forms. SplitContainer splitContainer1;  
    ```  
  
2. 创建用于定义用户界面的过程。 下面的代码设置属性，使窗体与 Microsoft Outlook 中的用户界面类似。 但是，通过使用其他控件或将它们停靠在不同的其他控件中，可以轻松地创建具有同样灵活性的其他用户界面。  
  
    ```vb  
    Public Sub CreateOutlookUI()  
        ' Create an instance of each control being used.  
        Me.components = New System.ComponentModel.Container()  
        Me.treeView1 = New System.Windows.Forms.TreeView()  
        Me.listView1 = New System.Windows.Forms.ListView()  
        Me.richTextBox1 = New System.Windows.Forms.RichTextBox()  
        Me.splitContainer1 = New System.Windows.Forms.SplitContainer()  
        Me.splitContainer2= New System.Windows.Forms. SplitContainer()  
  
        ' Should you develop this into a working application,  
        ' use the AddHandler method to hook up event procedures here.  
  
        ' Set properties of TreeView control.  
        ' Use the With statement to avoid repetitive code.  
        With Me.treeView1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 0  
            .Nodes.Add("treeView")  
        End With  
  
    ' Set properties of ListView control.  
       With Me.listView1  
          .Dock = System.Windows.Forms.DockStyle.Top  
          .TabIndex = 2  
          .Items.Add("listView")  
       End With  
  
    ' Set properties of RichTextBox control.  
       With Me.richTextBox1  
          .Dock = System.Windows.Forms.DockStyle.Fill  
          .TabIndex = 3  
          .Text = "richTextBox1"  
       End With  
  
        ' Set properties of the first SplitContainer control.  
        With Me.splitContainer1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 1  
            .SplitterWidth = 4  
            .SplitterDistance = 150  
            .Orientation = Orientation.Horizontal  
            .Panel1.Controls.Add(Me.listView1)  
            .Panel2.Controls.Add(Me.richTextBox1)  
    End With  
  
        ' Set properties of the second SplitContainer control.  
        With Me.splitContainer2  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 4  
            .SplitterWidth = 4  
            .SplitterDistance = 100  
            .Panel1.Controls.Add(Me.treeView1)  
            .Panel2.Controls.Add(Me.SplitContainer1)  
    End With  
  
    ' Add the main SplitContainer control to the form.  
        Me.Controls.Add(Me.splitContainer2)  
        Me.Text = "Intricate UI Example"  
    End Sub  
    ```  
  
    ```csharp  
    public void createOutlookUI()  
    {  
        // Create an instance of each control being used.  
        treeView1 = new System.Windows.Forms.TreeView();  
        listView1 = new System.Windows.Forms.ListView();  
        richTextBox1 = new System.Windows.Forms.RichTextBox();  
        splitContainer2 = new System.Windows.Forms.SplitContainer();  
        splitContainer1 = new System.Windows.Forms.SplitContainer();  
  
        // Insert code here to hook up event methods.  
  
        // Set properties of TreeView control.  
        treeView1.Dock = System.Windows.Forms.DockStyle.Fill;  
        treeView1.TabIndex = 0;  
        treeView1.Nodes.Add("treeView");  
  
        // Set properties of ListView control.  
        listView1.Dock = System.Windows.Forms.DockStyle.Top;  
        listView1.TabIndex = 2;  
        listView1.Items.Add("listView");  
  
        // Set properties of RichTextBox control.  
        richTextBox1.Dock = System.Windows.Forms.DockStyle.Fill;  
        richTextBox1.TabIndex = 3;  
        richTextBox1.Text = "richTextBox1";  
  
        // Set properties of first SplitContainer control.  
        splitContainer1.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 1;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 150;  
        splitContainer2.Orientation = Orientation.Horizontal;  
        splitContainer2.Panel1.Controls.Add(this.listView1);  
        splitContainer2.Panel1.Controls.Add(this.richTextBox1);  
  
        // Set properties of second SplitContainer control.  
        splitContainer2.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 4;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 100;  
        splitContainer2.Panel1.Controls.Add(this.treeView1);  
        splitContainer2.Panel1.Controls.Add(this.splitContainer1);  
  
        // Add the main SplitContainer control to the form.  
        this.Controls.Add(this.splitContainer2);  
        this.Text = "Intricate UI Example";  
    }  
    ```  
  
3. 在 Visual Basic 中，添加对你在过程中刚创建的过程的调用 `New()` 。 在 Visual c # 中，将下面这行代码添加到窗体类的构造函数中。  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer 控件](splitcontainer-control-windows-forms.md)
- [如何：通过使用设计器使用 Windows 窗体创建多窗格用户界面](create-a-multipane-user-interface-with-wf-using-the-designer.md)
