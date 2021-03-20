---
title: 属性动画技术概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
ms.openlocfilehash: 9e29f4ffa96b54aba1b5f3df828bfc16099882fa
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668326"
---
# <a name="property-animation-techniques-overview"></a>属性动画技术概述

本主题介绍了处理动画属性的不同方法：情节提要、本地动画、时钟和基于帧的动画。  
  
<a name="prerequisites"></a>

## <a name="prerequisites"></a>必备条件  

 若要了解本主题，应熟悉[动画概述](animation-overview.md)中描述的基本动画功能。  
  
<a name="summary"></a>

## <a name="different-ways-to-animate"></a>动画处理的不同方法  

 由于动画处理属性存在多种不同的方案，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供几种动画处理属性的方法。  
  
 对于每种方法，下表指明了每种方法是否可以基于实例在样式、控件模板或数据模板中使用；是否可以在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中使用；以及该方法是否能够以交互方式控制动画。  “基于实例”是指直接将动画或情节提要应用于对象实例（而不是在样式、控件模板或数据模板中应用）的技术。  
  
|动画技术|方案|支持 XAML|可以交互方式控制|  
|-------------------------|---------------|-------------------|--------------------------------|  
|情节提要动画|每个实例、 <xref:System.Windows.Style> 、 <xref:System.Windows.Controls.ControlTemplate> 、 <xref:System.Windows.DataTemplate>|是|是|  
|本地动画|基于实例|否|否|  
|时钟动画|基于实例|否|是|  
|基于帧的动画|基于实例|否|不适用|  
  
<a name="storyboard_animations"></a>

## <a name="storyboard-animations"></a>情节提要动画  

 <xref:System.Windows.Media.Animation.Storyboard>如果要在中定义和应用动画 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，请使用，在动画开始后以交互方式控制动画，创建复杂的动画树，或在中进行动画处理 <xref:System.Windows.Style> <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.DataTemplate> 。 对于要进行动画处理的对象 <xref:System.Windows.Media.Animation.Storyboard> ，该对象必须为 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> ，或者必须用于设置 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> 。 有关详细信息，请参阅[情节提要概述](storyboards-overview.md)。  
  
 <xref:System.Windows.Media.Animation.Storyboard>是一种特殊类型的容器 <xref:System.Windows.Media.Animation.Timeline> ，它提供其所包含动画的目标信息。 若要使用进行动画处理 <xref:System.Windows.Media.Animation.Storyboard> ，请完成以下三个步骤。  
  
1. 声明一个 <xref:System.Windows.Media.Animation.Storyboard> 和一个或多个动画。  
  
2. 使用 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 和 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> 附加属性来指定每个动画的目标对象和属性。  
  
3. 仅) 为或定义 (代码 <xref:System.Windows.NameScope> <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> 。 注册要与此或进行动画处理的对象的名称 <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> 。  
  
4. 开始 <xref:System.Windows.Media.Animation.Storyboard> 。  
  
 开始将 <xref:System.Windows.Media.Animation.Storyboard> 动画应用于它们会进行动画处理的属性，然后启动它们。 可以通过两种方式开始 <xref:System.Windows.Media.Animation.Storyboard> ：使用 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 类提供的方法 <xref:System.Windows.Media.Animation.Storyboard> ，也可以使用 <xref:System.Windows.Media.Animation.BeginStoryboard> 操作。 在中进行动画处理的唯一方法 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 是使用 <xref:System.Windows.Media.Animation.BeginStoryboard> 操作。 <xref:System.Windows.Media.Animation.BeginStoryboard>操作可以在 <xref:System.Windows.EventTrigger> 、属性或中使用 <xref:System.Windows.Trigger> <xref:System.Windows.DataTrigger> 。  
  
 下表显示支持每个开始技术的不同位置 <xref:System.Windows.Media.Animation.Storyboard> ：每个实例、样式、控件模板和数据模板。  
  
|情节提要开始时使用…|基于实例|Style|控件模板|数据模板|示例|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和 <xref:System.Windows.EventTrigger>|是|是|是|是|[使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和属性 <xref:System.Windows.Trigger>|否|是|是|是|[在属性值更改时触发动画](how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和 <xref:System.Windows.DataTrigger>|否|是|是|是|[如何：在数据更改时触发动画](/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法|是|否|否|否|[使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 有关对象的详细信息 <xref:System.Windows.Media.Animation.Storyboard> ，请参阅 [情节提要概述](storyboards-overview.md)。  
  
## <a name="local-animations"></a>本地动画  

 本地动画提供了一种简便的方式来对任何对象的依赖属性进行动画处理 <xref:System.Windows.Media.Animation.Animatable> 。 如果想要将单一动画应用到属性中，可以使用本地动画，并且动画启动后不需要以交互方式控制动画。 与 <xref:System.Windows.Media.Animation.Storyboard> 动画不同，本地动画可以对与或无关的对象进行动画处理 <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> 。 您也不必为 <xref:System.Windows.NameScope> 这种类型的动画定义。  
  
 本地动画可能仅在代码中使用，无法在样式、控件模板或数据模板中定义。 本地动画启动后，无法以交互方式控制。  
  
 若要使用本地动画进行动画处理，应完成以下步骤。  
  
1. 创建 <xref:System.Windows.Media.Animation.AnimationTimeline> 对象。  
  
2. 使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 要进行动画处理的对象的方法，将应用 <xref:System.Windows.Media.Animation.AnimationTimeline> 到您指定的属性。  
  
 下面的示例演示如何对的宽度和背景色进行动画处理 <xref:System.Windows.Controls.Button> 。  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>时钟动画  

 <xref:System.Windows.Media.MediaPlayer.Clock%2A>当你希望在不使用的情况下进行动画处理 <xref:System.Windows.Media.Animation.Storyboard> 并且你想要在启动时创建复杂的计时树或交互控制动画时，请使用对象。 您可以使用时钟对象对任何对象的依赖属性进行动画处理 <xref:System.Windows.Media.Animation.Animatable> 。  
  
 不能使用 <xref:System.Windows.Media.Animation.Clock> 对象直接在样式、控件模板或数据模板中进行动画处理。  (动画和计时系统实际上确实使用 <xref:System.Windows.Media.Animation.Clock> 对象在样式、控件模板和数据模板中进行动画处理，但它必须从创建这些 <xref:System.Windows.Media.Animation.Clock> 对象 <xref:System.Windows.Media.Animation.Storyboard> 。 有关对象和对象之间的关系的详细信息 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Clock> ，请参阅 [动画和计时系统概述](animation-and-timing-system-overview.md)。 )   
  
 若要将单个应用于 <xref:System.Windows.Media.Animation.Clock> 属性，请完成以下步骤。  
  
1. 创建 <xref:System.Windows.Media.Animation.AnimationTimeline> 对象。  
  
2. 使用的 <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> 方法 <xref:System.Windows.Media.Animation.AnimationTimeline> 来创建 <xref:System.Windows.Media.Animation.AnimationClock> 。  
  
3. 使用 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> 要进行动画处理的对象的方法，将应用于 <xref:System.Windows.Media.Animation.AnimationClock> 指定的属性。  
  
 下面的示例演示如何创建 <xref:System.Windows.Media.Animation.AnimationClock> 并将其应用到两个相似的属性。  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 如果想要创建一个计时树并用其处理动画属性，应完成以下几个步骤。  
  
1. 使用 <xref:System.Windows.Media.Animation.ParallelTimeline> 和 <xref:System.Windows.Media.Animation.AnimationTimeline> 对象创建计时树。  
  
2. 使用 <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> 根的 <xref:System.Windows.Media.Animation.ParallelTimeline> 来创建 <xref:System.Windows.Media.Animation.ClockGroup> 。  
  
3. 循环访问的 <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> <xref:System.Windows.Media.Animation.ClockGroup> ，并应用其子 <xref:System.Windows.Media.Animation.Clock> 对象。 对于每个 <xref:System.Windows.Media.Animation.AnimationClock> 子级，使用 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> 要进行动画处理的对象的方法，将应用于 <xref:System.Windows.Media.Animation.AnimationClock> 指定的属性  
  
 有关时钟对象的详细信息，请参阅[动画和计时系统概述](animation-and-timing-system-overview.md)。  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>基于帧的动画：绕过动画和计时系统  

 在需要完全绕过 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 动画系统时使用此方法。 此方法的一个方案是物理动画，其中的每个动画步骤都要求基于最后一组对象交互来重新计算。  
  
 基于帧的动画无法在样式、控件模板或数据模板内定义。  
  
 若要逐帧进行动画处理，可以注册对象的 <xref:System.Windows.Media.CompositionTarget.Rendering> 事件，该对象包含要进行动画处理的对象。 每帧调用一次此事件处理程序方法。 每次 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 将可视化树中的持久呈现数据封送到复合树时，都将调用事件处理程序方法。  
  
 在事件处理程序中，执行动画效果所需的任何计算，并设置想要使用这些值进行动画处理的对象的属性。  
  
 若要获取当前帧的显示时间， <xref:System.EventArgs> 可以将与此事件关联的转换为 <xref:System.Windows.Media.RenderingEventArgs> ，这提供了一个 <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> 可用于获取当前帧呈现时间的属性。  
  
 有关详细信息，请参阅 <xref:System.Windows.Media.CompositionTarget.Rendering> 页。  
  
## <a name="see-also"></a>请参阅

- [动画概述](animation-overview.md)
- [演示图板概述](storyboards-overview.md)
- [动画和计时系统概述](animation-and-timing-system-overview.md)
- [依赖项属性概述](../advanced/dependency-properties-overview.md)
