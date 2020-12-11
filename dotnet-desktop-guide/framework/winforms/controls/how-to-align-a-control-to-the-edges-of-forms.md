---
title: 如何：使控件与窗体边缘对齐
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: 5d662489b7e31f391bbd508409e69c091a25592c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971769"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a>如何：使控件与窗体边缘对齐

通过设置 <xref:System.Windows.Forms.Control.Dock%2A> 属性，可以使控件与窗体的边缘对齐。 此属性指定控件在窗体中的驻留位置。 可以将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为下列值：

|设置|控件上的效果|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|停靠到窗体底部。|
|<xref:System.Windows.Forms.DockStyle.Fill>|占据窗体中的所有剩余空间。|
|<xref:System.Windows.Forms.DockStyle.Left>|停靠到窗体的左侧。|
|<xref:System.Windows.Forms.DockStyle.None>|不在任何位置停靠，它显示在由 <xref:System.Windows.Forms.Control.Location%2A> 属性指定的位置。|
|<xref:System.Windows.Forms.DockStyle.Right>|停靠到窗体的右侧。|
|<xref:System.Windows.Forms.DockStyle.Top>|停靠到窗体的顶部。|

Visual Studio 中具有对此功能的设计时支持。

## <a name="set-the-dock-property-for-your-control-at-run-time"></a>在运行时设置控件的 Dock 属性

在代码中将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为适当的值。

```vb
' To set the Dock property internally.
Me.Dock = DockStyle.Top
' To set the Dock property from another object.
UserControl1.Dock = DockStyle.Top
```

```csharp
// To set the Dock property internally.
this.Dock = DockStyle.Top;
// To set the Dock property from another object.
UserControl1.Dock = DockStyle.Top;
```

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [使用 .NET Framework 开发自定义 Windows 窗体控件](developing-custom-windows-forms-controls.md)
- [如何：在 FlowLayoutPanel 控件中锚定和停靠子控件](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [AutoSize 属性概述](autosize-property-overview.md)
