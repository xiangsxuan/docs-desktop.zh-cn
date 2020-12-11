---
title: 如何：将 MenuStrip 追加到 MDI 父窗口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], appending
- MDI [Windows Forms], merging menu items
ms.assetid: ab70c936-b452-4653-b417-17be57bb795b
ms.openlocfilehash: 06e5c9daab8b7eb72024fff27d661c0eb3bf84c6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971264"
---
# <a name="how-to-append-a-menustrip-to-an-mdi-parent-window-windows-forms"></a>如何：将 MenuStrip 追加到 MDI 父窗口（Windows 窗体）
在某些应用程序中，多文档界面 (MDI) 子窗口的类型可以不同于 MDI 父窗口。 例如，MDI 父窗口可能为电子表格，而 MDI 子窗口可能为图表。 在这种情况下，由于激活了不同类型的 MDI 子窗口，你想用 MDI 子菜单上的内容更新 MDI 父菜单的内容。  
  
 下面的过程使用 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>、<xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>、<xref:System.Windows.Forms.MergeAction> 和 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 属性将 MDI 子菜单附加到 MDI 父菜单。 关闭 MDI 子窗口可将附加的菜单从 MDI 父窗口中删除。  
  
 另请参阅 [多文档界面 (MDI) 应用程序](../advanced/multiple-document-interface-mdi-applications.md)。  
  
### <a name="to-append-a-menu-item-to-an-mdi-parent"></a>将菜单项附加到 MDI 父菜单  
  
1. 创建一个窗体并将其 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 属性设置为 `true`。  
  
2. 将 <xref:System.Windows.Forms.MenuStrip> 添加到 `Form1` 并将 <xref:System.Windows.Forms.MenuStrip> 的 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 属性设置为 `true`。  
  
3. 将 `Form1`<xref:System.Windows.Forms.MenuStrip> 的 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 属性设置为 `false`。  
  
4. 将顶级菜单项添加到 `Form1`<xref:System.Windows.Forms.MenuStrip> 并将其 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为 `&File`。  
  
5. 将子菜单项添加到 `&File` 菜单项，并将其 <xref:System.Windows.Forms.Form.Text%2A> 属性设置为 `&Open`。  
  
6. 将窗体添加到项目，将 <xref:System.Windows.Forms.MenuStrip> 添加该窗体，并将 `Form2`<xref:System.Windows.Forms.MenuStrip> 的 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 属性设置为 `true`。  
  
7. 将顶级菜单项添加到 `Form2`<xref:System.Windows.Forms.MenuStrip> 并将其 <xref:System.Windows.Forms.Form.Text%2A> 属性设置为 `&Special`。  
  
8. 将两个子菜单项添加到 `&Special` 菜单项，并将其 <xref:System.Windows.Forms.Form.Text%2A> 属性分别设置为 `Command&1` 和 `Command&2`。  
  
9. 将 `&Special`、`Command&1` 和 `Command&2` 菜单项的 <xref:System.Windows.Forms.MergeAction> 属性设置为 <xref:System.Windows.Forms.MergeAction.Append>。  
  
10. 为的事件创建一个事件处理程序 <xref:System.Windows.Forms.Control.Click> `&Open` <xref:System.Windows.Forms.ToolStripMenuItem> 。  
  
11. 在事件处理程序内，插入类似于以下示例代码的代码，从而将 `Form2` 的新实例创建和显示为 `Form1` 的 MDI 子级。  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
        NewMDIChild.MdiParent = Me  
        'Display the new form.  
        NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
        newMDIChild.MdiParent = this;  
        // Display the new form.  
        newMDIChild.Show();  
    }  
    ```  
  
12. 将类似于以下示例代码的代码放在 `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> 中以注册事件处理程序。  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `Form1` 和 `Form2` 的两个 <xref:System.Windows.Forms.Form> 控件。  
  
- `Form1` 上名为 `menuStrip1` 的 <xref:System.Windows.Forms.MenuStrip> 控件和 `Form2` 上名为 `menuStrip2` 的 <xref:System.Windows.Forms.MenuStrip> 控件。  
  
- 对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。
