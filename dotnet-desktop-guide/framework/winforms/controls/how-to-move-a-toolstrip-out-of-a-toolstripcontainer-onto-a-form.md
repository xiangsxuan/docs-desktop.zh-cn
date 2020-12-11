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
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="e3e2c-102">如何：将 ToolStrip 从 ToolStripContainer 移到窗体上</span><span class="sxs-lookup"><span data-stu-id="e3e2c-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="e3e2c-103">使用以下过程将移 <xref:System.Windows.Forms.ToolStrip> 出 <xref:System.Windows.Forms.ToolStripContainer> 到窗体上。</span><span class="sxs-lookup"><span data-stu-id="e3e2c-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>

## <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="e3e2c-104">将 ToolStrip 从 ToolStripContainer 移到窗体上</span><span class="sxs-lookup"><span data-stu-id="e3e2c-104">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>

1. <span data-ttu-id="e3e2c-105">选择 <xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="e3e2c-105">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>

2. <span data-ttu-id="e3e2c-106"><xref:System.Windows.Forms.ToolStrip>按 CTRL + X 剪切，或右键单击 <xref:System.Windows.Forms.ToolStrip> 并从上下文菜单中选择 "**剪切**"。</span><span class="sxs-lookup"><span data-stu-id="e3e2c-106">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>

3. <span data-ttu-id="e3e2c-107">选择窗体。</span><span class="sxs-lookup"><span data-stu-id="e3e2c-107">Select the form.</span></span>

4. <span data-ttu-id="e3e2c-108"><xref:System.Windows.Forms.ToolStrip>按 CTRL + V 粘贴，或从 "**编辑**" 菜单中选择 "**粘贴**"。</span><span class="sxs-lookup"><span data-stu-id="e3e2c-108">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>

5. <span data-ttu-id="e3e2c-109">将 <xref:System.Windows.Forms.ToolStrip.Dock%2A> 的属性设置 <xref:System.Windows.Forms.ToolStrip> 为 **Top**。</span><span class="sxs-lookup"><span data-stu-id="e3e2c-109">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3e2c-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3e2c-110">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="e3e2c-111">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="e3e2c-111">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
