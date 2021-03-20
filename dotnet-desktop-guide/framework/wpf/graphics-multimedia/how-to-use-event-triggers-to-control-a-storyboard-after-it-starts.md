---
title: 如何：在演示图板启动之后使用事件触发器来控制演示图板
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 1cd9e35524198e05b919f1225209388b9805520b
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667702"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>如何：在演示图板启动之后使用事件触发器来控制演示图板

此示例演示如何 <xref:System.Windows.Media.Animation.Storyboard> 在启动后对其进行控制。 若要 <xref:System.Windows.Media.Animation.Storyboard> 使用启动 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，请使用 <xref:System.Windows.Media.Animation.BeginStoryboard> ，它将动画分散到它们动画处理的对象和属性，然后启动情节提要。 如果 <xref:System.Windows.Media.Animation.BeginStoryboard> 通过指定名称的属性来指定名称 <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> ，则会使其成为可控制的情节提要。 然后，你可以在情节提要启动后以交互方式控制情节提要。

结合使用以下情节提要操作和 <xref:System.Windows.EventTrigger> 对象控制情节提要。

- <xref:System.Windows.Media.Animation.PauseStoryboard>：暂停情节提要。

- <xref:System.Windows.Media.Animation.ResumeStoryboard>：恢复暂停的情节提要。

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>：更改情节提要的速度。

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>：使情节提要前进到其填充期的末尾（如果有一个）。

- <xref:System.Windows.Media.Animation.StopStoryboard>：停止情节提要。

- <xref:System.Windows.Media.Animation.RemoveStoryboard>：移除情节提要，释放资源。

## <a name="example"></a>示例

下面的示例使用可控制的情节提要操作以交互方式控制情节提要。

> [!NOTE]
> 若要查看使用代码控制情节提要的示例，请参阅 [使用其交互式方法控制情节提要](how-to-control-a-storyboard-after-it-starts.md)。

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

有关其他示例，请参阅 [动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [在情节提要启动后使用其交互式方法对其进行控制](how-to-control-a-storyboard-after-it-starts.md)
- [动画概述](animation-overview.md)
- [演示图板概述](storyboards-overview.md)
