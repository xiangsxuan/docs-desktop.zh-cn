---
title: HScrollBar 和 VScrollBar 控件概述
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972642"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>HScrollBar 控件和 VScrollBar 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.ScrollBar> 控件用于通过在应用程序或控件中水平或垂直滚动来轻松地浏览较长的项列表或大量的信息。 滚动条是 Windows 界面的公共元素，因此该 <xref:System.Windows.Forms.ScrollBar> 控件通常用于不是从类派生的控件 <xref:System.Windows.Forms.ScrollableControl> 。 同样，许多开发人员 <xref:System.Windows.Forms.ScrollBar> 在创作自己的用户控件时选择合并控件。  
  
 <xref:System.Windows.Forms.HScrollBar> (水平) 和 <xref:System.Windows.Forms.VScrollBar> (垂直) 控件独立于其他控件操作，并且具有其自己的一组事件、属性和方法。 <xref:System.Windows.Forms.ScrollBar> 控件与附加到文本框、列表框、组合框或 MDI 窗体的内置滚动条不同 (<xref:System.Windows.Forms.TextBox> 控件具有 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 用于显示或隐藏附加到控件) 的滚动条的属性。  
  
 这些 <xref:System.Windows.Forms.ScrollBar> 控件使用 <xref:System.Windows.Forms.ScrollBar.Scroll> 事件监视滚动框 (有时称为滚动条) 的滚动框的移动。 使用 <xref:System.Windows.Forms.ScrollBar.Scroll> 事件可在拖动滚动条值时，提供对滚动条值的访问。  
  
## <a name="value-property"></a>Value 属性  
 <xref:System.Windows.Forms.ScrollBar.Value%2A>默认情况下，属性 (为 0) 是 `integer` 与滚动条中滚动框的位置相对应的值。 当滚动框位置为最小值时，它会移动到水平滚动条的最左边位置 () 或垂直滚动条) 的顶部位置 (。 当滚动框处于最大值时，滚动框会移动到最右侧或底部位置。 同样，范围底部和顶部中间的值将在滚动条的中间放置滚动框的上边缘。  
  
 除了使用鼠标单击更改滚动条值以外，用户还可以将滚动框拖动到滚动条上的任意点。 生成的值取决于滚动框的位置，但它始终在 <xref:System.Windows.Forms.ScrollBar.Minimum%2A> 用户设置的到属性的范围内 <xref:System.Windows.Forms.ScrollBar.Maximum%2A> 。  
  
## <a name="largechange-and-smallchange-properties"></a>LargeChange 和 SmallChange 属性  
 当用户按下 PAGE UP 或 PAGE DOWN 键或单击滚动框两侧的滚动条轨道时， <xref:System.Windows.Forms.ScrollBar.Value%2A> 属性将根据属性中设置的值进行更改 <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> 。  
  
 当用户按下某个箭头键或单击某个滚动条按钮时， <xref:System.Windows.Forms.ScrollBar.Value%2A> 属性将根据属性中设置的值进行更改 <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
