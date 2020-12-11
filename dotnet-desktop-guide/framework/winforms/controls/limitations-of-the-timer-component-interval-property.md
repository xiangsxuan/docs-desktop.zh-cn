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
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="58394-102">Windows 窗体 Timer 组件的 Interval 属性的限制</span><span class="sxs-lookup"><span data-stu-id="58394-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>

<span data-ttu-id="58394-103">Windows 窗体 <xref:System.Windows.Forms.Timer> 组件有一个 <xref:System.Windows.Forms.Timer.Interval%2A> 属性，该属性指定一个计时器事件与下一个计时器事件之间的间隔时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="58394-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="58394-104">除非禁用了该组件，否则计时器将继续以 <xref:System.Windows.Forms.Timer.Tick> 大致相等的时间间隔接收事件。</span><span class="sxs-lookup"><span data-stu-id="58394-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="58394-105">此组件专为 Windows 窗体环境设计。</span><span class="sxs-lookup"><span data-stu-id="58394-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="58394-106">如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="58394-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="58394-107">Interval 属性</span><span class="sxs-lookup"><span data-stu-id="58394-107">The Interval Property</span></span>  

 <span data-ttu-id="58394-108"><xref:System.Windows.Forms.Timer.Interval%2A>编程组件时，属性具有几个要考虑的限制 <xref:System.Windows.Forms.Timer> ：</span><span class="sxs-lookup"><span data-stu-id="58394-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
- <span data-ttu-id="58394-109">如果你的应用程序或另一个应用程序对系统的需求（例如长循环、密集型计算或驱动器、网络或端口访问）发出大量要求，则你的应用程序可能无法在属性指定的情况下获取计时器事件 <xref:System.Windows.Forms.Timer.Interval%2A> 。</span><span class="sxs-lookup"><span data-stu-id="58394-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
- <span data-ttu-id="58394-110">不保证时间间隔刚好在一段时间内。</span><span class="sxs-lookup"><span data-stu-id="58394-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="58394-111">为了确保准确性，计时器应根据需要检查系统时钟，而不是尝试跟踪内部累积的时间。</span><span class="sxs-lookup"><span data-stu-id="58394-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
- <span data-ttu-id="58394-112">属性的精度 <xref:System.Windows.Forms.Timer.Interval%2A> 以毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="58394-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="58394-113">某些计算机提供分辨率高于毫秒的高分辨率计数器。</span><span class="sxs-lookup"><span data-stu-id="58394-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="58394-114">此类计数器的可用性取决于计算机的处理器硬件。</span><span class="sxs-lookup"><span data-stu-id="58394-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="58394-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58394-115">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="58394-116">Timer 组件</span><span class="sxs-lookup"><span data-stu-id="58394-116">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="58394-117">Timer 组件概述</span><span class="sxs-lookup"><span data-stu-id="58394-117">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
