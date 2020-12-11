---
title: 停靠控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 02f1c26dcb322a39c41781c83d8c820bd2fd27e0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972039"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>如何：在 Windows 窗体上停靠控件

您可以将控件停靠到窗体的边缘，或者使控件填充控件的容器 () 窗体或容器控件。 例如，Windows 资源管理器将其控件停靠在 <xref:System.Windows.Forms.TreeView> 窗口的左侧，并将其 <xref:System.Windows.Forms.ListView> 控件停靠到窗口的右侧。 使用 <xref:System.Windows.Forms.Control.Dock%2A> 所有可见 Windows 窗体控件的属性来定义停靠模式。

> [!NOTE]
> 控件按 z 顺序反向停靠。

<xref:System.Windows.Forms.Control.Dock%2A>属性与 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性交互。 有关详细信息，请参阅 [AutoSize 属性概述](autosize-property-overview.md)。

## <a name="to-dock-a-control"></a>停靠控件

1. 在 Visual Studio 中，选择要停靠的控件。

2. 在 " **属性** " 窗口中，单击属性右侧的箭头 <xref:System.Windows.Forms.Control.Dock%2A> 。

   将显示一个编辑器，其中显示一系列表示窗体边缘和中心的框。

3. 单击表示要停靠控件的窗体边缘的按钮。 若要填充控件的窗体或容器控件的内容，请单击中心框。 单击 " **(无")** 禁用停靠。

   控件会自动调整控件的大小以适应停靠边缘的边界。

   > [!NOTE]
   > 继承的控件必须能够 `Protected` 停靠。 若要更改控件的访问级别，请在 "**属性**" 窗口中设置其 "**修饰符**" 属性。

## <a name="see-also"></a>另请参阅

- [Windows 窗体控件](index.md)
- [标记单个 Windows 窗体控件并提供它们的快捷方式](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
- [根据功能列出的 Windows 窗体控件](windows-forms-controls-by-function.md)
- [如何：在 FlowLayoutPanel 控件中锚定和停靠子控件](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [AutoSize 属性概述](autosize-property-overview.md)
- [如何：在 Windows 窗体上锚定控件](how-to-anchor-controls-on-windows-forms.md)
