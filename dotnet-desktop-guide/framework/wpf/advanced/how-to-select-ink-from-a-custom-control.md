---
title: 如何：从自定义控件选择墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 5c9b2f3d64e4cbb309772d6a1d9fa88f589df84c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973693"
---
# <a name="how-to-select-ink-from-a-custom-control"></a>如何：从自定义控件选择墨迹
通过将添加 <xref:System.Windows.Ink.IncrementalLassoHitTester> 到自定义控件，可以启用控件，以便用户可以使用套索工具选择墨迹，这与使用套索选择墨迹的方式类似 <xref:System.Windows.Controls.InkCanvas> 。  
  
 本示例假定您熟悉如何创建启用了墨的自定义控件。  若要创建接受墨迹输入的自定义控件，请参阅 [创建墨迹输入控件](creating-an-ink-input-control.md)。  
  
## <a name="example"></a>示例  
 当用户绘制套索时，将 <xref:System.Windows.Ink.IncrementalLassoHitTester> 预测用户完成套索后哪些笔划将位于套索路径边界内。  在套索路径边界内确定的笔划可被视为处于选中状态。  选定的笔划也可以取消选中状态。  例如，如果用户在绘制套索时反转方向，则 <xref:System.Windows.Ink.IncrementalLassoHitTester> 可以取消选择某些笔画。  
  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>引发 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 事件，该事件使自定义控件可以在用户绘制套索时做出响应。  例如，当用户选择并取消选择笔划时，可以更改笔划的外观。  
  
## <a name="managing-the-ink-mode"></a>管理墨迹模式  
 如果套索显示方式与控件上的墨迹不同，则对用户非常有用。 若要实现此目的，自定义控件必须跟踪用户是否正在编写或选择墨迹。 要执行此操作，最简单的方法是声明一个包含两个值的枚举：一个用于指示用户正在写入墨迹，另一个用于指示用户正在选择墨迹。  
  
 [!code-csharp[HowToSelectInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 接下来，向类添加两个 <xref:System.Windows.Ink.DrawingAttributes> ：一个用于在用户写入墨迹时使用，一个在用户选择墨迹时使用。  在构造函数中，初始化， <xref:System.Windows.Ink.DrawingAttributes> 并将两个 <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> 事件附加到同一个事件处理程序。 然后，将 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> 的属性设置 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 为墨迹 <xref:System.Windows.Ink.DrawingAttributes> 。  
  
 [!code-csharp[HowToSelectInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 添加一个属性，该属性公开选择模式。 当用户更改选择模式时，将 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> 的属性设置 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 为相应的对象， <xref:System.Windows.Ink.DrawingAttributes> 然后将属性重新附加 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 到 <xref:System.Windows.Controls.InkPresenter> 。  
  
 [!code-csharp[HowToSelectInk#5](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 将 <xref:System.Windows.Ink.DrawingAttributes> 作为属性公开，以便应用程序可以确定墨笔划和选择笔划的外观。  
  
 [!code-csharp[HowToSelectInk#6](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 当对象的属性 <xref:System.Windows.Ink.DrawingAttributes> 更改时，必须重新 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 附加到 <xref:System.Windows.Controls.InkPresenter> 。  在事件的事件处理程序中，将重新 <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> 附加 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 到 <xref:System.Windows.Controls.InkPresenter> 。  
  
 [!code-csharp[HowToSelectInk#7](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a>使用 IncrementalLassoHitTester  
 创建并初始化一个 <xref:System.Windows.Ink.StrokeCollection> 包含所选笔画的。  
  
 [!code-csharp[HowToSelectInk#8](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 当用户开始绘制笔划（墨迹或套索）时，请取消选择任何所选笔画。 然后，如果用户正在绘制套索，则 <xref:System.Windows.Ink.IncrementalLassoHitTester> 通过调用创建 <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A> ，订阅 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 事件，然后调用 <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A> 。 此代码可以是单独的方法，并从 <xref:System.Windows.UIElement.OnStylusDown%2A> 和 <xref:System.Windows.UIElement.OnMouseDown%2A> 方法调用。  
  
 [!code-csharp[HowToSelectInk#9](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 在用户绘制套索时，向添加触笔接触点 <xref:System.Windows.Ink.IncrementalLassoHitTester> 。  从 <xref:System.Windows.UIElement.OnStylusMove%2A> 、 <xref:System.Windows.UIElement.OnStylusUp%2A> 、 <xref:System.Windows.UIElement.OnMouseMove%2A> 和方法调用以下方法 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 。  
  
 [!code-csharp[HowToSelectInk#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 处理 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> 事件，以便在用户选择和取消选择笔划时做出响应。  <xref:System.Windows.Ink.LassoSelectionChangedEventArgs>类具有 <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> 和属性， <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> 这些属性分别用于获取已选中和未选中的笔划。  
  
 [!code-csharp[HowToSelectInk#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 当用户完成套索绘制后，请取消订阅 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 事件并调用 <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A> 。  
  
 [!code-csharp[HowToSelectInk#12](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a>将其放在一起。  
 下面的示例是一个自定义控件，该控件使用户能够使用套索选择墨迹。  
  
 [!code-csharp[HowToSelectInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Ink.IncrementalLassoHitTester>
- <xref:System.Windows.Ink.StrokeCollection>
- <xref:System.Windows.Input.StylusPointCollection>
- [创建墨迹输入控件](creating-an-ink-input-control.md)
