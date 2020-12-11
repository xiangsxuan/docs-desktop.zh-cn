---
title: 如何：移动 ToolStripMenuItem
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971150"
---
# <a name="how-to-move-toolstripmenuitems"></a>如何：移动 ToolStripMenuItem
在设计时，可以将整个顶级菜单及其菜单项移动到上的其他位置 <xref:System.Windows.Forms.MenuStrip> 。 您还可以在顶级菜单之间移动各个菜单项，或更改菜单中菜单项的位置。

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>将顶级菜单及其菜单项移到另一个顶级位置

1. 单击并按住鼠标左键，在要移动的菜单上单击鼠标左键。

2. 将插入点拖到预期新位置之前的顶级菜单，然后松开鼠标左键。

     选定的菜单将移动到插入点的右侧。

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>将顶级菜单及其菜单项移至下拉位置

1. 左键单击要移动的菜单，按 CTRL + X，或右键单击菜单并从快捷菜单中选择 " **剪切** "。

2. 在目标顶级菜单中，左键单击预期新位置上方的菜单项，然后按 CTRL + V，或右键单击预期新位置上方的菜单项，然后从快捷菜单中选择 " **粘贴** "。

     您剪切的菜单将插入到所选菜单项之后。

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>使用 Items 集合编辑器在菜单内移动菜单项

1. 右键单击包含要移动的菜单项的菜单。

2. 在快捷菜单中，选择 " **编辑 DropDownItems**"。

3. 在 **项集合编辑器** 中，单击要移动的菜单项。

4. 单击向上键和向下键可在菜单中移动菜单项。

5. 单击“确定”。

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>使用键盘在菜单内移动菜单项

1. 按住 ALT 键。

2. 单击并按住鼠标左键，在要移动的菜单项上单击鼠标左键。

3. 将菜单项拖到新位置，然后释放鼠标左键。

## <a name="to-move-a-menu-item-to-another-menu"></a>将菜单项移动到另一个菜单

1. 左键单击要移动的菜单项，然后按 CTRL + X，或右键单击菜单项，然后从快捷菜单中选择 " **剪切** "。

2. 左键单击将包含您剪切的菜单项的菜单。

3. 左键单击预期新位置之前的菜单项，按 CTRL + V，或右键单击预期新位置之前的菜单项，然后从快捷菜单中选择 " **粘贴** "。

     您剪切的菜单项将插入到所选菜单项之后。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
