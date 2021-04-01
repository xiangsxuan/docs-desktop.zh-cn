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
# <a name="how-to-receive-notification-when-a-clocks-state-changes"></a><span data-ttu-id="6e9b4-102">如何：在时钟状态发生变化时接收通知</span><span class="sxs-lookup"><span data-stu-id="6e9b4-102">How to: Receive Notification When a Clock's State Changes</span></span>
<span data-ttu-id="6e9b4-103"><xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated>当时钟变为无效时，将发生时钟事件 <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> ，例如当时钟开始或停止时。</span><span class="sxs-lookup"><span data-stu-id="6e9b4-103">A clock's <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> event occurs when its <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> becomes invalid, such as when the clock starts or stops.</span></span> <span data-ttu-id="6e9b4-104">您可以使用直接注册此事件 <xref:System.Windows.Media.Animation.Clock> ，也可以使用进行注册 <xref:System.Windows.Media.Animation.Timeline> 。</span><span class="sxs-lookup"><span data-stu-id="6e9b4-104">You can register for this event with directly using a <xref:System.Windows.Media.Animation.Clock>, or you can register using a <xref:System.Windows.Media.Animation.Timeline>.</span></span>  
  
 <span data-ttu-id="6e9b4-105">在下面的示例中，有一个 <xref:System.Windows.Media.Animation.Storyboard> 和两个 <xref:System.Windows.Media.Animation.DoubleAnimation> 对象用于对两个矩形的宽度进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="6e9b4-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> and two <xref:System.Windows.Media.Animation.DoubleAnimation> objects are used to animate the width of two rectangles.</span></span> <span data-ttu-id="6e9b4-106"><xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>事件用于侦听时钟状态更改。</span><span class="sxs-lookup"><span data-stu-id="6e9b4-106">The <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event is used to listen for clock state changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e9b4-107">示例</span><span class="sxs-lookup"><span data-stu-id="6e9b4-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 <span data-ttu-id="6e9b4-108">下图显示了动画在 (*Storyboard*) 的进度下进入的不同状态。</span><span class="sxs-lookup"><span data-stu-id="6e9b4-108">The following illustration shows the different states the animations enter as the parent timeline (*Storyboard*) progresses.</span></span>  
  
 <span data-ttu-id="6e9b4-109">![具有两个动画的演示图板的时钟状态](./media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span><span class="sxs-lookup"><span data-stu-id="6e9b4-109">![Clock states for a Storyboard with two animations](./media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span></span>  
  
 <span data-ttu-id="6e9b4-110">下表显示了触发 *Animation1* 事件的时间 <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> ：</span><span class="sxs-lookup"><span data-stu-id="6e9b4-110">The following table shows the times at which *Animation1*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
|<span data-ttu-id="6e9b4-111">时间 (秒) </span><span class="sxs-lookup"><span data-stu-id="6e9b4-111">Time (Seconds)</span></span>|<span data-ttu-id="6e9b4-112">1</span><span class="sxs-lookup"><span data-stu-id="6e9b4-112">1</span></span>|<span data-ttu-id="6e9b4-113">10</span><span class="sxs-lookup"><span data-stu-id="6e9b4-113">10</span></span>|<span data-ttu-id="6e9b4-114">19</span><span class="sxs-lookup"><span data-stu-id="6e9b4-114">19</span></span>|<span data-ttu-id="6e9b4-115">21</span><span class="sxs-lookup"><span data-stu-id="6e9b4-115">21</span></span>|<span data-ttu-id="6e9b4-116">30</span><span class="sxs-lookup"><span data-stu-id="6e9b4-116">30</span></span>|<span data-ttu-id="6e9b4-117">39</span><span class="sxs-lookup"><span data-stu-id="6e9b4-117">39</span></span>|  
|<span data-ttu-id="6e9b4-118">状态</span><span class="sxs-lookup"><span data-stu-id="6e9b4-118">State</span></span>|<span data-ttu-id="6e9b4-119">可用</span><span class="sxs-lookup"><span data-stu-id="6e9b4-119">Active</span></span>|<span data-ttu-id="6e9b4-120">活动</span><span class="sxs-lookup"><span data-stu-id="6e9b4-120">Active</span></span>|<span data-ttu-id="6e9b4-121">已停止</span><span class="sxs-lookup"><span data-stu-id="6e9b4-121">Stopped</span></span>|<span data-ttu-id="6e9b4-122">可用</span><span class="sxs-lookup"><span data-stu-id="6e9b4-122">Active</span></span>|<span data-ttu-id="6e9b4-123">活动</span><span class="sxs-lookup"><span data-stu-id="6e9b4-123">Active</span></span>|<span data-ttu-id="6e9b4-124">已停止</span><span class="sxs-lookup"><span data-stu-id="6e9b4-124">Stopped</span></span>|  
  
 <span data-ttu-id="6e9b4-125">下表显示了触发 *Animation2* 事件的时间 <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> ：</span><span class="sxs-lookup"><span data-stu-id="6e9b4-125">The following table shows the times at which *Animation2*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="6e9b4-126">时间 (秒) </span><span class="sxs-lookup"><span data-stu-id="6e9b4-126">Time (Seconds)</span></span>|<span data-ttu-id="6e9b4-127">1</span><span class="sxs-lookup"><span data-stu-id="6e9b4-127">1</span></span>|<span data-ttu-id="6e9b4-128">9</span><span class="sxs-lookup"><span data-stu-id="6e9b4-128">9</span></span>|<span data-ttu-id="6e9b4-129">11</span><span class="sxs-lookup"><span data-stu-id="6e9b4-129">11</span></span>|<span data-ttu-id="6e9b4-130">19</span><span class="sxs-lookup"><span data-stu-id="6e9b4-130">19</span></span>|<span data-ttu-id="6e9b4-131">21</span><span class="sxs-lookup"><span data-stu-id="6e9b4-131">21</span></span>|<span data-ttu-id="6e9b4-132">29</span><span class="sxs-lookup"><span data-stu-id="6e9b4-132">29</span></span>|<span data-ttu-id="6e9b4-133">31</span><span class="sxs-lookup"><span data-stu-id="6e9b4-133">31</span></span>|<span data-ttu-id="6e9b4-134">39</span><span class="sxs-lookup"><span data-stu-id="6e9b4-134">39</span></span>|  
|<span data-ttu-id="6e9b4-135">状态</span><span class="sxs-lookup"><span data-stu-id="6e9b4-135">State</span></span>|<span data-ttu-id="6e9b4-136">活动</span><span class="sxs-lookup"><span data-stu-id="6e9b4-136">Active</span></span>|<span data-ttu-id="6e9b4-137">好</span><span class="sxs-lookup"><span data-stu-id="6e9b4-137">Filling</span></span>|<span data-ttu-id="6e9b4-138">活动</span><span class="sxs-lookup"><span data-stu-id="6e9b4-138">Active</span></span>|<span data-ttu-id="6e9b4-139">已停止</span><span class="sxs-lookup"><span data-stu-id="6e9b4-139">Stopped</span></span>|<span data-ttu-id="6e9b4-140">活动</span><span class="sxs-lookup"><span data-stu-id="6e9b4-140">Active</span></span>|<span data-ttu-id="6e9b4-141">好</span><span class="sxs-lookup"><span data-stu-id="6e9b4-141">Filling</span></span>|<span data-ttu-id="6e9b4-142">活动</span><span class="sxs-lookup"><span data-stu-id="6e9b4-142">Active</span></span>|<span data-ttu-id="6e9b4-143">已停止</span><span class="sxs-lookup"><span data-stu-id="6e9b4-143">Stopped</span></span>|  
  
 <span data-ttu-id="6e9b4-144">请注意， *Animation1* 的  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> 事件将在10秒后激发，即使其状态仍然存在 <xref:System.Windows.Media.Animation.ClockState.Active> 。</span><span class="sxs-lookup"><span data-stu-id="6e9b4-144">Notice that *Animation1*'s  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires at 10 seconds, even though its state remains <xref:System.Windows.Media.Animation.ClockState.Active>.</span></span> <span data-ttu-id="6e9b4-145">这是因为它的状态在10秒内发生了更改，但它从 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Filling> <xref:System.Windows.Media.Animation.ClockState.Active> 相同的时钟周期更改为，然后再改回。</span><span class="sxs-lookup"><span data-stu-id="6e9b4-145">That's because its state changed at 10 seconds, but it changed from <xref:System.Windows.Media.Animation.ClockState.Active> to <xref:System.Windows.Media.Animation.ClockState.Filling> and then back to <xref:System.Windows.Media.Animation.ClockState.Active> in the same tick.</span></span>
