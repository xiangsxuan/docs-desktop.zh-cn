---
title: 如何：处理 ContextMenuStrip 打开事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: 3001480959ef90cb31048cbcf70aeff1632979fb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971833"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a>如何：处理 ContextMenuStrip 打开事件
可以 <xref:System.Windows.Forms.ContextMenuStrip> 通过处理事件自定义控件的行为 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何处理 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 事件。 事件处理程序将项动态添加到 <xref:System.Windows.Forms.ContextMenuStrip> 控件。 有关完整的代码示例，请参阅 [如何：动态添加 ToolStrip 项](how-to-add-toolstrip-items-dynamically.md)。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 将 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> 属性设置为， `true` 以防止菜单打开。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [ToolStrip 控件](toolstrip-control-windows-forms.md)
