---
title: 如何：设置动画的持续时间
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: bdae1689ffeb8c54d756b9debbd26d57a052892d
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973843"
---
# <a name="how-to-set-a-duration-for-an-animation"></a>如何：设置动画的持续时间
<xref:System.Windows.Media.Animation.Timeline>表示时间段，并且该时间段的长度由时间线的确定 <xref:System.Windows.Duration> 。 当 <xref:System.Windows.Media.Animation.Timeline> 到达其持续时间的终点时，它将停止播放。 如果 <xref:System.Windows.Media.Animation.Timeline> 有子时间线，它们也会停止播放。 对于动画， <xref:System.Windows.Duration> 指定动画从其起始值过渡到其结束值需要多长时间。  
  
 您可以 <xref:System.Windows.Duration> 使用特定的、有限的时间或特殊值或来 <xref:System.Windows.Duration.Automatic%2A> 指定 <xref:System.Windows.Duration.Forever%2A> 。 动画的持续时间必须始终为时间值，因为动画必须始终具有定义的有限长度，否则，动画将不知道如何在其目标值之间进行转换。 )  (对象（例如和）的容器时间线 <xref:System.Windows.Media.Animation.TimelineGroup> <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.ParallelTimeline> 的默认持续时间为 <xref:System.Windows.Duration.Automatic%2A> ，这意味着在其最后一个子级停止播放时，它们会自动结束。  
  
 在下面的示例中，的宽度、高度和填充颜色 <xref:System.Windows.Shapes.Rectangle> 都进行了动画处理。 持续时间在动画和容器时间线上设置，产生动画效果，包括控制动画的感知速度，并将子时间线的持续时间替换为容器时间线的持续时间。  
  
## <a name="example"></a>示例  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Duration>
- [动画概述](animation-overview.md)
