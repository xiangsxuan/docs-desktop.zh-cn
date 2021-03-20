---
title: 使用 DrawingVisual 对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
ms.openlocfilehash: d12098c4a6c9cd87a2d3c1bf7b2c81349a76bf6c
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667234"
---
# <a name="using-drawingvisual-objects"></a>使用 DrawingVisual 对象
本主题概述了如何使用 <xref:System.Windows.Media.DrawingVisual> 可视层中的对象 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
<a name="drawingvisual_object"></a>
## <a name="drawingvisual-object"></a>DrawingVisual 对象  
 <xref:System.Windows.Media.DrawingVisual>是一个轻量绘图类，用于呈现形状、图像或文本。 此类之所以为轻量类是因为它不提供布局或事件处理，从而性能得以提升。 因此，绘图非常适用于背景和剪贴画。  
  
<a name="drawingvisual_host_container"></a>
## <a name="drawingvisual-host-container"></a>DrawingVisual 宿主容器  
 为了使用 <xref:System.Windows.Media.DrawingVisual> 对象，需要为对象创建主机容器。 宿主容器对象必须派生自 <xref:System.Windows.FrameworkElement> 类，该类提供类缺少的布局和事件处理支持 <xref:System.Windows.Media.DrawingVisual> 。 宿主容器对象不显示任何可视属性，因为它的主要用途是包含子对象。 但是， <xref:System.Windows.UIElement.Visibility%2A> 必须将宿主容器的属性设置为 <xref:System.Windows.Visibility.Visible> ; 否则，其子元素将不可见。  
  
 为视觉对象创建宿主容器对象时，需要将视觉对象引用存储在中 <xref:System.Windows.Media.VisualCollection> 。 使用 <xref:System.Windows.Media.VisualCollection.Add%2A> 方法可将视觉对象添加到宿主容器。 在下面的示例中，将创建一个主机容器对象，并向其添加三个视觉对象 <xref:System.Windows.Media.VisualCollection> 。  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
> 有关从中提取上述代码示例的完整代码示例，请参阅[使用 DrawingVisual 的命中测试示例](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)。  
  
<a name="creating_drawingvisual_objects"></a>
## <a name="creating-drawingvisual-objects"></a>创建 DrawingVisual 对象  
 当你创建 <xref:System.Windows.Media.DrawingVisual> 对象时，它没有绘制内容。 可以通过检索对象并在其中进行绘制来添加文本、图形或图像内容 <xref:System.Windows.Media.DrawingContext> 。 <xref:System.Windows.Media.DrawingContext>通过调用对象的方法来返回 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> <xref:System.Windows.Media.DrawingVisual> 。  
  
 若要在中绘制矩形 <xref:System.Windows.Media.DrawingContext> ，请使用 <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> 对象的方法 <xref:System.Windows.Media.DrawingContext> 。 对于绘制其他类型的内容，存在类似的方法。 完成将内容绘制到后 <xref:System.Windows.Media.DrawingContext> ，调用 <xref:System.Windows.Media.DrawingContext.Close%2A> 方法关闭 <xref:System.Windows.Media.DrawingContext> 并保存内容。  
  
 在下面的示例中， <xref:System.Windows.Media.DrawingVisual> 将创建一个对象，并在其中绘制一个矩形 <xref:System.Windows.Media.DrawingContext> 。  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>
## <a name="creating-overrides-for-frameworkelement-members"></a>为 FrameworkElement 成员创建重写  
 宿主容器对象负责管理其视觉对象的集合。 这需要宿主容器实现派生类的成员重写 <xref:System.Windows.FrameworkElement> 。  
  
 下表介绍了必须重写的两个成员：  
  
- <xref:System.Windows.FrameworkElement.GetVisualChild%2A>：从子元素集合中返回指定索引处的子级。  
  
- <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>：获取此元素内的可视化子元素的数目。  
  
 在下面的示例中，实现了两个成员的重写 <xref:System.Windows.FrameworkElement> 。  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>
## <a name="providing-hit-testing-support"></a>提供命中测试支持  
 宿主容器对象可以提供事件处理，即使它未显示任何可见属性，但其 <xref:System.Windows.UIElement.Visibility%2A> 属性必须设置为 <xref:System.Windows.Visibility.Visible> 。 这样便可以为宿主容器创建事件处理例程，此例程可以捕获鼠标事件，如松开鼠标左键。 然后，事件处理例程可以通过调用方法来实现命中测试 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 。 此方法的 <xref:System.Windows.Media.HitTestResultCallback> 参数引用用户定义的过程，您可以使用该过程来确定命中测试的结果操作。  
  
 在下面的示例中，为宿主容器对象及其子级实现命中测试支持。  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [WPF 图形呈现疑难解答](wpf-graphics-rendering-overview.md)
- [可视化层中的命中测试](hit-testing-in-the-visual-layer.md)
