---
title: 如何：从 MDI 下拉菜单中删除 ToolStripMenuItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
ms.openlocfilehash: 3198195cf0991734826508aa65818505bf2038c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971143"
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a>如何：从 MDI 下拉菜单移除 ToolStripMenuItem（Windows 窗体）
在某些应用程序中，多文档界面 (MDI) 子窗口的类型可以不同于 MDI 父窗口。 例如，MDI 父窗口可能为电子表格，而 MDI 子窗口可能为图表。 在这种情况下，由于激活了不同类型的 MDI 子窗口，你想用 MDI 子菜单上的内容更新 MDI 父菜单的内容。  
  
 下面的过程使用 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 、 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 、 <xref:System.Windows.Forms.MergeAction> 和 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 属性从 MDI 父菜单的下拉部分中删除菜单项。 关闭 MDI 子窗口会将移除的菜单项还原到 MDI 父菜单。  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a>从 MDI 下拉菜单中删除 MenuStrip  
  
1. 创建一个窗体并将其 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 属性设置为 `true`。  
  
2. 将 <xref:System.Windows.Forms.MenuStrip> 添加到 `Form1` 并将 <xref:System.Windows.Forms.MenuStrip> 的 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 属性设置为 `true`。  
  
3. 将顶级菜单项添加到 `Form1`<xref:System.Windows.Forms.MenuStrip> 并将其 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为 `&File`。  
  
4. 将三个子菜单项添加到 `&File` 菜单项，并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&Open` 、 `&Import from` 和 `E&xit` 。  
  
5. 向子菜单项添加两个子菜单项 `&Import from` ，并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&Word` 和 `&Excel` 。  
  
6. 将窗体添加到项目，将 <xref:System.Windows.Forms.MenuStrip> 添加该窗体，并将 `Form2`<xref:System.Windows.Forms.MenuStrip> 的 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 属性设置为 `true`。  
  
7. 将顶级菜单项添加到 `Form2`<xref:System.Windows.Forms.MenuStrip> 并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&File`。  
  
8. 将 `&Import from` 子菜单项添加到的 `&File` 菜单 `Form2` ，然后将 `&Word` 子菜单项添加到 `&File` 菜单中。  
  
9. 设置 <xref:System.Windows.Forms.MergeAction> 菜单项的和属性，如下 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> `Form2` 表所示。  
  
    |Form2 菜单项|MergeAction 值|MergeIndex 值|  
    |---------------------|-----------------------|----------------------|  
    |文件|MatchOnly|-1|  
    |导入自|MatchOnly|-1|  
    |Word|删除|-1|  
  
10. 在中 `Form1` ，为的事件创建一个事件处理程序 <xref:System.Windows.Forms.Control.Click> `&Open` <xref:System.Windows.Forms.ToolStripMenuItem> 。  
  
11. 在事件处理程序中，插入类似于以下代码示例的代码，以创建和显示的新实例 `Form2` 作为的 MDI 子级 `Form1` ：  
  
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
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `Form1` 和 `Form2` 的两个 <xref:System.Windows.Forms.Form> 控件。  
  
- `Form1` 上名为 `menuStrip1` 的 <xref:System.Windows.Forms.MenuStrip> 控件和 `Form2` 上名为 `menuStrip2` 的 <xref:System.Windows.Forms.MenuStrip> 控件。  
  
- 对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- [如何：创建 MDI 父窗体](../advanced/how-to-create-mdi-parent-forms.md)
- [如何：创建 MDI 子窗体](../advanced/how-to-create-mdi-child-forms.md)
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
