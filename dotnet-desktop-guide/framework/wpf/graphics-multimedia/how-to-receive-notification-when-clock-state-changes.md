---
title: 如何：在时钟状态发生变化时接收通知
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
ms.openlocfilehash: dc3fffb88ce59ceb908d6febd2f078820513b641
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970846"
---
# <a name="how-to-receive-notification-when-a-clocks-state-changes"></a>如何：在时钟状态发生变化时接收通知
<xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated>当时钟变为无效时，将发生时钟事件 <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> ，例如当时钟开始或停止时。 您可以使用直接注册此事件 <xref:System.Windows.Media.Animation.Clock> ，也可以使用进行注册 <xref:System.Windows.Media.Animation.Timeline> 。  
  
 在下面的示例中，有一个 <xref:System.Windows.Media.Animation.Storyboard> 和两个 <xref:System.Windows.Media.Animation.DoubleAnimation> 对象用于对两个矩形的宽度进行动画处理。 <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>事件用于侦听时钟状态更改。  
  
## <a name="example"></a>示例  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 下图显示了动画在 (*Storyboard*) 的进度下进入的不同状态。  
  
 ![具有两个动画的演示图板的时钟状态](./media/graphicsmm-3timelines.png "graphicsmm_3timelines")  
  
 下表显示了触发 *Animation1* 事件的时间 <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> ：  
  
||||||||  
|-|-|-|-|-|-|-|  
|时间 (秒) |1|10|19|21|30|39|  
|状态|可用|活动|已停止|可用|活动|已停止|  
  
 下表显示了触发 *Animation2* 事件的时间 <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> ：  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|时间 (秒) |1|9|11|19|21|29|31|39|  
|状态|活动|好|活动|已停止|活动|好|活动|已停止|  
  
 请注意， *Animation1* 的  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> 事件将在10秒后激发，即使其状态仍然存在 <xref:System.Windows.Media.Animation.ClockState.Active> 。 这是因为它的状态在10秒内发生了更改，但它从 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Filling> <xref:System.Windows.Media.Animation.ClockState.Active> 相同的时钟周期更改为，然后再改回。
