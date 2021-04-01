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
# <a name="creating-an-ink-input-control"></a><span data-ttu-id="b7974-102">创建墨迹输入控件</span><span class="sxs-lookup"><span data-stu-id="b7974-102">Creating an Ink Input Control</span></span>

<span data-ttu-id="b7974-103">可以创建动态和静态呈现墨迹的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="b7974-103">You can create a custom control that dynamically and statically renders ink.</span></span> <span data-ttu-id="b7974-104">也就是说，当用户绘制笔划时呈现墨迹，使墨迹显示为触笔的 "流"，并在将墨迹添加到控件后通过 tablet 笔从剪贴板中粘贴或从文件加载墨迹来显示墨迹。</span><span class="sxs-lookup"><span data-stu-id="b7974-104">That is, render ink as a user draws a stroke, causing the ink to appear to "flow" from the tablet pen, and display ink after it is added to the control, either via the tablet pen, pasted from the Clipboard, or loaded from a file.</span></span> <span data-ttu-id="b7974-105">若要动态呈现墨迹，控件必须使用 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 。</span><span class="sxs-lookup"><span data-stu-id="b7974-105">To dynamically render ink, your control must use a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="b7974-106">若要以静态方式呈现墨迹，你必须重写触笔事件方法 (<xref:System.Windows.UIElement.OnStylusDown%2A> 、 <xref:System.Windows.UIElement.OnStylusMove%2A> 和 <xref:System.Windows.UIElement.OnStylusUp%2A>) 来收集 <xref:System.Windows.Input.StylusPoint> 数据、创建笔画，并将其添加到 <xref:System.Windows.Controls.InkPresenter> (以便在控件) 上呈现墨迹。</span><span class="sxs-lookup"><span data-stu-id="b7974-106">To statically render ink, you must override the stylus event methods (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, and <xref:System.Windows.UIElement.OnStylusUp%2A>) to collect <xref:System.Windows.Input.StylusPoint> data, create strokes, and add them to an <xref:System.Windows.Controls.InkPresenter> (which renders the ink on the control).</span></span>  
  
 <span data-ttu-id="b7974-107">本主题包含以下小节：</span><span class="sxs-lookup"><span data-stu-id="b7974-107">This topic contains the following subsections:</span></span>  
  
- [<span data-ttu-id="b7974-108">如何：收集触笔接触点数据和创建墨迹笔划</span><span class="sxs-lookup"><span data-stu-id="b7974-108">How to: Collect Stylus Point Data and Create Ink Strokes</span></span>](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [<span data-ttu-id="b7974-109">如何：使控件接受鼠标输入</span><span class="sxs-lookup"><span data-stu-id="b7974-109">How to: Enable Your Control to Accept Input from the Mouse</span></span>](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [<span data-ttu-id="b7974-110">综合运用</span><span class="sxs-lookup"><span data-stu-id="b7974-110">Putting it together</span></span>](#PuttingItTogether)  
  
- [<span data-ttu-id="b7974-111">使用其他插件和 DynamicRenderers</span><span class="sxs-lookup"><span data-stu-id="b7974-111">Using Additional Plug-ins and DynamicRenderers</span></span>](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [<span data-ttu-id="b7974-112">结束语</span><span class="sxs-lookup"><span data-stu-id="b7974-112">Conclusion</span></span>](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>

## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a><span data-ttu-id="b7974-113">如何：收集触笔接触点数据和创建墨迹笔划</span><span class="sxs-lookup"><span data-stu-id="b7974-113">How to: Collect Stylus Point Data and Create Ink Strokes</span></span>  

 <span data-ttu-id="b7974-114">若要创建用于收集和管理墨迹笔划的控件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b7974-114">To create a control that collects and manages ink strokes do the following:</span></span>  
  
1. <span data-ttu-id="b7974-115">从派生的类 <xref:System.Windows.Controls.Control> 或从派生的类之一（ <xref:System.Windows.Controls.Control> 如） <xref:System.Windows.Controls.Label> 。</span><span class="sxs-lookup"><span data-stu-id="b7974-115">Derive a class from <xref:System.Windows.Controls.Control> or one of the classes derived from <xref:System.Windows.Controls.Control>, such as <xref:System.Windows.Controls.Label>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. <span data-ttu-id="b7974-116">将添加 <xref:System.Windows.Controls.InkPresenter> 到类，并将 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性设置为新的 <xref:System.Windows.Controls.InkPresenter> 。</span><span class="sxs-lookup"><span data-stu-id="b7974-116">Add an <xref:System.Windows.Controls.InkPresenter> to the class and set the <xref:System.Windows.Controls.ContentControl.Content%2A> property to the new <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. <span data-ttu-id="b7974-117"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Controls.InkPresenter> 通过调用方法，将的添加到中 <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> ，并将添加 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 到集合中 <xref:System.Windows.UIElement.StylusPlugIns%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b7974-117">Attach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkPresenter> by calling the <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> method, and add the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="b7974-118">这样，便可以在 <xref:System.Windows.Controls.InkPresenter> 控件收集触笔点数据时显示墨迹。</span><span class="sxs-lookup"><span data-stu-id="b7974-118">This allows the <xref:System.Windows.Controls.InkPresenter> to display the ink as the stylus point data is collected by your control.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. <span data-ttu-id="b7974-119">重写 <xref:System.Windows.UIElement.OnStylusDown%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b7974-119">Override the <xref:System.Windows.UIElement.OnStylusDown%2A> method.</span></span>  <span data-ttu-id="b7974-120">在此方法中，通过调用来捕获触笔 <xref:System.Windows.Input.Stylus.Capture%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b7974-120">In this method, capture the stylus with a call to <xref:System.Windows.Input.Stylus.Capture%2A>.</span></span> <span data-ttu-id="b7974-121">捕获触笔后， <xref:System.Windows.UIElement.StylusMove> <xref:System.Windows.UIElement.StylusUp> 即使触笔离开控件边界，控件也将继续接收和事件。</span><span class="sxs-lookup"><span data-stu-id="b7974-121">By capturing the stylus, your control will to continue to receive <xref:System.Windows.UIElement.StylusMove> and <xref:System.Windows.UIElement.StylusUp> events even if the stylus leaves the control's boundaries.</span></span> <span data-ttu-id="b7974-122">这并不是绝对必需的，但几乎总是希望获得良好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="b7974-122">This is not strictly mandatory, but almost always desired for a good user experience.</span></span> <span data-ttu-id="b7974-123">创建新的 <xref:System.Windows.Input.StylusPointCollection> 以收集 <xref:System.Windows.Input.StylusPoint> 数据。</span><span class="sxs-lookup"><span data-stu-id="b7974-123">Create a new <xref:System.Windows.Input.StylusPointCollection> to gather <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="b7974-124">最后，将初始数据集添加 <xref:System.Windows.Input.StylusPoint> 到中 <xref:System.Windows.Input.StylusPointCollection> 。</span><span class="sxs-lookup"><span data-stu-id="b7974-124">Finally, add the initial set of <xref:System.Windows.Input.StylusPoint> data to the <xref:System.Windows.Input.StylusPointCollection>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. <span data-ttu-id="b7974-125">重写 <xref:System.Windows.UIElement.OnStylusMove%2A> 方法，并将 <xref:System.Windows.Input.StylusPoint> 数据添加到 <xref:System.Windows.Input.StylusPointCollection> 之前创建的对象。</span><span class="sxs-lookup"><span data-stu-id="b7974-125">Override the <xref:System.Windows.UIElement.OnStylusMove%2A> method and add the <xref:System.Windows.Input.StylusPoint> data to the <xref:System.Windows.Input.StylusPointCollection> object that you created earlier.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. <span data-ttu-id="b7974-126">重写 <xref:System.Windows.UIElement.OnStylusUp%2A> 方法，并使用数据创建新的 <xref:System.Windows.Ink.Stroke> <xref:System.Windows.Input.StylusPointCollection> 。</span><span class="sxs-lookup"><span data-stu-id="b7974-126">Override the <xref:System.Windows.UIElement.OnStylusUp%2A> method and create a new <xref:System.Windows.Ink.Stroke> with the <xref:System.Windows.Input.StylusPointCollection> data.</span></span> <span data-ttu-id="b7974-127">将创建的新添加 <xref:System.Windows.Ink.Stroke> 到 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 的集合 <xref:System.Windows.Controls.InkPresenter> ，并释放触笔捕获。</span><span class="sxs-lookup"><span data-stu-id="b7974-127">Add the new <xref:System.Windows.Ink.Stroke> you created to the <xref:System.Windows.Controls.InkPresenter.Strokes%2A> collection of the <xref:System.Windows.Controls.InkPresenter> and release stylus capture.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>

## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a><span data-ttu-id="b7974-128">如何：使控件接受鼠标输入</span><span class="sxs-lookup"><span data-stu-id="b7974-128">How to: Enable Your Control to Accept Input from the Mouse</span></span>  

 <span data-ttu-id="b7974-129">如果将前面的控件添加到应用程序，运行它，并使用鼠标作为输入设备，你会注意到这些笔划不会保留。</span><span class="sxs-lookup"><span data-stu-id="b7974-129">If you add the preceding control to your application, run it, and use the mouse as an input device, you will notice that the strokes are not persisted.</span></span> <span data-ttu-id="b7974-130">若要在鼠标作为输入设备使用时保持笔画，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b7974-130">To persist the strokes when the mouse is used as the input device do the following:</span></span>  
  
1. <span data-ttu-id="b7974-131">重写 <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> 并创建一个新的，并在 <xref:System.Windows.Input.StylusPointCollection> 事件发生时获取鼠标的位置，并 <xref:System.Windows.Input.StylusPoint> 使用点数据创建并将添加 <xref:System.Windows.Input.StylusPoint> 到 <xref:System.Windows.Input.StylusPointCollection> 。</span><span class="sxs-lookup"><span data-stu-id="b7974-131">Override the <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> and create a new <xref:System.Windows.Input.StylusPointCollection> Get the position of the mouse when the event occurred and create a <xref:System.Windows.Input.StylusPoint> using the point data and add the <xref:System.Windows.Input.StylusPoint> to the <xref:System.Windows.Input.StylusPointCollection>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. <span data-ttu-id="b7974-132">重写 <xref:System.Windows.UIElement.OnMouseMove%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b7974-132">Override the <xref:System.Windows.UIElement.OnMouseMove%2A> method.</span></span> <span data-ttu-id="b7974-133">在事件发生时获取鼠标位置，并 <xref:System.Windows.Input.StylusPoint> 使用点数据创建。</span><span class="sxs-lookup"><span data-stu-id="b7974-133">Get the position of the mouse when the event occurred and create a <xref:System.Windows.Input.StylusPoint> using the point data.</span></span>  <span data-ttu-id="b7974-134">将添加 <xref:System.Windows.Input.StylusPoint> 到 <xref:System.Windows.Input.StylusPointCollection> 之前创建的对象。</span><span class="sxs-lookup"><span data-stu-id="b7974-134">Add the <xref:System.Windows.Input.StylusPoint> to the <xref:System.Windows.Input.StylusPointCollection> object that you created earlier.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. <span data-ttu-id="b7974-135">重写 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b7974-135">Override the <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> method.</span></span>  <span data-ttu-id="b7974-136"><xref:System.Windows.Ink.Stroke>使用数据创建新的 <xref:System.Windows.Input.StylusPointCollection> ，并将创建的新添加 <xref:System.Windows.Ink.Stroke> 到 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 的集合中 <xref:System.Windows.Controls.InkPresenter> 。</span><span class="sxs-lookup"><span data-stu-id="b7974-136">Create a new <xref:System.Windows.Ink.Stroke> with the <xref:System.Windows.Input.StylusPointCollection> data, and add the new <xref:System.Windows.Ink.Stroke> you created to the <xref:System.Windows.Controls.InkPresenter.Strokes%2A> collection of the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>

## <a name="putting-it-together"></a><span data-ttu-id="b7974-137">综合运用</span><span class="sxs-lookup"><span data-stu-id="b7974-137">Putting it together</span></span>  

 <span data-ttu-id="b7974-138">下面的示例是在用户使用鼠标或笔时收集墨迹的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="b7974-138">The following example is a custom control that collects ink when the user uses either the mouse or the pen.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>

## <a name="using-additional-plug-ins-and-dynamicrenderers"></a><span data-ttu-id="b7974-139">使用其他插件和 DynamicRenderers</span><span class="sxs-lookup"><span data-stu-id="b7974-139">Using Additional Plug-ins and DynamicRenderers</span></span>  

 <span data-ttu-id="b7974-140">与 InkCanvas 一样，自定义控件可以具有自定义 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 对象和其他 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 对象。</span><span class="sxs-lookup"><span data-stu-id="b7974-140">Like the InkCanvas, your custom control can have custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and additional <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objects.</span></span> <span data-ttu-id="b7974-141">将它们添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 集合中。</span><span class="sxs-lookup"><span data-stu-id="b7974-141">Add these to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="b7974-142">中的对象的顺序 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 会影响呈现墨迹时的外观。</span><span class="sxs-lookup"><span data-stu-id="b7974-142">The order of the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> affects the appearance of the ink when it is rendered.</span></span> <span data-ttu-id="b7974-143">假设你有一个 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 名为的 `dynamicRenderer` 和一个名为的自定义 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> `translatePlugin` ，它将从 tablet 笔偏移墨迹。</span><span class="sxs-lookup"><span data-stu-id="b7974-143">Suppose you have a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> called `dynamicRenderer` and a custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> called `translatePlugin` that offsets the ink from the tablet pen.</span></span> <span data-ttu-id="b7974-144">如果 `translatePlugin` 是中的第一个 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> ，并且 `dynamicRenderer` 为第二个，则当用户移动笔时，"流" 的墨迹将偏移。</span><span class="sxs-lookup"><span data-stu-id="b7974-144">If `translatePlugin` is the first <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, and `dynamicRenderer` is the second, the ink that "flows" will be offset as the user moves the pen.</span></span> <span data-ttu-id="b7974-145">如果 `dynamicRenderer` 是第一个，并且 `translatePlugin` 为第二个，则在用户提起笔之前，墨迹不会偏移。</span><span class="sxs-lookup"><span data-stu-id="b7974-145">If `dynamicRenderer` is first, and `translatePlugin` is second, the ink will not be offset until the user lifts the pen.</span></span>  
  
<a name="AdvancedInkHandling_Conclusion"></a>

## <a name="conclusion"></a><span data-ttu-id="b7974-146">结束语</span><span class="sxs-lookup"><span data-stu-id="b7974-146">Conclusion</span></span>  

 <span data-ttu-id="b7974-147">可以通过重写触笔事件方法来创建一个用于收集和呈现墨迹的控件。</span><span class="sxs-lookup"><span data-stu-id="b7974-147">You can create a control that collects and renders ink by overriding the stylus event methods.</span></span> <span data-ttu-id="b7974-148">通过创建自己的控件，派生你自己 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 的类并将它们插入到中 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> ，你可以使用数字墨迹实现几乎任何行为想象。</span><span class="sxs-lookup"><span data-stu-id="b7974-148">By creating your own control, deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes, and inserting them the into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, you can implement virtually any behavior imaginable with digital ink.</span></span> <span data-ttu-id="b7974-149">你可以在生成数据时对其进行访问 <xref:System.Windows.Input.StylusPoint> ，使你可以自定义 <xref:System.Windows.Input.Stylus> 输入，并根据应用程序将其呈现在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="b7974-149">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to  customize <xref:System.Windows.Input.Stylus> input and render it on the screen as appropriate for your application.</span></span> <span data-ttu-id="b7974-150">由于你对数据具有此类低级别访问权限 <xref:System.Windows.Input.StylusPoint> ，因此你可以实现墨迹收集，并为应用程序提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="b7974-150">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and render it with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7974-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7974-151">See also</span></span>

- [<span data-ttu-id="b7974-152">高级墨迹处理</span><span class="sxs-lookup"><span data-stu-id="b7974-152">Advanced Ink Handling</span></span>](advanced-ink-handling.md)
- <span data-ttu-id="b7974-153">[访问和操作笔输入](/previous-versions/ms818317(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="b7974-153">[Accessing and Manipulating Pen Input](/previous-versions/ms818317(v=msdn.10))</span></span>
