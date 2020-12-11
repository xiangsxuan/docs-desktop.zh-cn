---
title: 如何：为 MDI 应用程序设置自动菜单合并
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 33e07bb655d81c6a802ebdce871a2fed845a5c96
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972548"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>如何：为 MDI 应用程序设置自动菜单合并
以下过程提供了在多文档界面中设置自动合并的基本步骤， (MDI) 应用程序 <xref:System.Windows.Forms.MenuStrip> 。  
  
### <a name="to-set-up-automatic-menu-merging"></a>设置自动菜单合并  
  
1. 通过将 MDI 父窗体的属性设置为来创建该窗体 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> `true` 。  
  
2. 向 <xref:System.Windows.Forms.MenuStrip> MDI 父级添加，并将其 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> 属性设置为 <xref:System.Windows.Forms.MenuStrip> 。  
  
3. 创建一个 MDI 子窗体，并将其 <xref:System.Windows.Forms.Form.MdiParent%2A> 属性设置为父窗体的名称。  
  
4. 将添加 <xref:System.Windows.Forms.MenuStrip> 到 MDI 子窗体。  
  
5. 在子窗体上，将 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 的属性设置 <xref:System.Windows.Forms.MenuStrip> 为 `false` 。  
  
6. <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MenuStrip> 当激活子窗体时，将菜单项添加到要合并到父窗体的子窗体中。  
  
7. 使用 <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> 子窗体中菜单项的属性 <xref:System.Windows.Forms.MenuStrip> 来控制它们合并到父窗体中的方式。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
