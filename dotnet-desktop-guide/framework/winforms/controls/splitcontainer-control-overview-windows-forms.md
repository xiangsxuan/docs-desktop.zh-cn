---
title: SplitContainer 控件概述
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: f697629020342d534265c633707fed8c4a460e20
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971997"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>SplitContainer 控件概述（Windows 窗体）

Windows 窗体 <xref:System.Windows.Forms.SplitContainer> 控件可视为一个复合控件；它是由可移动条隔开的两个面板。 当鼠标指针位于条上方时，指针将改变形状以表示条可移动。  
  
> [!IMPORTANT]
> 在 " **工具箱**" 中， <xref:System.Windows.Forms.SplitContainer> 控件替换 <xref:System.Windows.Forms.Splitter> Visual Studio 早期版本中的控件。 相较于 <xref:System.Windows.Forms.Splitter> 控件，优先选择 <xref:System.Windows.Forms.SplitContainer> 控件。 <xref:System.Windows.Forms.Splitter> 类仍包含在 .NET Framework 中，以便与现有应用程序兼容，但我们强烈建议为新项目使用 <xref:System.Windows.Forms.SplitContainer> 控件。  
  
 使用 <xref:System.Windows.Forms.SplitContainer> 控件，可以创建复杂的用户界面; 通常情况下，在一个面板中进行选择将确定哪些对象显示在其他面板中。 这种安排对于显示和浏览信息非常有效。 通过具有两个面板，可以在区域、栏或 "拆分器" 中聚合信息，使用户可以轻松地调整面板的大小。  
  
 <xref:System.Windows.Forms.SplitContainer>还可以嵌套多个控件，并将第二个 <xref:System.Windows.Forms.SplitContainer> 控件水平定向，以创建顶部面板和底部面板。  
  
 请注意， <xref:System.Windows.Forms.SplitContainer> 控件在默认情况下可以通过键盘访问; 如果属性设置为，则用户可以按箭头键移动拆分器 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> `false` 。  
  
 <xref:System.Windows.Forms.SplitContainer.Orientation%2A>控件的属性 <xref:System.Windows.Forms.SplitContainer> 决定拆分器的方向，而不是控件本身的方向。 因此，当此属性设置为时 <xref:System.Windows.Forms.Orientation.Vertical> ，拆分器将从上到下运行，从而创建左右面板。  
  
 此外，请注意，属性的值 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 因属性的值而异 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 。 有关详细信息，请参阅 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 属性。  
  
 您还可以限制控件的大小和移动 <xref:System.Windows.Forms.SplitContainer> 。 <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>属性确定控件调整大小后哪个面板将保持相同的大小 <xref:System.Windows.Forms.SplitContainer> ，并且 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性确定是否可通过键盘或鼠标来可移动拆分器。  
  
> [!NOTE]
> 即使将 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性设置为，也 `true` 可能仍以编程方式移动拆分器; 例如，使用 <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 属性。  
  
 最后，控件的每个面板 <xref:System.Windows.Forms.SplitContainer> 都有属性来确定其各个大小。  
  
## <a name="commonly-used-properties-methods-and-events"></a>常用的属性、方法和事件  
  
|名称|描述|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 属性|确定调整控件大小后哪个面板的大小将保持不变 <xref:System.Windows.Forms.SplitContainer> 。|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性|确定是否可以用键盘或鼠标移动拆分器。|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A> 属性|确定拆分器是垂直排列还是水平排列。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 属性|确定从左边缘或上边缘到可移动拆分栏的距离（以像素为单位）。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 属性|确定用户可以移动拆分器的最小距离（以像素为单位）。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> 属性|确定拆分器的粗细（以像素为单位）。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving> 事件|在拆分器移动时发生。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved> 事件|在拆分器移动后发生。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer 控件](splitcontainer-control-windows-forms.md)
- [SplitContainer 控件示例](/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
