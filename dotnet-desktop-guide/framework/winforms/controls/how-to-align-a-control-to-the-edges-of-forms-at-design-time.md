---
title: 如何：设计时将控件与窗体边缘对齐
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b08e01eb9adb984a32a8fc435cf1f3b93b159a14
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971904"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a>如何：设计时将控件与窗体边缘对齐

可以通过设置属性的值，使控件与窗体的边缘对齐 <xref:System.Windows.Forms.Control.Dock%2A> 。 此属性指定控件在窗体中的驻留位置。 可以将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为下列值：

|设置|控件上的效果|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|停靠到窗体底部。|
|<xref:System.Windows.Forms.DockStyle.Fill>|占据窗体中的所有剩余空间。|
|<xref:System.Windows.Forms.DockStyle.Left>|停靠到窗体的左侧。|
|<xref:System.Windows.Forms.DockStyle.None>|不会停靠在任何位置，并且它会出现在由其指定的位置 <xref:System.Windows.Forms.Control.Location%2A> 。|
|<xref:System.Windows.Forms.DockStyle.Right>|停靠到窗体的右侧。|
|<xref:System.Windows.Forms.DockStyle.Top>|停靠到窗体的顶部。|

也可以在代码中设置这些值。 有关详细信息，请参阅 [如何：将控件与窗体边缘对齐](how-to-align-a-control-to-the-edges-of-forms.md)。

## <a name="set-the-dock-property-for-your-control-at-design-time"></a>在设计时设置控件的 Dock 属性

1. 在 Visual Studio 的 "Windows 窗体设计器中，选择控件。

2. 在 " **属性** " 窗口中，单击属性旁边的下拉框 <xref:System.Windows.Forms.Control.Dock%2A> 。

     显示了六种可能的设置的图形界面 <xref:System.Windows.Forms.Control.Dock%2A> 。

3. 选择适当的设置。

4. 控件现在将按设置指定的方式停靠。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [如何：使控件与窗体边缘对齐](how-to-align-a-control-to-the-edges-of-forms.md)
- [演练：使用对齐线在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [如何：在 Windows 窗体上锚定控件](how-to-anchor-controls-on-windows-forms.md)
- [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [如何：在 FlowLayoutPanel 控件中锚定和停靠子控件](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [设计时开发 Windows 窗体控件](developing-windows-forms-controls-at-design-time.md)
