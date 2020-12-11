---
title: 在 MenuStrip 控件中合并菜单项
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 9fc2b40ef23d72db51853c124095b734a7646cda
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972608"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>在 Windows 窗体 MenuStrip 控件中合并菜单项
如果有多文档界面 (MDI) 应用程序，则可以将菜单项或整个菜单从子窗体合并到父窗体的菜单中。  
  
 本主题介绍与在 MDI 应用程序中合并菜单项相关的基本概念。  
  
## <a name="general-concepts"></a>一般概念  
 合并过程涉及目标和源代码管理：  
  
- 目标是 <xref:System.Windows.Forms.MenuStrip> 要合并菜单项的主窗体或 MDI 父窗体上的控件。  
  
- 源是 <xref:System.Windows.Forms.MenuStrip> MDI 子窗体上的控件，它包含要合并到目标菜单中的菜单项。  
  
 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>属性标识其下拉列表将用当前 mdi 父窗体的 mdi 子级的标题填充的菜单项。 例如，通常列出当前在 " **窗口** " 菜单上打开的 MDI 子级。  
  
 <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A>属性标识哪个菜单项来自 <xref:System.Windows.Forms.MenuStrip> MDI 子窗体上的。  
  
 您可以手动或自动合并菜单项。 对于这两种方法，菜单项以相同的方式进行合并，但以不同的方式激活合并，如本主题后面的 "手动合并" 和 "自动合并" 部分所述。 在手动和自动合并中，每个合并操作都将影响下一个合并操作。  
  
 <xref:System.Windows.Forms.MenuStrip> 将菜单项从一个移 <xref:System.Windows.Forms.ToolStrip> 到另一个，而不是克隆它们，就像在中一样 <xref:System.Windows.Forms.MainMenu> 。  
  
## <a name="mergeaction-values"></a>MergeAction 值  
 您可以使用属性对源中的菜单项设置合并操作 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MergeAction> 。  
  
 下表介绍了可用合并操作的含义和典型用法。  
  
|MergeAction 值|描述|典型用法|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>| (默认) 会将源项添加到目标项集合的末尾。|当激活程序的一部分时，将菜单项添加到菜单的末尾。|  
|<xref:System.Windows.Forms.MergeAction.Insert>|在源项上设置的属性所指定的位置，将源项添加到目标项的集合中 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 。|当激活程序的一部分时，将菜单项添加到菜单的中间或开头。<br /><br /> 如果 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 这两个菜单项的值相同，则按相反顺序添加它们。 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>适当设置以保留原始订单。|  
|<xref:System.Windows.Forms.MergeAction.Replace>|查找文本匹配项， <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 如果未找到任何文本匹配项，则使用该值，然后将匹配的目标菜单项替换为源菜单项。|将目标菜单项替换为同一名称的具有不同操作的源菜单项。|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|查找文本匹配项， <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 如果未找到匹配项，则使用该值，然后将所有下拉项从源添加到目标。|生成在子菜单中插入或添加菜单项的菜单结构，或从子菜单中删除菜单项。 例如，可以将一个菜单项从 MDI 子级添加到主 " <xref:System.Windows.Forms.MenuStrip> **另存为**" 菜单。<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> 允许您在不执行任何操作的情况下浏览菜单结构。 它提供了一种方法来评估后续项。|  
|<xref:System.Windows.Forms.MergeAction.Remove>|查找文本匹配项， <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 如果未找到匹配项，则使用该值，然后从目标中删除该项。|从目标中删除菜单项 <xref:System.Windows.Forms.MenuStrip> 。|  
  
## <a name="manual-merging"></a>手动合并  
 只有 <xref:System.Windows.Forms.MenuStrip> 控件参与自动合并。 若要将其他控件（如和控件）的项组合在 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.StatusStrip> 一起，您必须 <xref:System.Windows.Forms.ToolStripManager.Merge%2A> <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> 根据需要在代码中调用和方法以手动合并这些项。  
  
## <a name="automatic-merging"></a>自动合并  
 通过激活源窗体，可以使用 MDI 应用程序的自动合并。 若要 <xref:System.Windows.Forms.MenuStrip> 在 MDI 应用程序中使用，请将 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> 属性设置为目标，以便在 <xref:System.Windows.Forms.MenuStrip> 源上执行的合并操作 <xref:System.Windows.Forms.MenuStrip> 反映在目标中 <xref:System.Windows.Forms.MenuStrip> 。  
  
 可以通过 <xref:System.Windows.Forms.MenuStrip> 在 MDI 源上激活来触发自动合并。 激活时，源 <xref:System.Windows.Forms.MenuStrip> 会合并到 MDI 目标中。 当新窗体变为活动状态时，将在最后一个窗体上恢复合并，并在新窗体上触发。 您可以根据 <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> 需要在每个上设置属性 <xref:System.Windows.Forms.ToolStripItem> ，并 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 在每个上设置属性来控制此行为 <xref:System.Windows.Forms.MenuStrip> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- [MenuStrip 控件](menustrip-control-windows-forms.md)
- [如何：使用 MenuStrip 创建 MDI 窗口列表](how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)
- [如何：为 MDI 应用程序设置自动菜单合并](how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
