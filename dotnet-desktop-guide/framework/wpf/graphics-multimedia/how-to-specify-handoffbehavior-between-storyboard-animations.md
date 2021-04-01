---
title: 如何：指定演示图板动画之间的 HandoffBehavior
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: d7129d6a48bdf31dc4953bb450267ad3b38fdd17
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971006"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="e416e-102">如何：指定演示图板动画之间的 HandoffBehavior</span><span class="sxs-lookup"><span data-stu-id="e416e-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="e416e-103">此示例演示如何指定演示图板动画之间的切换行为。</span><span class="sxs-lookup"><span data-stu-id="e416e-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="e416e-104">的 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 属性 <xref:System.Windows.Media.Animation.BeginStoryboard> 指定新动画如何与已应用于属性的任何现有动画进行交互。</span><span class="sxs-lookup"><span data-stu-id="e416e-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e416e-105">示例</span><span class="sxs-lookup"><span data-stu-id="e416e-105">Example</span></span>  
 <span data-ttu-id="e416e-106">下面的示例创建两个按钮，这些按钮在鼠标光标移到它们上方时放大，并在光标移开时变得更小。</span><span class="sxs-lookup"><span data-stu-id="e416e-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="e416e-107">如果将鼠标悬停在某个按钮上，然后快速删除光标，则第一个动画在第一个动画完成之前将会应用。</span><span class="sxs-lookup"><span data-stu-id="e416e-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="e416e-108">当两个动画重叠时，这种情况下，您可以看到和的值之间的差异 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> 。</span><span class="sxs-lookup"><span data-stu-id="e416e-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="e416e-109">如果值为， <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 则将重叠动画组合起来会使动画间的过渡更平稳，而值 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> 会导致新动画立即替换先前的重叠动画。</span><span class="sxs-lookup"><span data-stu-id="e416e-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e416e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e416e-110">See also</span></span>

- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [<span data-ttu-id="e416e-111">动画概述</span><span class="sxs-lookup"><span data-stu-id="e416e-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="e416e-112">动画和计时帮助主题</span><span class="sxs-lookup"><span data-stu-id="e416e-112">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
