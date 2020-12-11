---
title: 如何：在 ToolStrip 控件中创建切换按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 6a003b91cd4db5db2790a20db97dbaa4d8925e96
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971864"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="4425d-102">如何：在 ToolStrip 控件中创建切换按钮</span><span class="sxs-lookup"><span data-stu-id="4425d-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>

<span data-ttu-id="4425d-103">当用户单击切换按钮时，它会显示凹陷，并保持凹陷外观，直到用户再次单击此按钮。</span><span class="sxs-lookup"><span data-stu-id="4425d-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>

## <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="4425d-104">创建切换 ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="4425d-104">To create a toggling ToolStripButton</span></span>

- <span data-ttu-id="4425d-105">使用类似于下面的代码示例的代码。</span><span class="sxs-lookup"><span data-stu-id="4425d-105">Use code such as the following code example.</span></span> <span data-ttu-id="4425d-106">此代码假定您的窗体包含一个 <xref:System.Windows.Forms.ToolStrip> 控件，并且它的 <xref:System.Windows.Forms.ToolStrip.Items%2A> 集合包含一个名为的 <xref:System.Windows.Forms.ToolStripButton> `toolStripButton1` 。</span><span class="sxs-lookup"><span data-stu-id="4425d-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="4425d-107">它还假定您有一个名为的事件处理程序 `toolStripButton1_CheckedChanged` 。</span><span class="sxs-lookup"><span data-stu-id="4425d-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>

    ```vb
    toolStripButton1.CheckOnClick = True
    toolStripButton1.CheckedChanged AddressOf _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

    ```csharp
    toolStripButton1.CheckOnClick = true;
    toolStripButton1.CheckedChanged += new _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

## <a name="see-also"></a><span data-ttu-id="4425d-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4425d-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStripButton>
- [<span data-ttu-id="4425d-109">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="4425d-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
