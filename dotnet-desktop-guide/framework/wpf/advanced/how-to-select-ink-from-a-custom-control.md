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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973693"
---
# <a name="how-to-select-ink-from-a-custom-control"></a><span data-ttu-id="8a020-102">如何：从自定义控件选择墨迹</span><span class="sxs-lookup"><span data-stu-id="8a020-102">How to: Select Ink from a Custom Control</span></span>
<span data-ttu-id="8a020-103">通过将添加 <xref:System.Windows.Ink.IncrementalLassoHitTester> 到自定义控件，可以启用控件，以便用户可以使用套索工具选择墨迹，这与使用套索选择墨迹的方式类似 <xref:System.Windows.Controls.InkCanvas> 。</span><span class="sxs-lookup"><span data-stu-id="8a020-103">By adding an <xref:System.Windows.Ink.IncrementalLassoHitTester> to your custom control, you can enable your control so that a user can select ink with a lasso tool, similar to the way the <xref:System.Windows.Controls.InkCanvas> selects ink with a lasso.</span></span>  
  
 <span data-ttu-id="8a020-104">本示例假定您熟悉如何创建启用了墨的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="8a020-104">This example assumes you are familiar with creating an ink-enabled custom control.</span></span>  <span data-ttu-id="8a020-105">若要创建接受墨迹输入的自定义控件，请参阅 [创建墨迹输入控件](creating-an-ink-input-control.md)。</span><span class="sxs-lookup"><span data-stu-id="8a020-105">To create a custom control that accepts ink input, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a020-106">示例</span><span class="sxs-lookup"><span data-stu-id="8a020-106">Example</span></span>  
 <span data-ttu-id="8a020-107">当用户绘制套索时，将 <xref:System.Windows.Ink.IncrementalLassoHitTester> 预测用户完成套索后哪些笔划将位于套索路径边界内。</span><span class="sxs-lookup"><span data-stu-id="8a020-107">When the user draws a lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> predicts which strokes will be within the lasso path's boundaries after the user completes the lasso.</span></span>  <span data-ttu-id="8a020-108">在套索路径边界内确定的笔划可被视为处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="8a020-108">Strokes that are determined to be within the lasso path's boundaries can be thought of as being selected.</span></span>  <span data-ttu-id="8a020-109">选定的笔划也可以取消选中状态。</span><span class="sxs-lookup"><span data-stu-id="8a020-109">Selected strokes can also become unselected.</span></span>  <span data-ttu-id="8a020-110">例如，如果用户在绘制套索时反转方向，则 <xref:System.Windows.Ink.IncrementalLassoHitTester> 可以取消选择某些笔画。</span><span class="sxs-lookup"><span data-stu-id="8a020-110">For example, if the user reverses direction while drawing the lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> may unselect some strokes.</span></span>  
  
 <span data-ttu-id="8a020-111"><xref:System.Windows.Ink.IncrementalLassoHitTester>引发 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 事件，该事件使自定义控件可以在用户绘制套索时做出响应。</span><span class="sxs-lookup"><span data-stu-id="8a020-111">The <xref:System.Windows.Ink.IncrementalLassoHitTester> raises the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, which enables your custom control to respond while the user is drawing the lasso.</span></span>  <span data-ttu-id="8a020-112">例如，当用户选择并取消选择笔划时，可以更改笔划的外观。</span><span class="sxs-lookup"><span data-stu-id="8a020-112">For example, you can change the appearance of strokes as the user selects and unselects them.</span></span>  
  
## <a name="managing-the-ink-mode"></a><span data-ttu-id="8a020-113">管理墨迹模式</span><span class="sxs-lookup"><span data-stu-id="8a020-113">Managing the Ink Mode</span></span>  
 <span data-ttu-id="8a020-114">如果套索显示方式与控件上的墨迹不同，则对用户非常有用。</span><span class="sxs-lookup"><span data-stu-id="8a020-114">It is helpful to the user if the lasso appears differently than the ink on your control.</span></span> <span data-ttu-id="8a020-115">若要实现此目的，自定义控件必须跟踪用户是否正在编写或选择墨迹。</span><span class="sxs-lookup"><span data-stu-id="8a020-115">To accomplish this, your custom control must keep track of whether the user is writing or selecting ink.</span></span> <span data-ttu-id="8a020-116">要执行此操作，最简单的方法是声明一个包含两个值的枚举：一个用于指示用户正在写入墨迹，另一个用于指示用户正在选择墨迹。</span><span class="sxs-lookup"><span data-stu-id="8a020-116">The easiest way to do this is to declare an enumeration with two values: one to indicate that the user is writing ink and one to indicate that the user is selecting ink.</span></span>  
  
 [!code-csharp[HowToSelectInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 <span data-ttu-id="8a020-117">接下来，向类添加两个 <xref:System.Windows.Ink.DrawingAttributes> ：一个用于在用户写入墨迹时使用，一个在用户选择墨迹时使用。</span><span class="sxs-lookup"><span data-stu-id="8a020-117">Next, add two <xref:System.Windows.Ink.DrawingAttributes> to the class: one to use when the user writes ink, one to use when the user selects ink.</span></span>  <span data-ttu-id="8a020-118">在构造函数中，初始化， <xref:System.Windows.Ink.DrawingAttributes> 并将两个 <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> 事件附加到同一个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="8a020-118">In the constructor, initialize the <xref:System.Windows.Ink.DrawingAttributes> and attach both <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> events to the same event handler.</span></span> <span data-ttu-id="8a020-119">然后，将 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> 的属性设置 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 为墨迹 <xref:System.Windows.Ink.DrawingAttributes> 。</span><span class="sxs-lookup"><span data-stu-id="8a020-119">Then set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the ink <xref:System.Windows.Ink.DrawingAttributes>.</span></span>  
  
 [!code-csharp[HowToSelectInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 <span data-ttu-id="8a020-120">添加一个属性，该属性公开选择模式。</span><span class="sxs-lookup"><span data-stu-id="8a020-120">Add a property that exposes the selection mode.</span></span> <span data-ttu-id="8a020-121">当用户更改选择模式时，将 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> 的属性设置 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 为相应的对象， <xref:System.Windows.Ink.DrawingAttributes> 然后将属性重新附加 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 到 <xref:System.Windows.Controls.InkPresenter> 。</span><span class="sxs-lookup"><span data-stu-id="8a020-121">When the user changes the selection mode, set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the appropriate <xref:System.Windows.Ink.DrawingAttributes> object and then reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Property to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#5](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 <span data-ttu-id="8a020-122">将 <xref:System.Windows.Ink.DrawingAttributes> 作为属性公开，以便应用程序可以确定墨笔划和选择笔划的外观。</span><span class="sxs-lookup"><span data-stu-id="8a020-122">Expose the <xref:System.Windows.Ink.DrawingAttributes> as properties so applications can determine the appearance of the ink strokes and selection strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#6](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 <span data-ttu-id="8a020-123">当对象的属性 <xref:System.Windows.Ink.DrawingAttributes> 更改时，必须重新 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 附加到 <xref:System.Windows.Controls.InkPresenter> 。</span><span class="sxs-lookup"><span data-stu-id="8a020-123">When a property of a <xref:System.Windows.Ink.DrawingAttributes> object changes, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> must be reattached to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="8a020-124">在事件的事件处理程序中，将重新 <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> 附加 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 到 <xref:System.Windows.Controls.InkPresenter> 。</span><span class="sxs-lookup"><span data-stu-id="8a020-124">In the event handler for the <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> event, reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#7](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a><span data-ttu-id="8a020-125">使用 IncrementalLassoHitTester</span><span class="sxs-lookup"><span data-stu-id="8a020-125">Using the IncrementalLassoHitTester</span></span>  
 <span data-ttu-id="8a020-126">创建并初始化一个 <xref:System.Windows.Ink.StrokeCollection> 包含所选笔画的。</span><span class="sxs-lookup"><span data-stu-id="8a020-126">Create and initialize a <xref:System.Windows.Ink.StrokeCollection> that contains the selected strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#8](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 <span data-ttu-id="8a020-127">当用户开始绘制笔划（墨迹或套索）时，请取消选择任何所选笔画。</span><span class="sxs-lookup"><span data-stu-id="8a020-127">When the user starts to draw a stroke, either ink or the lasso, unselect any selected strokes.</span></span> <span data-ttu-id="8a020-128">然后，如果用户正在绘制套索，则 <xref:System.Windows.Ink.IncrementalLassoHitTester> 通过调用创建 <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A> ，订阅 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 事件，然后调用 <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8a020-128">Then, if the user is drawing a lasso, create an <xref:System.Windows.Ink.IncrementalLassoHitTester> by calling <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, subscribe to the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, and call <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span></span> <span data-ttu-id="8a020-129">此代码可以是单独的方法，并从 <xref:System.Windows.UIElement.OnStylusDown%2A> 和 <xref:System.Windows.UIElement.OnMouseDown%2A> 方法调用。</span><span class="sxs-lookup"><span data-stu-id="8a020-129">This code can be a separate method and called from the <xref:System.Windows.UIElement.OnStylusDown%2A> and <xref:System.Windows.UIElement.OnMouseDown%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#9](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 <span data-ttu-id="8a020-130">在用户绘制套索时，向添加触笔接触点 <xref:System.Windows.Ink.IncrementalLassoHitTester> 。</span><span class="sxs-lookup"><span data-stu-id="8a020-130">Add the stylus points to the <xref:System.Windows.Ink.IncrementalLassoHitTester> while the user draws the lasso.</span></span>  <span data-ttu-id="8a020-131">从 <xref:System.Windows.UIElement.OnStylusMove%2A> 、 <xref:System.Windows.UIElement.OnStylusUp%2A> 、 <xref:System.Windows.UIElement.OnMouseMove%2A> 和方法调用以下方法 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8a020-131">Call the following method from the <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, and <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 <span data-ttu-id="8a020-132">处理 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> 事件，以便在用户选择和取消选择笔划时做出响应。</span><span class="sxs-lookup"><span data-stu-id="8a020-132">Handle the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> event to respond when the user selects and unselects strokes.</span></span>  <span data-ttu-id="8a020-133"><xref:System.Windows.Ink.LassoSelectionChangedEventArgs>类具有 <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> 和属性， <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> 这些属性分别用于获取已选中和未选中的笔划。</span><span class="sxs-lookup"><span data-stu-id="8a020-133">The <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> class has the <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> and <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> properties that get the strokes that were selected and unselected, respectively.</span></span>  
  
 [!code-csharp[HowToSelectInk#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 <span data-ttu-id="8a020-134">当用户完成套索绘制后，请取消订阅 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 事件并调用 <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8a020-134">When the user finishes drawing the lasso, unsubscribe from the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event and call <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span></span>  
  
 [!code-csharp[HowToSelectInk#12](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a><span data-ttu-id="8a020-135">将其放在一起。</span><span class="sxs-lookup"><span data-stu-id="8a020-135">Putting it All Together.</span></span>  
 <span data-ttu-id="8a020-136">下面的示例是一个自定义控件，该控件使用户能够使用套索选择墨迹。</span><span class="sxs-lookup"><span data-stu-id="8a020-136">The following example is a custom control that enables a user to select ink with a lasso.</span></span>  
  
 [!code-csharp[HowToSelectInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8a020-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a020-137">See also</span></span>

- <xref:System.Windows.Ink.IncrementalLassoHitTester>
- <xref:System.Windows.Ink.StrokeCollection>
- <xref:System.Windows.Input.StylusPointCollection>
- [<span data-ttu-id="8a020-138">创建墨迹输入控件</span><span class="sxs-lookup"><span data-stu-id="8a020-138">Creating an Ink Input Control</span></span>](creating-an-ink-input-control.md)
