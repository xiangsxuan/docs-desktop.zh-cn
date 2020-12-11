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
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="c5a3b-102">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="c5a3b-102">Events in Windows Forms Controls</span></span>

<span data-ttu-id="c5a3b-103">Windows 窗体控件继承了60多个事件 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="c5a3b-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c5a3b-104">其中包括 <xref:System.Windows.Forms.Control.Paint> 导致控件绘制的事件、与显示窗口相关的事件，例如 <xref:System.Windows.Forms.Control.Resize> 和 <xref:System.Windows.Forms.Control.Layout> 事件，以及低级鼠标和键盘事件。</span><span class="sxs-lookup"><span data-stu-id="c5a3b-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="c5a3b-105">某些低级别事件会合成 <xref:System.Windows.Forms.Control> 给语义事件 <xref:System.Windows.Forms.Control.Click> ，例如和 <xref:System.Windows.Forms.Control.DoubleClick> 。</span><span class="sxs-lookup"><span data-stu-id="c5a3b-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="c5a3b-106">有关继承事件的详细信息，请参阅 <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="c5a3b-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="c5a3b-107">如果自定义控件需要重写继承事件功能，请重写继承的 `On`*EventName* 方法，而不附加委托。</span><span class="sxs-lookup"><span data-stu-id="c5a3b-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="c5a3b-108">如果不熟悉 .NET Framework 中的事件模型，请参阅[从组件引发事件](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="c5a3b-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a3b-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5a3b-109">See also</span></span>

- [<span data-ttu-id="c5a3b-110">重写 OnPaint 方法</span><span class="sxs-lookup"><span data-stu-id="c5a3b-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="c5a3b-111">处理用户输入</span><span class="sxs-lookup"><span data-stu-id="c5a3b-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="c5a3b-112">定义事件</span><span class="sxs-lookup"><span data-stu-id="c5a3b-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="c5a3b-113">事件</span><span class="sxs-lookup"><span data-stu-id="c5a3b-113">Events</span></span>](/dotnet/standard/events/index)
