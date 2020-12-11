---
title: 如何：更改 ToolStrip 项的间距和对齐方式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971884"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>如何：在 Windows 窗体中更改 ToolStrip 项的间距和对齐方式
<xref:System.Windows.Forms.ToolStrip>控件完全支持布局功能，如调整大小、控件的间距（ <xref:System.Windows.Forms.ToolStripItem> 相对于控件）、上控件的排列方式 <xref:System.Windows.Forms.ToolStrip> 和相对于控件的间距 <xref:System.Windows.Forms.ToolStrip> 。  
  
 由于属性的默认值 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 为，因此 `true` 控件将自动调整大小，除非将 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 属性设置为 `false` 。  
  
### <a name="to-manually-size-a-toolstripitem"></a>手动调整 ToolStripItem 的大小  
  
1. <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>对于关联的控件，将属性设置为 `false` 。  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. 按所 <xref:System.Windows.Forms.ToolStripItem.Size%2A> 需方式为关联的设置属性 <xref:System.Windows.Forms.ToolStripItem> 。  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>设置 ToolStripItem 的间距  
  
1. 在关联控件的属性中插入所需的值（以像素为单位） <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 。  
  
     此属性的值 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 按如下顺序指定项与相邻项之间的间距： Left、Top、Right 和底端。  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>将 ToolStripItem 与 ToolStrip 右端对齐  
  
1. <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>对于关联的控件，将属性设置为 <xref:System.Windows.Forms.ToolStripItemAlignment.Right> 。 默认情况下， <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 设置为 <xref:System.Windows.Forms.ToolStripItemAlignment.Left> ，它将控件与的左侧对齐 <xref:System.Windows.Forms.ToolStrip> 。  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>在 ToolStrip 上排列 ToolStrip 项  
  
- 将 <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 属性设置为所需的值 <xref:System.Windows.Forms.ToolStripLayoutStyle> 。  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 控件体系结构](toolstrip-control-architecture.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
