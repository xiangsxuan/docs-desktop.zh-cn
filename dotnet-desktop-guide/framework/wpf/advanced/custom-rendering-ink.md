---
title: 自定义呈现墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
ms.openlocfilehash: 406a01d03e991857faaa5f071d414bc4f594cc4a
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666103"
---
# <a name="custom-rendering-ink"></a>自定义呈现墨迹
<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>使用笔划的属性可以指定笔划的外观，例如，其大小、颜色和形状，但有时您可能希望自定义除 "允许" 之外的外观 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 。 建议通过使用喷笔、油画和多种其他效果呈现外观，从而自定义墨迹的外观。 使用 Windows Presentation Foundation (WPF) ，可以通过实现自定义和对象自定义呈现墨迹 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Ink.Stroke> 。  
  
 本主题包含以下小节：  
  
- [体系结构](#Architecture)  
  
- [实现动态呈现器](#ImplementingADynamicRenderer)  
  
- [实现自定义笔划](#ImplementingCustomStrokes)  
  
- [实现自定义 InkCanvas](#ImplementingACustomInkCanvas)  
  
- [结束语](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>体系结构  
 墨迹呈现会出现两次：用户将墨迹写入墨迹书写表面时，以及将笔划添加到启用了墨迹的表面之后。 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>当用户将触笔移到数字化仪上时，将呈现墨迹，并在将 <xref:System.Windows.Ink.Stroke> 其添加到元素中后呈现自己。  
  
 动态呈现墨迹时需要实现三个类。  
  
1. **DynamicRenderer**：实现一个派生自的类 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 。 此类是一个专用 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 的，它在绘制时呈现笔画。 在 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 单独的线程上进行呈现，因此即使在应用程序用户界面 (UI) 线程被阻止时，墨迹图面也会显示为收集墨迹。 有关线程模型的详细信息，请参阅[墨迹线程模型](the-ink-threading-model.md)。 若要自定义动态呈现笔画，请重写 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> 方法。  
  
2. **Stroke**：实现一个派生自的类 <xref:System.Windows.Ink.Stroke> 。 此类负责在将 <xref:System.Windows.Input.StylusPoint> 数据转换为对象之后静态呈现该数据 <xref:System.Windows.Ink.Stroke> 。 重写 <xref:System.Windows.Ink.Stroke.DrawCore%2A> 方法以确保笔划的静态呈现与动态呈现一致。  
  
3. **InkCanvas：** 实现派生自的类 <xref:System.Windows.Controls.InkCanvas> 。 将自定义的分配 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 给 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 属性。 重写 <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 方法，并向属性添加自定义笔画 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 。 这样可以确保墨迹外观一致。  
  
<a name="ImplementingADynamicRenderer"></a>
## <a name="implementing-a-dynamic-renderer"></a>实现动态呈现器  
 尽管 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 类是的标准部分，但 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 若要执行更专用的呈现，则必须创建从派生的自定义动态呈现器 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 并重写 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> 方法。  
  
 下面的示例演示了一个 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 使用线性渐变画笔效果绘制墨迹的自定义。  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>
## <a name="implementing-custom-strokes"></a>实现自定义笔划  
 实现从 <xref:System.Windows.Ink.Stroke> 派生的类。 此类负责 <xref:System.Windows.Input.StylusPoint> 在将数据转换为对象之后呈现数据 <xref:System.Windows.Ink.Stroke> 。 重写 <xref:System.Windows.Ink.Stroke.DrawCore%2A> 类以执行实际绘图。  
  
 Stroke 类还可以使用方法存储自定义数据 <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> 。 此数据持续存在时会与笔划数据一起存储。  
  
 <xref:System.Windows.Ink.Stroke>类还可以执行命中测试。 还可以通过 <xref:System.Windows.Ink.Stroke.HitTest%2A> 在当前类中重写方法来实现自己的命中测试算法。  
  
 下面的 c # 代码演示了一个以 <xref:System.Windows.Ink.Stroke> <xref:System.Windows.Input.StylusPoint> 三维笔画形式呈现数据的自定义类。  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>
## <a name="implementing-a-custom-inkcanvas"></a>实现自定义 InkCanvas  
 使用自定义和笔划的最简单方法 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 是实现派生自的类 <xref:System.Windows.Controls.InkCanvas> ，并使用这些类。 <xref:System.Windows.Controls.InkCanvas>具有一个 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 属性，该属性指定在用户绘制笔画时如何呈现笔画。  
  
 若要在上自定义呈现笔画， <xref:System.Windows.Controls.InkCanvas> 请执行以下操作：  
  
- 创建一个派生自的类 <xref:System.Windows.Controls.InkCanvas> 。  
  
- 将自定义 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 的分配给 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> 属性。  
  
- 重写 <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 方法。 使用此方法时，请删除之前添加到 InkCanvas 的原始笔划。 然后创建一个自定义笔画，将其添加到 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 属性，并使用 <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> 包含自定义笔划的新来调用基类。  
  
 下面的 c # 代码演示一个自定义 <xref:System.Windows.Controls.InkCanvas> 类，该类使用自定义的 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 并收集自定义笔画。  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 <xref:System.Windows.Controls.InkCanvas>可以有多个 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 。 可以通过将多个 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 对象 <xref:System.Windows.Controls.InkCanvas> 添加到属性，将这些对象添加到中 <xref:System.Windows.UIElement.StylusPlugIns%2A> 。  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>结束语  
 您可以通过派生您自己的 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 、和类来自定义墨迹的外观 <xref:System.Windows.Ink.Stroke> <xref:System.Windows.Controls.InkCanvas> 。 将这些类结合使用可以确保用户绘制笔划时和笔划被收集后的笔划外观保持一致。  
  
## <a name="see-also"></a>请参阅

- [高级墨迹处理](advanced-ink-handling.md)
