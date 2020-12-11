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
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>如何：在 ToolStrip 控件中创建切换按钮

当用户单击切换按钮时，它会显示凹陷，并保持凹陷外观，直到用户再次单击此按钮。

## <a name="to-create-a-toggling-toolstripbutton"></a>创建切换 ToolStripButton

- 使用类似于下面的代码示例的代码。 此代码假定您的窗体包含一个 <xref:System.Windows.Forms.ToolStrip> 控件，并且它的 <xref:System.Windows.Forms.ToolStrip.Items%2A> 集合包含一个名为的 <xref:System.Windows.Forms.ToolStripButton> `toolStripButton1` 。 它还假定您有一个名为的事件处理程序 `toolStripButton1_CheckedChanged` 。

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

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStripButton>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
