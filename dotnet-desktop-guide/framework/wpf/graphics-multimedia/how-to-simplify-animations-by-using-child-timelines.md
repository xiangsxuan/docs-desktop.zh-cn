---
title: 如何：使用子时间线简化动画
ms.date: 03/30/2017
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
ms.openlocfilehash: 21a297208be045eea79d6f5ca6c8eac016d26345
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971009"
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>如何：使用子时间线简化动画
此示例演示如何使用子对象简化动画 <xref:System.Windows.Media.Animation.ParallelTimeline> 。 <xref:System.Windows.Media.Animation.Storyboard>是的一种类型 <xref:System.Windows.Media.Animation.Timeline> ，它为其包含的时间线提供目标信息。 使用 <xref:System.Windows.Media.Animation.Storyboard> 提供时间线目标信息，包括对象和属性信息。  
  
 若要开始动画，请使用一个或多个 <xref:System.Windows.Media.Animation.ParallelTimeline> 对象作为的嵌套子元素 <xref:System.Windows.Media.Animation.Storyboard> 。 这些 <xref:System.Windows.Media.Animation.ParallelTimeline> 对象可以包含其他动画，因此，可以更好地封装复杂动画中的计时序列。 例如，如果您 <xref:System.Windows.Controls.TextBlock> 在同一中对一个和多个形状进行动画处理， <xref:System.Windows.Media.Animation.Storyboard> 则可以将和形状的动画分离，使每个形状都位于 <xref:System.Windows.Controls.TextBlock> 一个单独的中 <xref:System.Windows.Media.Animation.ParallelTimeline> 。 由于每个 <xref:System.Windows.Media.Animation.ParallelTimeline> 都具有其自己的 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 和的所有子元素 <xref:System.Windows.Media.Animation.ParallelTimeline> ，因此可以 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 更好地封装计时。  
  
 下面的示例将 (对象的两部分文本 <xref:System.Windows.Controls.TextBlock>) 从同一中 <xref:System.Windows.Media.Animation.Storyboard> 。 <xref:System.Windows.Media.Animation.ParallelTimeline>封装一个对象的动画 <xref:System.Windows.Controls.TextBlock> 。  
  
 **性能说明：** 虽然你可以 <xref:System.Windows.Media.Animation.Storyboard> 将时间线嵌套在彼此 <xref:System.Windows.Media.Animation.ParallelTimeline> 之间，但更适合嵌套，因为它们需要更少的开销。  (<xref:System.Windows.Media.Animation.Storyboard> 类继承自 <xref:System.Windows.Media.Animation.ParallelTimeline> 类。 )   
  
## <a name="example"></a>示例  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [指定情节提要动画之间的 HandoffBehavior](how-to-specify-handoffbehavior-between-storyboard-animations.md)
