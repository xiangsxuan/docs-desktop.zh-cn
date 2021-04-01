---
title: 创建墨迹输入控件
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: d9b18054154e6871925f423f539d44f12adca1f5
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971946"
---
# <a name="creating-an-ink-input-control"></a>创建墨迹输入控件

可以创建动态和静态呈现墨迹的自定义控件。 也就是说，当用户绘制笔划时呈现墨迹，使墨迹显示为触笔的 "流"，并在将墨迹添加到控件后通过 tablet 笔从剪贴板中粘贴或从文件加载墨迹来显示墨迹。 若要动态呈现墨迹，控件必须使用 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 。 若要以静态方式呈现墨迹，你必须重写触笔事件方法 (<xref:System.Windows.UIElement.OnStylusDown%2A> 、 <xref:System.Windows.UIElement.OnStylusMove%2A> 和 <xref:System.Windows.UIElement.OnStylusUp%2A>) 来收集 <xref:System.Windows.Input.StylusPoint> 数据、创建笔画，并将其添加到 <xref:System.Windows.Controls.InkPresenter> (以便在控件) 上呈现墨迹。  
  
 本主题包含以下小节：  
  
- [如何：收集触笔接触点数据和创建墨迹笔划](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [如何：使控件接受鼠标输入](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [综合运用](#PuttingItTogether)  
  
- [使用其他插件和 DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [结束语](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>

## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>如何：收集触笔接触点数据和创建墨迹笔划  

 若要创建用于收集和管理墨迹笔划的控件，请执行以下操作：  
  
1. 从派生的类 <xref:System.Windows.Controls.Control> 或从派生的类之一（ <xref:System.Windows.Controls.Control> 如） <xref:System.Windows.Controls.Label> 。  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. 将添加 <xref:System.Windows.Controls.InkPresenter> 到类，并将 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性设置为新的 <xref:System.Windows.Controls.InkPresenter> 。  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Controls.InkPresenter> 通过调用方法，将的添加到中 <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> ，并将添加 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 到集合中 <xref:System.Windows.UIElement.StylusPlugIns%2A> 。 这样，便可以在 <xref:System.Windows.Controls.InkPresenter> 控件收集触笔点数据时显示墨迹。  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. 重写 <xref:System.Windows.UIElement.OnStylusDown%2A> 方法。  在此方法中，通过调用来捕获触笔 <xref:System.Windows.Input.Stylus.Capture%2A> 。 捕获触笔后， <xref:System.Windows.UIElement.StylusMove> <xref:System.Windows.UIElement.StylusUp> 即使触笔离开控件边界，控件也将继续接收和事件。 这并不是绝对必需的，但几乎总是希望获得良好的用户体验。 创建新的 <xref:System.Windows.Input.StylusPointCollection> 以收集 <xref:System.Windows.Input.StylusPoint> 数据。 最后，将初始数据集添加 <xref:System.Windows.Input.StylusPoint> 到中 <xref:System.Windows.Input.StylusPointCollection> 。  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. 重写 <xref:System.Windows.UIElement.OnStylusMove%2A> 方法，并将 <xref:System.Windows.Input.StylusPoint> 数据添加到 <xref:System.Windows.Input.StylusPointCollection> 之前创建的对象。  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. 重写 <xref:System.Windows.UIElement.OnStylusUp%2A> 方法，并使用数据创建新的 <xref:System.Windows.Ink.Stroke> <xref:System.Windows.Input.StylusPointCollection> 。 将创建的新添加 <xref:System.Windows.Ink.Stroke> 到 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 的集合 <xref:System.Windows.Controls.InkPresenter> ，并释放触笔捕获。  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>

## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>如何：使控件接受鼠标输入  

 如果将前面的控件添加到应用程序，运行它，并使用鼠标作为输入设备，你会注意到这些笔划不会保留。 若要在鼠标作为输入设备使用时保持笔画，请执行以下操作：  
  
1. 重写 <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> 并创建一个新的，并在 <xref:System.Windows.Input.StylusPointCollection> 事件发生时获取鼠标的位置，并 <xref:System.Windows.Input.StylusPoint> 使用点数据创建并将添加 <xref:System.Windows.Input.StylusPoint> 到 <xref:System.Windows.Input.StylusPointCollection> 。  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. 重写 <xref:System.Windows.UIElement.OnMouseMove%2A> 方法。 在事件发生时获取鼠标位置，并 <xref:System.Windows.Input.StylusPoint> 使用点数据创建。  将添加 <xref:System.Windows.Input.StylusPoint> 到 <xref:System.Windows.Input.StylusPointCollection> 之前创建的对象。  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. 重写 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 方法。  <xref:System.Windows.Ink.Stroke>使用数据创建新的 <xref:System.Windows.Input.StylusPointCollection> ，并将创建的新添加 <xref:System.Windows.Ink.Stroke> 到 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 的集合中 <xref:System.Windows.Controls.InkPresenter> 。  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>

## <a name="putting-it-together"></a>综合运用  

 下面的示例是在用户使用鼠标或笔时收集墨迹的自定义控件。  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>

## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>使用其他插件和 DynamicRenderers  

 与 InkCanvas 一样，自定义控件可以具有自定义 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 对象和其他 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 对象。 将它们添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 集合中。 中的对象的顺序 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 会影响呈现墨迹时的外观。 假设你有一个 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 名为的 `dynamicRenderer` 和一个名为的自定义 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> `translatePlugin` ，它将从 tablet 笔偏移墨迹。 如果 `translatePlugin` 是中的第一个 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> ，并且 `dynamicRenderer` 为第二个，则当用户移动笔时，"流" 的墨迹将偏移。 如果 `dynamicRenderer` 是第一个，并且 `translatePlugin` 为第二个，则在用户提起笔之前，墨迹不会偏移。  
  
<a name="AdvancedInkHandling_Conclusion"></a>

## <a name="conclusion"></a>结束语  

 可以通过重写触笔事件方法来创建一个用于收集和呈现墨迹的控件。 通过创建自己的控件，派生你自己 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 的类并将它们插入到中 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> ，你可以使用数字墨迹实现几乎任何行为想象。 你可以在生成数据时对其进行访问 <xref:System.Windows.Input.StylusPoint> ，使你可以自定义 <xref:System.Windows.Input.Stylus> 输入，并根据应用程序将其呈现在屏幕上。 由于你对数据具有此类低级别访问权限 <xref:System.Windows.Input.StylusPoint> ，因此你可以实现墨迹收集，并为应用程序提供最佳性能。  
  
## <a name="see-also"></a>请参阅

- [高级墨迹处理](advanced-ink-handling.md)
- [访问和操作笔输入](/previous-versions/ms818317(v=msdn.10))
