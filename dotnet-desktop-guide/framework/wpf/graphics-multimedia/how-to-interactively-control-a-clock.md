---
title: 如何：以交互方式控制时钟
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973506"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="34ec6-102">如何：以交互方式控制时钟</span><span class="sxs-lookup"><span data-stu-id="34ec6-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="34ec6-103"><xref:System.Windows.Media.Animation.Clock>对象的 <xref:System.Windows.Media.Animation.ClockController> 属性使你能够以交互方式启动、暂停、恢复、查找、将时钟推进到其填充期并停止时钟。</span><span class="sxs-lookup"><span data-stu-id="34ec6-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="34ec6-104">只能以交互方式控制计时树的根时钟。</span><span class="sxs-lookup"><span data-stu-id="34ec6-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34ec6-105">还可以通过其他方式以交互方式控制不需要直接使用时钟的动画：你也可以使用情节提要。</span><span class="sxs-lookup"><span data-stu-id="34ec6-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="34ec6-106">标记和代码都支持情节提要。</span><span class="sxs-lookup"><span data-stu-id="34ec6-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="34ec6-107">有关示例，请参阅使用情节提要或[动画概述](animation-overview.md)对[属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="34ec6-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="34ec6-108">在下面的示例中，使用了多个按钮以交互方式控制动画时钟。</span><span class="sxs-lookup"><span data-stu-id="34ec6-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34ec6-109">示例</span><span class="sxs-lookup"><span data-stu-id="34ec6-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="34ec6-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="34ec6-110">See also</span></span>

- [<span data-ttu-id="34ec6-111">使用情节提要对属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="34ec6-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="34ec6-112">动画概述</span><span class="sxs-lookup"><span data-stu-id="34ec6-112">Animation Overview</span></span>](animation-overview.md)
