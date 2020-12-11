---
title: 如何：使用 MenuStrip 创建 MDI 窗口列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: f013c3df2ab5783a22fe2c34402dc53a328cafa2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971222"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a>如何：使用 MenuStrip 创建 MDI 窗口列表（Windows 窗体）
使用多文档界面 (MDI) 创建可同时打开多个文档的应用程序，并将内容从一个文档复制并粘贴到另一个文档中。  
  
 此过程说明如何在父窗口菜单上创建所有活动子窗体的列表。  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a>在 MenuStrip 上创建 MDI 窗口列表  
  
1. 创建一个窗体并将其 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 属性设置为 `true`。  
  
2. 在窗体上添加一个 <xref:System.Windows.Forms.MenuStrip> 控件。  
  
3. 向添加两个顶级菜单项 <xref:System.Windows.Forms.MenuStrip> ，并将其 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为 `&File` 和 `&Window` 。  
  
4. 将子菜单项添加到 `&File` 菜单项，并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&Open`。  
  
5. 将 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 的属性设置 <xref:System.Windows.Forms.MenuStrip> 为 `&Window` <xref:System.Windows.Forms.ToolStripMenuItem> 。  
  
6. 向项目中添加一个窗体，并向其添加所需的控件，如另一个 <xref:System.Windows.Forms.MenuStrip> 。  
  
7. 为 `&New`<xref:System.Windows.Forms.ToolStripMenuItem> 的 <xref:System.Windows.Forms.Control.Click> 事件创建一个事件处理程序。  
  
8. 在事件处理程序中，插入类似于下面的代码，以便创建和显示的新实例 `Form2` 作为的 MDI 子级 `Form1` 。  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. 将类似于以下代码的代码放入， `&New` <xref:System.Windows.Forms.ToolStripMenuItem> 以注册事件处理程序。  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `Form1` 和 `Form2` 的两个 <xref:System.Windows.Forms.Form> 控件。  
  
- `Form1` 上名为 `menuStrip1` 的 <xref:System.Windows.Forms.MenuStrip> 控件和 `Form2` 上名为 `menuStrip2` 的 <xref:System.Windows.Forms.MenuStrip> 控件。  
  
- 对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- [如何：创建 MDI 父窗体](../advanced/how-to-create-mdi-parent-forms.md)
- [如何：创建 MDI 子窗体](../advanced/how-to-create-mdi-child-forms.md)
- [MenuStrip 控件](menustrip-control-windows-forms.md)
