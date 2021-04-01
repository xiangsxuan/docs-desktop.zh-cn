---
title: 如何：在不更改时间线速度的情况下更改时钟速度
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 19e6874b9b472cb4a5f716677f99af03f2b73b10
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970088"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a><span data-ttu-id="da046-102">如何：在不更改时间线速度的情况下更改时钟速度</span><span class="sxs-lookup"><span data-stu-id="da046-102">How to: Change the Speed of a Clock Without Changing the Speed of Its Timeline</span></span>
<span data-ttu-id="da046-103">使用 <xref:System.Windows.Media.Animation.ClockController> 对象的 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 属性可以更改的速度， <xref:System.Windows.Media.Animation.Clock> 而无需更改时钟的 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> <xref:System.Windows.Media.Animation.Timeline> 。</span><span class="sxs-lookup"><span data-stu-id="da046-103">A <xref:System.Windows.Media.Animation.ClockController> object's <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> property enables you to change the speed of a <xref:System.Windows.Media.Animation.Clock> without altering the <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> of the clock's <xref:System.Windows.Media.Animation.Timeline>.</span></span> <span data-ttu-id="da046-104">在下面的示例中， <xref:System.Windows.Media.Animation.ClockController> 用于以交互方式修改 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 时钟的。</span><span class="sxs-lookup"><span data-stu-id="da046-104">In the following example, a <xref:System.Windows.Media.Animation.ClockController> is used to interactively modify the <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> of a clock.</span></span> <span data-ttu-id="da046-105"><xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated>事件和时钟的 <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> 属性用于在每次更改其交互式时显示时钟的当前全局速度 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 。</span><span class="sxs-lookup"><span data-stu-id="da046-105">The <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> event and the clock's <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> property are used to display the clock's current global speed each time its interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> is changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da046-106">示例</span><span class="sxs-lookup"><span data-stu-id="da046-106">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
