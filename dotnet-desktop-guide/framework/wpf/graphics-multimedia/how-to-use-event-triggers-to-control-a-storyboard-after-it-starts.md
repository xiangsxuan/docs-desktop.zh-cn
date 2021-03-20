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
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="5b352-102">如何：在演示图板启动之后使用事件触发器来控制演示图板</span><span class="sxs-lookup"><span data-stu-id="5b352-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>

<span data-ttu-id="5b352-103">此示例演示如何 <xref:System.Windows.Media.Animation.Storyboard> 在启动后对其进行控制。</span><span class="sxs-lookup"><span data-stu-id="5b352-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="5b352-104">若要 <xref:System.Windows.Media.Animation.Storyboard> 使用启动 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，请使用 <xref:System.Windows.Media.Animation.BeginStoryboard> ，它将动画分散到它们动画处理的对象和属性，然后启动情节提要。</span><span class="sxs-lookup"><span data-stu-id="5b352-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="5b352-105">如果 <xref:System.Windows.Media.Animation.BeginStoryboard> 通过指定名称的属性来指定名称 <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> ，则会使其成为可控制的情节提要。</span><span class="sxs-lookup"><span data-stu-id="5b352-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="5b352-106">然后，你可以在情节提要启动后以交互方式控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="5b352-106">You can then interactively control the storyboard after it starts.</span></span>

<span data-ttu-id="5b352-107">结合使用以下情节提要操作和 <xref:System.Windows.EventTrigger> 对象控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="5b352-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>

- <span data-ttu-id="5b352-108"><xref:System.Windows.Media.Animation.PauseStoryboard>：暂停情节提要。</span><span class="sxs-lookup"><span data-stu-id="5b352-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>

- <span data-ttu-id="5b352-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>：恢复暂停的情节提要。</span><span class="sxs-lookup"><span data-stu-id="5b352-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="5b352-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>：更改情节提要的速度。</span><span class="sxs-lookup"><span data-stu-id="5b352-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>

- <span data-ttu-id="5b352-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>：使情节提要前进到其填充期的末尾（如果有一个）。</span><span class="sxs-lookup"><span data-stu-id="5b352-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>

- <span data-ttu-id="5b352-112"><xref:System.Windows.Media.Animation.StopStoryboard>：停止情节提要。</span><span class="sxs-lookup"><span data-stu-id="5b352-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>

- <span data-ttu-id="5b352-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>：移除情节提要，释放资源。</span><span class="sxs-lookup"><span data-stu-id="5b352-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>

## <a name="example"></a><span data-ttu-id="5b352-114">示例</span><span class="sxs-lookup"><span data-stu-id="5b352-114">Example</span></span>

<span data-ttu-id="5b352-115">下面的示例使用可控制的情节提要操作以交互方式控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="5b352-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="5b352-116">若要查看使用代码控制情节提要的示例，请参阅 [使用其交互式方法控制情节提要](how-to-control-a-storyboard-after-it-starts.md)。</span><span class="sxs-lookup"><span data-stu-id="5b352-116">To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

<span data-ttu-id="5b352-117">有关其他示例，请参阅 [动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。</span><span class="sxs-lookup"><span data-stu-id="5b352-117">For additional examples, see the [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

## <a name="see-also"></a><span data-ttu-id="5b352-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b352-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="5b352-119">在情节提要启动后使用其交互式方法对其进行控制</span><span class="sxs-lookup"><span data-stu-id="5b352-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="5b352-120">动画概述</span><span class="sxs-lookup"><span data-stu-id="5b352-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="5b352-121">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="5b352-121">Storyboards Overview</span></span>](storyboards-overview.md)
