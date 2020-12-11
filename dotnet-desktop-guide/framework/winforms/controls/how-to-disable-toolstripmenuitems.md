---
title: 如何：禁用 ToolStripMenuItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971844"
---
# <a name="how-to-disable-toolstripmenuitems"></a>如何：禁用 ToolStripMenuItem
你可以通过启用和禁用菜单项来限制或放宽用户在响应用户活动时所能执行的命令。 默认情况下，菜单项在创建时处于启用状态，但可以通过属性进行调整 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 。 可以在设计时在 " **属性** " 窗口中或通过编程方式在代码中设置此属性。  
  
### <a name="to-disable-a-menu-item-programmatically"></a>以编程方式禁用菜单项  
  
- 在设置菜单项属性的方法中，添加要将属性设置为的代码 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> `false` 。  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    > 禁用菜单中的第一个或顶级菜单项将隐藏菜单中包含的所有菜单项，但不会将其禁用。 同样，禁用具有子菜单项的菜单项将隐藏子菜单项，但不会禁用子菜单项。 如果给定菜单上的所有命令均不可供用户使用，则会被视为良好的编程做法，隐藏和禁用整个菜单，因为这会显示一个干净的用户界面。 你应隐藏和禁用菜单，并禁用菜单中的每个项和子菜单项，因为仅限隐藏不会阻止通过快捷键访问菜单命令。 将 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 顶级菜单项的属性设置为 `false` 以隐藏整个菜单。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [如何：隐藏 ToolStripMenuItem](how-to-hide-toolstripmenuitems.md)
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
