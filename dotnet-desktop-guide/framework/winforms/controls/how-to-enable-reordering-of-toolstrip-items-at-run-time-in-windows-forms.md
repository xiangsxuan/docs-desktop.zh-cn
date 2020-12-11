---
title: 如何：在运行时启用 ToolStrip 项重新排序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: 44b52bf997819f090569d08eb395d8af18f61370
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972037"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>如何：在 Windows 窗体中启用 ToolStrip 项的运行时重新排序
可以让用户重新排列 <xref:System.Windows.Forms.ToolStripItem> 上的控件 <xref:System.Windows.Forms.ToolStrip> 。  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>在运行时启用 ToolStripItem 重排  
  
- 将 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 属性设置为 `true`。 默认情况下， <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 为 `false` 。  
  
     在运行时，用户按下 ALT 键并按鼠标左键将拖动 <xref:System.Windows.Forms.ToolStripItem> 到上的其他位置 <xref:System.Windows.Forms.ToolStrip> 。  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 控件体系结构](toolstrip-control-architecture.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
