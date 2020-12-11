---
title: Timer 组件概述
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: ca1a7bf304da3fd602e3b0c36bb3aa20cd6b1345
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970889"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="0f5a1-102">Timer 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="0f5a1-102">Timer Component Overview (Windows Forms)</span></span>

<span data-ttu-id="0f5a1-103">Windows 窗体 <xref:System.Windows.Forms.Timer> 是一种按固定事件间隔引发事件的组件。</span><span class="sxs-lookup"><span data-stu-id="0f5a1-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="0f5a1-104">此组件专为 Windows 窗体环境设计。</span><span class="sxs-lookup"><span data-stu-id="0f5a1-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="0f5a1-105">如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="0f5a1-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="0f5a1-106">键属性、方法和事件</span><span class="sxs-lookup"><span data-stu-id="0f5a1-106">Key Properties, Methods, and Events</span></span>  

 <span data-ttu-id="0f5a1-107">间隔的长度由 <xref:System.Windows.Forms.Timer.Interval%2A> 属性定义，该属性的值以毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="0f5a1-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="0f5a1-108">启用组件后，将 <xref:System.Windows.Forms.Timer.Tick> 每隔一个间隔引发一次事件。</span><span class="sxs-lookup"><span data-stu-id="0f5a1-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="0f5a1-109">这是要在其中添加要执行的代码的位置。</span><span class="sxs-lookup"><span data-stu-id="0f5a1-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="0f5a1-110">有关详细信息，请参阅 [如何：按设置的时间间隔运行过程和 Windows 窗体定时器组件](run-procedures-at-set-intervals-with-wf-timer-component.md)。</span><span class="sxs-lookup"><span data-stu-id="0f5a1-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="0f5a1-111">组件的关键方法 <xref:System.Windows.Forms.Timer> 为 <xref:System.Windows.Forms.Timer.Start%2A> 和 <xref:System.Windows.Forms.Timer.Stop%2A> ，这会打开和关闭计时器。</span><span class="sxs-lookup"><span data-stu-id="0f5a1-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="0f5a1-112">当计时器关闭时，它将重置;没有办法暂停 <xref:System.Windows.Forms.Timer> 组件。</span><span class="sxs-lookup"><span data-stu-id="0f5a1-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f5a1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f5a1-113">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="0f5a1-114">Timer 组件</span><span class="sxs-lookup"><span data-stu-id="0f5a1-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="0f5a1-115">Windows 窗体 Timer 组件的 Interval 属性的限制</span><span class="sxs-lookup"><span data-stu-id="0f5a1-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
