---
title: 如何：使用设计器禁用 ToolStripMenuItem
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 692b6c11f6d58c52a0af29ed04ada45c48cae058
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971198"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>如何：使用设计器禁用 ToolStripMenuItem
你可以通过启用和禁用菜单项来限制或放宽用户在响应用户活动时所能执行的命令。 默认情况下，菜单项在创建时处于启用状态，但可以通过属性进行调整 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 。 可以在设计时在 " **属性** " 窗口中或通过编程方式在代码中设置此属性。 有关详细信息，请参阅 how [to： Disable toolstripmenuitem](how-to-disable-toolstripmenuitems.md)。

## <a name="to-disable-a-menu-item-at-design-time"></a>在设计时禁用菜单项

1. 在窗体上选中菜单项时，将 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 属性设置为 `false` 。

    > [!TIP]
    > 禁用菜单中的第一个或顶级菜单项，将禁用该菜单中包含的所有菜单项。 同样，禁用具有子菜单项的菜单项将禁用子菜单项。 如果给定菜单上的所有命令均不可供用户使用，则会被视为良好的编程做法，隐藏和禁用整个菜单，因为这会显示一个干净的用户界面。 你应隐藏和禁用菜单，因为仅隐藏不会阻止通过快捷键访问菜单命令。 将 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 顶级菜单项的属性设置为 `false` 以隐藏整个菜单。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [如何：隐藏 ToolStripMenuItem](how-to-hide-toolstripmenuitems.md)
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
