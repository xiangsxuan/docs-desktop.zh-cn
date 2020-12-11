---
title: 如何：管理 ToolStrip 溢出
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970560"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>如何：在 Windows 窗体中管理 ToolStrip 溢出

如果控件中的所有项都 <xref:System.Windows.Forms.ToolStrip> 不适合于分配的空间，则可以在上启用溢出功能， <xref:System.Windows.Forms.ToolStrip> 并确定特定的溢出行为 <xref:System.Windows.Forms.ToolStripItem> 。

当你添加 <xref:System.Windows.Forms.ToolStripItem> 的需要的空间超过了给定窗体的当前大小所分配的空间时 <xref:System.Windows.Forms.ToolStrip> ，将 <xref:System.Windows.Forms.ToolStripOverflowButton> 自动在上显示 <xref:System.Windows.Forms.ToolStrip> 。 <xref:System.Windows.Forms.ToolStripOverflowButton>随即出现，启用溢出的项将移至下拉溢出菜单中。 这使您可以自定义项的正确调整，并为其设置优先级 <xref:System.Windows.Forms.ToolStrip> 。 还可以通过使用 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 和 <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> 属性和事件更改项在溢出时的外观 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 。 如果您在设计时或运行时放大窗体，则在 <xref:System.Windows.Forms.ToolStripItem> 主窗体上可以显示更多的， <xref:System.Windows.Forms.ToolStrip> 在 <xref:System.Windows.Forms.ToolStripOverflowButton> 您减小窗体大小时，甚至可能会消失。

## <a name="to-enable-overflow-on-a-toolstrip-control"></a>对 ToolStrip 控件启用溢出

- 确保的 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 属性未设置为 `false` <xref:System.Windows.Forms.ToolStrip> 。 默认值为 `True`。

     当 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> `True` (默认的) 时， <xref:System.Windows.Forms.ToolStripItem> 当的内容 <xref:System.Windows.Forms.ToolStripItem> 超出水平的宽度或高度时，将发送到下拉溢出菜单 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> 。

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>指定特定 ToolStripItem 的溢出行为

- 将 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 的属性设置 <xref:System.Windows.Forms.ToolStripItem> 为所需的值。 可能的为 `Always` 、 `Never` 和 `AsNeeded` 。 默认值为 `AsNeeded`。

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 控件体系结构](toolstrip-control-architecture.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
