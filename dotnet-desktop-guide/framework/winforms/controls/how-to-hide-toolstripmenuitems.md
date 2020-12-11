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
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="9d492-102">如何：隐藏 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="9d492-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="9d492-103">通过隐藏菜单项，可以控制应用程序的用户界面并限制用户命令。</span><span class="sxs-lookup"><span data-stu-id="9d492-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="9d492-104">通常，当菜单上的所有菜单项均不可用时，您需要隐藏整个菜单。</span><span class="sxs-lookup"><span data-stu-id="9d492-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="9d492-105">这为用户提供的干扰更少。</span><span class="sxs-lookup"><span data-stu-id="9d492-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="9d492-106">此外，您可能还希望隐藏和禁用菜单项或菜单项，因为仅隐藏不会阻止用户使用快捷键访问菜单命令。</span><span class="sxs-lookup"><span data-stu-id="9d492-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="9d492-107">以编程方式隐藏任何菜单项</span><span class="sxs-lookup"><span data-stu-id="9d492-107">To hide any menu item programmatically</span></span>  
  
- <span data-ttu-id="9d492-108">在设置菜单项属性的方法中，添加要将属性设置为的代码 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false` 。</span><span class="sxs-lookup"><span data-stu-id="9d492-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9d492-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d492-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [<span data-ttu-id="9d492-110">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="9d492-110">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="9d492-111">如何：禁用 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="9d492-111">How to: Disable ToolStripMenuItems</span></span>](how-to-disable-toolstripmenuitems.md)
