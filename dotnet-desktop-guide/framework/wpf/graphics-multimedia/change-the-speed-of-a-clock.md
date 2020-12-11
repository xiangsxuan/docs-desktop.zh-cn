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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970088"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>如何：在不更改时间线速度的情况下更改时钟速度
使用 <xref:System.Windows.Media.Animation.ClockController> 对象的 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 属性可以更改的速度， <xref:System.Windows.Media.Animation.Clock> 而无需更改时钟的 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> <xref:System.Windows.Media.Animation.Timeline> 。 在下面的示例中， <xref:System.Windows.Media.Animation.ClockController> 用于以交互方式修改 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 时钟的。 <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated>事件和时钟的 <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> 属性用于在每次更改其交互式时显示时钟的当前全局速度 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 。  
  
## <a name="example"></a>示例  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
