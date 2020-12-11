---
title: 如何：向 ContextMenuStrip 添加菜单项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: 7e3480c5a56170ce94d5b5bde0208542c82e7702
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971784"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a>如何：向 ContextMenuStrip 添加菜单项
一次只能向添加一个菜单项或多个项 <xref:System.Windows.Forms.ContextMenuStrip> 。  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a>向 ContextMenuStrip 添加单个菜单项  
  
- 使用 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 方法将一个菜单项添加到 <xref:System.Windows.Forms.ContextMenuStrip> 中。  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a>向 ContextMenuStrip 添加多个菜单项  
  
- 使用 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 方法将多个菜单项添加到 <xref:System.Windows.Forms.ContextMenuStrip> 中。  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a>另请参阅

- [ContextMenuStrip 控件](contextmenustrip-control.md)
