---
title: 如何：在属性值更改时触发动画
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973508"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="62414-102">如何：在属性值更改时触发动画</span><span class="sxs-lookup"><span data-stu-id="62414-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="62414-103">此示例演示如何使用在 <xref:System.Windows.Trigger> <xref:System.Windows.Media.Animation.Storyboard> 属性值更改时启动。</span><span class="sxs-lookup"><span data-stu-id="62414-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="62414-104">您可以 <xref:System.Windows.Trigger> 在 <xref:System.Windows.Style> 、或中使用 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.DataTemplate> 。</span><span class="sxs-lookup"><span data-stu-id="62414-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62414-105">示例</span><span class="sxs-lookup"><span data-stu-id="62414-105">Example</span></span>  
 <span data-ttu-id="62414-106">下面的示例使用在 <xref:System.Windows.Trigger> <xref:System.Windows.UIElement.Opacity%2A> <xref:System.Windows.Controls.Button> 其属性变为时对 a 的进行动画处理 <xref:System.Windows.UIElement.IsMouseOver%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="62414-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="62414-107">属性对象应用的动画的 <xref:System.Windows.Trigger> 行为方式比 <xref:System.Windows.EventTrigger> 使用方法启动动画或动画更复杂 <xref:System.Windows.Media.Animation.Storyboard> 。</span><span class="sxs-lookup"><span data-stu-id="62414-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="62414-108">它们使用其他对象定义的动画 "切换" <xref:System.Windows.Trigger> ，但使用 <xref:System.Windows.EventTrigger> 和方法触发的动画进行组合。</span><span class="sxs-lookup"><span data-stu-id="62414-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62414-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="62414-109">See also</span></span>

- <xref:System.Windows.Trigger>
- [<span data-ttu-id="62414-110">属性动画技术概述</span><span class="sxs-lookup"><span data-stu-id="62414-110">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
- [<span data-ttu-id="62414-111">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="62414-111">Storyboards Overview</span></span>](storyboards-overview.md)
