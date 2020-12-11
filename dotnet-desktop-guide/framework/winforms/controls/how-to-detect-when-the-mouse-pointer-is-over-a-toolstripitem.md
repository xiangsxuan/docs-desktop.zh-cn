---
title: 如何：检测鼠标指针何时在 ToolStripItem 上
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: f01a9acb3a566be40d65fb075c8487d4e9cb6e73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971201"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>如何：检测鼠标指针何时在 ToolStripItem 上
使用以下过程检测鼠标指针何时位于上 <xref:System.Windows.Forms.ToolStripItem> 。  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>检测指针何时在 ToolStripItem 上  
  
- 使用的 <xref:System.Windows.Forms.ToolStripItem.Selected%2A> 项的属性为 <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> `true` 。  
  
     这会使你不必同步 <xref:System.Windows.Forms.ToolStripItem.MouseEnter> 和 <xref:System.Windows.Forms.ToolStripItem.MouseLeave> 事件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
