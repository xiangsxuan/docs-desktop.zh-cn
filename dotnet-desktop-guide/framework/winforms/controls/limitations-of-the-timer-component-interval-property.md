---
title: "\"计时器组件间隔\" 属性的限制"
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 90023a20b32cc4f5709d35f4e8c0a339e1d46751
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972626"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Windows 窗体 Timer 组件的 Interval 属性的限制

Windows 窗体 <xref:System.Windows.Forms.Timer> 组件有一个 <xref:System.Windows.Forms.Timer.Interval%2A> 属性，该属性指定一个计时器事件与下一个计时器事件之间的间隔时间（以毫秒为单位）。 除非禁用了该组件，否则计时器将继续以 <xref:System.Windows.Forms.Timer.Tick> 大致相等的时间间隔接收事件。  
  
 此组件专为 Windows 窗体环境设计。 如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。  
  
## <a name="the-interval-property"></a>Interval 属性  

 <xref:System.Windows.Forms.Timer.Interval%2A>编程组件时，属性具有几个要考虑的限制 <xref:System.Windows.Forms.Timer> ：  
  
- 如果你的应用程序或另一个应用程序对系统的需求（例如长循环、密集型计算或驱动器、网络或端口访问）发出大量要求，则你的应用程序可能无法在属性指定的情况下获取计时器事件 <xref:System.Windows.Forms.Timer.Interval%2A> 。  
  
- 不保证时间间隔刚好在一段时间内。 为了确保准确性，计时器应根据需要检查系统时钟，而不是尝试跟踪内部累积的时间。  
  
- 属性的精度 <xref:System.Windows.Forms.Timer.Interval%2A> 以毫秒为单位。 某些计算机提供分辨率高于毫秒的高分辨率计数器。 此类计数器的可用性取决于计算机的处理器硬件。
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Timer>
- [Timer 组件](timer-component-windows-forms.md)
- [Timer 组件概述](timer-component-overview-windows-forms.md)
