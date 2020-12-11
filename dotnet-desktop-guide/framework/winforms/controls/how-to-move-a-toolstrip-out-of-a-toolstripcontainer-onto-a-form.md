---
title: 如何：将 ToolStrip 从 ToolStripContainer 移到窗体上
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: c6519add6789485d41146633abb5e11f80913649
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971156"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>如何：将 ToolStrip 从 ToolStripContainer 移到窗体上
使用以下过程将移 <xref:System.Windows.Forms.ToolStrip> 出 <xref:System.Windows.Forms.ToolStripContainer> 到窗体上。

## <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>将 ToolStrip 从 ToolStripContainer 移到窗体上

1. 选择 <xref:System.Windows.Forms.ToolStrip>。

2. <xref:System.Windows.Forms.ToolStrip>按 CTRL + X 剪切，或右键单击 <xref:System.Windows.Forms.ToolStrip> 并从上下文菜单中选择 "**剪切**"。

3. 选择窗体。

4. <xref:System.Windows.Forms.ToolStrip>按 CTRL + V 粘贴，或从 "**编辑**" 菜单中选择 "**粘贴**"。

5. 将 <xref:System.Windows.Forms.ToolStrip.Dock%2A> 的属性设置 <xref:System.Windows.Forms.ToolStrip> 为 **Top**。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
