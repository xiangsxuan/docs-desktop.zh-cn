---
title: 控件中的事件
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 27edaf2d895453d64d35ba6eff724df583a9b7dd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971307"
---
# <a name="events-in-windows-forms-controls"></a>Windows 窗体控件中的事件

Windows 窗体控件继承了60多个事件 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。 其中包括 <xref:System.Windows.Forms.Control.Paint> 导致控件绘制的事件、与显示窗口相关的事件，例如 <xref:System.Windows.Forms.Control.Resize> 和 <xref:System.Windows.Forms.Control.Layout> 事件，以及低级鼠标和键盘事件。 某些低级别事件会合成 <xref:System.Windows.Forms.Control> 给语义事件 <xref:System.Windows.Forms.Control.Click> ，例如和 <xref:System.Windows.Forms.Control.DoubleClick> 。 有关继承事件的详细信息，请参阅 <xref:System.Windows.Forms.Control> 。  
  
 如果自定义控件需要重写继承事件功能，请重写继承的 `On`*EventName* 方法，而不附加委托。 如果不熟悉 .NET Framework 中的事件模型，请参阅[从组件引发事件](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))。  
  
## <a name="see-also"></a>另请参阅

- [重写 OnPaint 方法](overriding-the-onpaint-method.md)
- [处理用户输入](handling-user-input.md)
- [定义事件](defining-an-event-in-windows-forms-controls.md)
- [事件](/dotnet/standard/events/index)
