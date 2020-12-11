---
title: 如何：在 ToolStrip 控件中使用工具提示
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 3f383b6cccba7825637ea65a0e13280b91b406c9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972646"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>如何：在 ToolStrip 控件中使用工具提示
可以 <xref:System.Windows.Forms.ToolTip> <xref:System.Windows.Forms.ToolStrip> 通过将控件的属性设置为，为所需的控件显示 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> `true` 。  
  
### <a name="to-display-a-tooltip"></a>显示工具提示  
  
- 将 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 控件的属性设置为 `true` 。  
  
     的默认值为，而的默认值 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> `true` <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> 为 `false` 。  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>使用 ToolStripButton 的工具提示文本的 ToolTipText 属性  
  
1. 将 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 按钮的属性设置为 `true` 。  
  
2. 将 <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> 按钮的属性设置为 `false` 。  
  
     `AutoToolTip` `true` 默认情况下，属性为 <xref:System.Windows.Forms.ToolStripButton> 、 <xref:System.Windows.Forms.ToolStripDropDownButton> 和 <xref:System.Windows.Forms.ToolStripSplitButton> 。  
  
     <xref:System.Windows.Forms.ToolStripButton> `Text` 默认情况下，为文本使用其属性 <xref:System.Windows.Forms.ToolTip> 。 使用此过程在中显示自定义文本 <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip> 。  
  
> [!NOTE]
> 如果将设置 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 为 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> 或 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image> ，则按钮上不会显示任何文本，但会出现工具提示。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
