---
title: TrackBar 控件概述
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 6901405100df4633c84850757f55b756bc9a0199
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973047"
---
# <a name="trackbar-control-overview-windows-forms"></a>TrackBar 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.TrackBar> (控件有时也称为 "滑块" 控件) 用于在大量信息中导航，或用于直观地调整数字设置。 <xref:System.Windows.Forms.TrackBar>控件包含两部分：滚动块（也称为滑块）和刻度线。 滚动块是可以调整的部分。 其位置与属性相对应 <xref:System.Windows.Forms.TrackBar.Value%2A> 。 刻度线是按固定间隔分隔的可视指示器。 跟踪条以指定的增量移动，并可水平或垂直对齐。 例如，您可以使用跟踪栏来控制系统的光标闪烁速率或鼠标速度。  
  
## <a name="key-properties"></a>键属性  
 控件的键属性 <xref:System.Windows.Forms.TrackBar> 为、、 <xref:System.Windows.Forms.TrackBar.Value%2A> <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> <xref:System.Windows.Forms.TrackBar.Minimum%2A> 和 <xref:System.Windows.Forms.TrackBar.Maximum%2A> 。 <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> 刻度的间距。 <xref:System.Windows.Forms.TrackBar.Minimum%2A> 和 <xref:System.Windows.Forms.TrackBar.Maximum%2A> 是可在跟踪条上表示的最小值和最大值。  
  
 另外两个重要的属性是 <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 和 <xref:System.Windows.Forms.TrackBar.LargeChange%2A> 。 属性的值 <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 是指在按下左箭头键或右箭头键时移动的位置数。 属性的值 <xref:System.Windows.Forms.TrackBar.LargeChange%2A> 是指在按下 PAGE UP 或 PAGE DOWN 键时移动的位置数，或响应滚动块两侧的跟踪条的鼠标单击。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.TrackBar>
- [TrackBar 控件](trackbar-control-windows-forms.md)
