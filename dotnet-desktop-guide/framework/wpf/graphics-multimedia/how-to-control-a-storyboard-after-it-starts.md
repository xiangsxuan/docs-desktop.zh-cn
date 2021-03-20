---
title: 如何：在演示图板启动后对其进行控制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 2687821966cd23048a070b1390a615691ca0be60
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668222"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>如何：在演示图板启动后对其进行控制

此示例演示如何使用代码 <xref:System.Windows.Media.Animation.Storyboard> 在启动后对其进行控制。 若要在中控制情节提要 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，请使用 <xref:System.Windows.Trigger> 和 <xref:System.Windows.TriggerAction> 对象; 有关示例，请参阅在 [情节提要启动之后使用事件触发器控制情节提要](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)。

若要启动情节提要，请使用其 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法，该方法将演示图板的动画分发到它们动画处理的属性，并启动情节提要。

若要使情节提要可控制，请使用 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法并将 **true** 指定为第二个参数。 然后，可以使用情节提要的交互式方法来暂停、恢复、查找、停止、加速或减速情节提要，或将其前进到其填充期。 下面列出了情节提要的交互式方法：

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>：暂停情节提要。

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>：恢复暂停的情节提要。

- <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>：设置情节提要的交互速度。

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>：查找指定位置的情节提要。

- <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>：查找情节提要到指定位置。 与 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 方法不同，此操作将在下一次计时周期前处理。

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>：将情节提要前进到其填充期（如果有）。

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>：停止情节提要。

在下面的示例中，使用了多个情节提要方法来以交互方式控制情节提要。

> [!NOTE]
> 若要查看使用触发器控制情节提要的示例 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，请参阅 [在情节提要启动后使用事件触发器控制情节提要](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)。

## <a name="example"></a>示例

[!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
[!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]

## <a name="see-also"></a>请参阅

- [在情节提要启动之后使用事件触发器来控制情节提要](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
