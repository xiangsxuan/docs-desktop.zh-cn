---
title: 如何：使用 CompositionTarget 以每帧间隔呈现
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CompositionTarget objects [WPF], rendering per frame
- rendering per frame using CompositionTarget objects [WPF]
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
ms.openlocfilehash: b4e245977ed60d0d31c90d861f8614a227b26098
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666896"
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>如何：使用 CompositionTarget 以每帧间隔呈现

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 动画引擎提供了许多用于创建基于帧的动画的功能。 但是，在某些应用程序方案中，需要基于每个帧以更细的粒度控制呈现。 <xref:System.Windows.Media.CompositionTarget>对象提供基于每帧回调创建自定义动画的功能。  
  
 <xref:System.Windows.Media.CompositionTarget> 是一个静态类，表示在其上绘制应用程序的显示图面。 <xref:System.Windows.Media.CompositionTarget.Rendering>每次绘制应用程序场景时都会引发该事件。 呈现帧速率是指每秒绘制场景的次数。  
  
> [!NOTE]
> 有关使用的完整代码示例 <xref:System.Windows.Media.CompositionTarget> ，请参阅 [使用 CompositionTarget 示例](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/CompositionTarget)。  
  
## <a name="example"></a>示例  

 <xref:System.Windows.Media.CompositionTarget.Rendering>呈现过程中将激发该事件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 下面的示例演示如何将委托注册 <xref:System.EventHandler> 到上的静态 <xref:System.Windows.Media.CompositionTarget.Rendering> 方法 <xref:System.Windows.Media.CompositionTarget> 。  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 可以使用呈现事件处理程序方法来创建自定义绘图内容。 每帧调用一次此事件处理程序方法。 每次 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 将可视化树中的持久呈现数据封送到组合场景图中时，都会调用事件处理程序方法。 另外，如果对可视化树的更改强制更新组合场景图，也会调用事件处理程序方法。 请注意，计算布局后会调用事件处理程序方法。 但是，可以修改事件处理程序方法中的布局，这意味着在呈现之前将再计算一次布局。  
  
 下面的示例演示如何在 <xref:System.Windows.Media.CompositionTarget> 事件处理程序方法中提供自定义绘图。 在这种情况下， <xref:System.Windows.Controls.Canvas> 使用基于鼠标坐标位置的颜色值绘制的背景色。 如果将鼠标移动到内 <xref:System.Windows.Controls.Canvas> ，则其背景色会更改。 另外，将基于当前的运行时间和所呈现的帧总数来计算平均帧速率。  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 可能会发现自定义绘图在不同计算机上以不同的速度运行。 这是由于自定义绘图与帧速率有关。 根据你所运行的系统和该系统的工作负载，该 <xref:System.Windows.Media.CompositionTarget.Rendering> 事件的每秒调用次数可能不同。 有关为运行 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序的设备确定图形硬件功能和性能的信息，请参阅[图形呈现层](../advanced/graphics-rendering-tiers.md)。  
  
 事件激发时添加或移除呈现 <xref:System.EventHandler> 委托将延迟，直到事件完成激发。 这与 <xref:System.MulticastDelegate> 在公共语言运行时中处理基于的事件在公共语言运行时 (CLR) 一致。 另请注意，无法保证按照任何特定顺序来调用呈现事件。 如果有多个 <xref:System.EventHandler> 依赖于特定顺序的委托，则应注册单个 <xref:System.Windows.Media.CompositionTarget.Rendering> 事件，并自行按正确的顺序对委托进行多路复用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.CompositionTarget>
- [WPF 图形呈现疑难解答](wpf-graphics-rendering-overview.md)
