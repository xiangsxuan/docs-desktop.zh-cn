---
title: 添加和删除具有 ContextMenu 组件的菜单项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: 989ab6d47ec761930a32f542b5fa1136e831f73d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971338"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>如何：使用 Windows 窗体 ContextMenu 组件添加和移除菜单项
说明如何在 Windows 窗体中添加和移除快捷菜单项。  
  
 Windows 窗体 <xref:System.Windows.Forms.ContextMenu> 组件提供了与所选对象相关的常用命令的菜单。 可以通过将对象添加到集合来向快捷菜单添加项 <xref:System.Windows.Forms.MenuItem> <xref:System.Windows.Forms.Menu.MenuItems%2A> 。  
  
 你可以从快捷菜单中永久删除项;但是，在运行时，可能更适合隐藏或禁用这些项。  
  
> [!IMPORTANT]
> 尽管 <xref:System.Windows.Forms.MenuStrip> 和 <xref:System.Windows.Forms.ContextMenuStrip> 将功能替换为 <xref:System.Windows.Forms.MainMenu> 以前版本的和控件，并将其 <xref:System.Windows.Forms.ContextMenu> 保留以 <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 实现后向兼容性和将来使用（如果你选择）。  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>从快捷菜单中删除项  
  
1. 使用 <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> 组件的集合的或 <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> 方法 <xref:System.Windows.Forms.Menu.MenuItems%2A> <xref:System.Windows.Forms.ContextMenu> 可移除特定菜单项。  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     -或-  
  
2. 使用 `Clear` 组件集合的方法 `MenuItems` <xref:System.Windows.Forms.ContextMenu> 从菜单中删除所有项。  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ContextMenu>
- [ContextMenu 组件](contextmenu-component-windows-forms.md)
- [ContextMenu 组件概述](contextmenu-component-overview-windows-forms.md)
