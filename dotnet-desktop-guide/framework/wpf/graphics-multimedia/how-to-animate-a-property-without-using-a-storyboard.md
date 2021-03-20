---
title: 如何：在不使用演示图板的情况下对属性进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: 8bbf2d68ffa5ad2467157893ab149e1a28a3af86
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668248"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a><span data-ttu-id="d305c-102">如何：在不使用演示图板的情况下对属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="d305c-102">How to: Animate a Property Without Using a Storyboard</span></span>
<span data-ttu-id="d305c-103">此示例演示在不使用的情况下将动画应用于属性的一种方法 <xref:System.Windows.Media.Animation.Storyboard> 。</span><span class="sxs-lookup"><span data-stu-id="d305c-103">This example shows one way to apply an animation to a property without using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d305c-104">此功能在 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 中不可用。</span><span class="sxs-lookup"><span data-stu-id="d305c-104">This functionality is not available in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="d305c-105">有关在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中对属性进行动画处理的信息，请参阅[使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="d305c-105">For information about animating a property in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="d305c-106">若要将本地动画应用到属性，请使用 <xref:System.Windows.UIElement.BeginAnimation%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="d305c-106">To apply a local animation to a property, use the <xref:System.Windows.UIElement.BeginAnimation%2A> method.</span></span> <span data-ttu-id="d305c-107">此方法采用两个参数：一个 <xref:System.Windows.DependencyProperty> 指定要进行动画处理的属性，以及一个要应用于该属性的动画。</span><span class="sxs-lookup"><span data-stu-id="d305c-107">This method takes two parameters: a <xref:System.Windows.DependencyProperty> that specifies the property to animate, and the animation to apply to that property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d305c-108">示例</span><span class="sxs-lookup"><span data-stu-id="d305c-108">Example</span></span>  
 <span data-ttu-id="d305c-109">下面的示例演示如何对的宽度和背景色进行动画处理 <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="d305c-109">The following example shows how to animate the width and background color of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 <span data-ttu-id="d305c-110">命名空间中存在各种动画类 <xref:System.Windows.Media.Animation> ，以对不同类型的属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="d305c-110">A variety of animation classes in the <xref:System.Windows.Media.Animation> namespace exist for animating different types of properties.</span></span> <span data-ttu-id="d305c-111">有关对属性进行动画处理的详细信息，请参阅[动画概述](animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d305c-111">For more information about animating properties, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="d305c-112">有关依赖属性（在这些示例中显示的属性类型）及其功能的详细信息，请参阅[依赖项属性概述](../advanced/dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d305c-112">For more information about dependency properties (the type of properties that are shown in these examples) and their features, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="d305c-113">还可以通过其他方式进行动画处理，而无需使用 <xref:System.Windows.Media.Animation.Storyboard> 对象; 有关详细信息，请参阅 [属性动画技术概述](property-animation-techniques-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d305c-113">There are other ways to animate without using <xref:System.Windows.Media.Animation.Storyboard> objects; for more information, see [Property Animation Techniques Overview](property-animation-techniques-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d305c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d305c-114">See also</span></span>

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="d305c-115">属性动画技术概述</span><span class="sxs-lookup"><span data-stu-id="d305c-115">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
- [<span data-ttu-id="d305c-116">动画概述</span><span class="sxs-lookup"><span data-stu-id="d305c-116">Animation Overview</span></span>](animation-overview.md)
