---
title: 如何：向 ToolStripMenuItem 添加增强功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
ms.openlocfilehash: 61a79b9bbe101d7bf694240bdffdecee5187adf2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971910"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>如何：向 ToolStripMenuItem 添加增强功能
可以 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 通过以下方式增强和控制的可用性：  
  
- 添加复选标记以指定是否打开或关闭某个功能，例如标尺是否沿字处理应用程序的边距显示，或指示正在显示的文件列表中的哪个文件（如在 **窗口** 菜单上）。  
  
- 添加直观表示菜单命令的图像。  
  
- 显示快捷键以提供用于执行命令的鼠标替代项。 例如，按 CTRL + C 将执行 **复制** 命令。  
  
- 显示 "访问键"，为菜单导航提供鼠标替代方法。 例如，按 ALT + F 会选择 " **文件** " 菜单。  
  
- 显示用于对相关命令进行分组并使菜单更具可读性的分隔条。  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>在菜单命令中显示复选标记  
  
- 将其 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 属性设置为 `true` 。  
  
     这还会将 <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> 属性设置为 `true` 。 仅当你希望菜单命令显示为 "默认选中" 时才使用此过程，无论是否选择了此选项。  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>显示每次单击更改状态的复选标记  
  
- 将菜单命令的 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 属性设置为 `true` 。  
  
### <a name="to-add-an-image-to-a-menu-command"></a>向菜单命令添加图像  
  
- 将菜单命令的 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 属性设置为图像的名称。 如果 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 此菜单命令的属性设置为 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> 或 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> ，则无法显示该图像。  
  
> [!NOTE]
> 如果选择此选项，图像边距也会显示复选标记。 此外，您还可以将 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 图像的属性设置为 `true` ，并且在运行时，图像将以阴影线边框显示。  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>显示菜单命令的快捷键  
  
- 将菜单命令的 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> 属性设置为所需的键盘组合，如 " **打开** " 菜单命令的 CTRL + O，并将 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 属性设置为 `true` 。  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>显示菜单命令的自定义快捷键  
  
- 将菜单命令的 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 属性设置为所需的键盘组合，如 CTRL + SHIFT + o 而非 SHIFT + CTRL + o，并将 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 属性设置为 `true` 。  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>显示菜单命令的访问键  
  
- 设置 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 菜单命令的属性时，请在要加下划线的字母前输入与号 ( # A0) 。 例如，键入 `&Open` 作为 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 菜单项的属性将生成一个显示为 " <u>O</u>笔" 的菜单命令。
  
     若要导航到此菜单命令，请按 ALT，将焦点置于 <xref:System.Windows.Forms.MenuStrip> ，并按菜单名称的访问键。 当菜单打开并显示带有访问键的项时，只需按 "访问键" 即可选择菜单命令。  
  
> [!NOTE]
> 避免定义重复访问键，如在同一菜单系统中定义两次 ALT + F。 无法保证重复访问键的选择顺序。  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>在菜单命令之间显示分隔条  
  
- 定义 <xref:System.Windows.Forms.MenuStrip> 及其所包含的项后，请使用 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 或 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 方法，按所需顺序向中添加菜单命令和 <xref:System.Windows.Forms.ToolStripSeparator> 控件 <xref:System.Windows.Forms.MenuStrip> 。  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,
    ' and the Save and Exit menu commands to the top-level File menu,
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,
    // and the Save and Exit menu commands to the top-level File menu,
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
