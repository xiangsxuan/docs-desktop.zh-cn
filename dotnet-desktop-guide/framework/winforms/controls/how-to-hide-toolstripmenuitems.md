---
title: 如何：隐藏 ToolStripMenuItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: 64c0f093063357c1e8db5933c035cc8295ad4f1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971829"
---
# <a name="how-to-hide-toolstripmenuitems"></a>如何：隐藏 ToolStripMenuItem
通过隐藏菜单项，可以控制应用程序的用户界面并限制用户命令。 通常，当菜单上的所有菜单项均不可用时，您需要隐藏整个菜单。 这为用户提供的干扰更少。 此外，您可能还希望隐藏和禁用菜单项或菜单项，因为仅隐藏不会阻止用户使用快捷键访问菜单命令。  
  
### <a name="to-hide-any-menu-item-programmatically"></a>以编程方式隐藏任何菜单项  
  
- 在设置菜单项属性的方法中，添加要将属性设置为的代码 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false` 。  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
- [如何：禁用 ToolStripMenuItem](how-to-disable-toolstripmenuitems.md)
