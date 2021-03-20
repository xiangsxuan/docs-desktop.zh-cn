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
# <a name="custom-rendering-ink"></a><span data-ttu-id="6e672-102">自定义呈现墨迹</span><span class="sxs-lookup"><span data-stu-id="6e672-102">Custom Rendering Ink</span></span>
<span data-ttu-id="6e672-103"><xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>使用笔划的属性可以指定笔划的外观，例如，其大小、颜色和形状，但有时您可能希望自定义除 "允许" 之外的外观 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-103">The <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property of a stroke allows you to specify the appearance of a stroke, such as its size, color, and shape, but there may be times that you want to customize the appearance beyond what <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> allow.</span></span> <span data-ttu-id="6e672-104">建议通过使用喷笔、油画和多种其他效果呈现外观，从而自定义墨迹的外观。</span><span class="sxs-lookup"><span data-stu-id="6e672-104">You may want to customize the appearance of ink by rendering in the appearance of an air brush, oil paint, and many other effects.</span></span> <span data-ttu-id="6e672-105">使用 Windows Presentation Foundation (WPF) ，可以通过实现自定义和对象自定义呈现墨迹 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Ink.Stroke> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-105">The Windows Presentation Foundation (WPF) allows you to custom render ink by implementing a custom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and <xref:System.Windows.Ink.Stroke> object.</span></span>  
  
 <span data-ttu-id="6e672-106">本主题包含以下小节：</span><span class="sxs-lookup"><span data-stu-id="6e672-106">This topic contains the following subsections:</span></span>  
  
- [<span data-ttu-id="6e672-107">体系结构</span><span class="sxs-lookup"><span data-stu-id="6e672-107">Architecture</span></span>](#Architecture)  
  
- [<span data-ttu-id="6e672-108">实现动态呈现器</span><span class="sxs-lookup"><span data-stu-id="6e672-108">Implementing a Dynamic Renderer</span></span>](#ImplementingADynamicRenderer)  
  
- [<span data-ttu-id="6e672-109">实现自定义笔划</span><span class="sxs-lookup"><span data-stu-id="6e672-109">Implementing Custom Strokes</span></span>](#ImplementingCustomStrokes)  
  
- [<span data-ttu-id="6e672-110">实现自定义 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="6e672-110">Implementing a Custom InkCanvas</span></span>](#ImplementingACustomInkCanvas)  
  
- [<span data-ttu-id="6e672-111">结束语</span><span class="sxs-lookup"><span data-stu-id="6e672-111">Conclusion</span></span>](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a><span data-ttu-id="6e672-112">体系结构</span><span class="sxs-lookup"><span data-stu-id="6e672-112">Architecture</span></span>  
 <span data-ttu-id="6e672-113">墨迹呈现会出现两次：用户将墨迹写入墨迹书写表面时，以及将笔划添加到启用了墨迹的表面之后。</span><span class="sxs-lookup"><span data-stu-id="6e672-113">Ink rendering occurs two times; when a user writes ink to an inking surface, and again after the stroke is added to the ink-enabled surface.</span></span> <span data-ttu-id="6e672-114"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>当用户将触笔移到数字化仪上时，将呈现墨迹，并在将 <xref:System.Windows.Ink.Stroke> 其添加到元素中后呈现自己。</span><span class="sxs-lookup"><span data-stu-id="6e672-114">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the ink when the user moves the tablet pen on the digitizer, and the <xref:System.Windows.Ink.Stroke> renders itself once it is added to an element.</span></span>  
  
 <span data-ttu-id="6e672-115">动态呈现墨迹时需要实现三个类。</span><span class="sxs-lookup"><span data-stu-id="6e672-115">There are three classes to implement when dynamically rendering ink.</span></span>  
  
1. <span data-ttu-id="6e672-116">**DynamicRenderer**：实现一个派生自的类 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-116">**DynamicRenderer**: Implement a class that derives from <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="6e672-117">此类是一个专用 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 的，它在绘制时呈现笔画。</span><span class="sxs-lookup"><span data-stu-id="6e672-117">This class is a specialized <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> that renders the stroke as it is drawn.</span></span> <span data-ttu-id="6e672-118">在 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 单独的线程上进行呈现，因此即使在应用程序用户界面 (UI) 线程被阻止时，墨迹图面也会显示为收集墨迹。</span><span class="sxs-lookup"><span data-stu-id="6e672-118">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> does the rendering on a separate thread, so the inking surface appears to collect ink even when the application user interface (UI) thread is blocked.</span></span> <span data-ttu-id="6e672-119">有关线程模型的详细信息，请参阅[墨迹线程模型](the-ink-threading-model.md)。</span><span class="sxs-lookup"><span data-stu-id="6e672-119">For more information about the threading model, see [The Ink Threading Model](the-ink-threading-model.md).</span></span> <span data-ttu-id="6e672-120">若要自定义动态呈现笔画，请重写 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="6e672-120">To customize dynamically rendering a stroke, override the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> method.</span></span>  
  
2. <span data-ttu-id="6e672-121">**Stroke**：实现一个派生自的类 <xref:System.Windows.Ink.Stroke> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-121">**Stroke**: Implement a class that derives from <xref:System.Windows.Ink.Stroke>.</span></span> <span data-ttu-id="6e672-122">此类负责在将 <xref:System.Windows.Input.StylusPoint> 数据转换为对象之后静态呈现该数据 <xref:System.Windows.Ink.Stroke> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-122">This class is responsible for static rendering of the <xref:System.Windows.Input.StylusPoint> data after it has been converted into a <xref:System.Windows.Ink.Stroke> object.</span></span> <span data-ttu-id="6e672-123">重写 <xref:System.Windows.Ink.Stroke.DrawCore%2A> 方法以确保笔划的静态呈现与动态呈现一致。</span><span class="sxs-lookup"><span data-stu-id="6e672-123">Override the <xref:System.Windows.Ink.Stroke.DrawCore%2A> method to ensure that static rendering of the stroke is consistent with dynamic rendering.</span></span>  
  
3. <span data-ttu-id="6e672-124">**InkCanvas：** 实现派生自的类 <xref:System.Windows.Controls.InkCanvas> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-124">**InkCanvas:** Implement a class that derives from <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="6e672-125">将自定义的分配 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 给 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="6e672-125">Assign the customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property.</span></span> <span data-ttu-id="6e672-126">重写 <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 方法，并向属性添加自定义笔画 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-126">Override the <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> method and add a custom stroke to the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property.</span></span> <span data-ttu-id="6e672-127">这样可以确保墨迹外观一致。</span><span class="sxs-lookup"><span data-stu-id="6e672-127">This ensures that the appearance of the ink is consistent.</span></span>  
  
<a name="ImplementingADynamicRenderer"></a>
## <a name="implementing-a-dynamic-renderer"></a><span data-ttu-id="6e672-128">实现动态呈现器</span><span class="sxs-lookup"><span data-stu-id="6e672-128">Implementing a Dynamic Renderer</span></span>  
 <span data-ttu-id="6e672-129">尽管 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 类是的标准部分，但 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 若要执行更专用的呈现，则必须创建从派生的自定义动态呈现器 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 并重写 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="6e672-129">Although the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> class is a standard part of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], to perform more specialized rendering, you must create a customized dynamic renderer that derives from the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and override the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> method.</span></span>  
  
 <span data-ttu-id="6e672-130">下面的示例演示了一个 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 使用线性渐变画笔效果绘制墨迹的自定义。</span><span class="sxs-lookup"><span data-stu-id="6e672-130">The following example demonstrates a customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> that draws ink with a linear gradient brush effect.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>
## <a name="implementing-custom-strokes"></a><span data-ttu-id="6e672-131">实现自定义笔划</span><span class="sxs-lookup"><span data-stu-id="6e672-131">Implementing Custom Strokes</span></span>  
 <span data-ttu-id="6e672-132">实现从 <xref:System.Windows.Ink.Stroke> 派生的类。</span><span class="sxs-lookup"><span data-stu-id="6e672-132">Implement a class that derives from <xref:System.Windows.Ink.Stroke>.</span></span> <span data-ttu-id="6e672-133">此类负责 <xref:System.Windows.Input.StylusPoint> 在将数据转换为对象之后呈现数据 <xref:System.Windows.Ink.Stroke> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-133">This class is responsible for rendering <xref:System.Windows.Input.StylusPoint> data after it has been converted into a <xref:System.Windows.Ink.Stroke> object.</span></span> <span data-ttu-id="6e672-134">重写 <xref:System.Windows.Ink.Stroke.DrawCore%2A> 类以执行实际绘图。</span><span class="sxs-lookup"><span data-stu-id="6e672-134">Override the <xref:System.Windows.Ink.Stroke.DrawCore%2A> class to do the actual drawing.</span></span>  
  
 <span data-ttu-id="6e672-135">Stroke 类还可以使用方法存储自定义数据 <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-135">Your Stroke class can also store custom data by using the <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> method.</span></span> <span data-ttu-id="6e672-136">此数据持续存在时会与笔划数据一起存储。</span><span class="sxs-lookup"><span data-stu-id="6e672-136">This data is stored with the stroke data when persisted.</span></span>  
  
 <span data-ttu-id="6e672-137"><xref:System.Windows.Ink.Stroke>类还可以执行命中测试。</span><span class="sxs-lookup"><span data-stu-id="6e672-137">The <xref:System.Windows.Ink.Stroke> class can also perform hit testing.</span></span> <span data-ttu-id="6e672-138">还可以通过 <xref:System.Windows.Ink.Stroke.HitTest%2A> 在当前类中重写方法来实现自己的命中测试算法。</span><span class="sxs-lookup"><span data-stu-id="6e672-138">You can also implement your own hit testing algorithm by overriding the <xref:System.Windows.Ink.Stroke.HitTest%2A> method in the current class.</span></span>  
  
 <span data-ttu-id="6e672-139">下面的 c # 代码演示了一个以 <xref:System.Windows.Ink.Stroke> <xref:System.Windows.Input.StylusPoint> 三维笔画形式呈现数据的自定义类。</span><span class="sxs-lookup"><span data-stu-id="6e672-139">The following C# code demonstrates a custom <xref:System.Windows.Ink.Stroke> class that renders <xref:System.Windows.Input.StylusPoint> data as a 3D stroke.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>
## <a name="implementing-a-custom-inkcanvas"></a><span data-ttu-id="6e672-140">实现自定义 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="6e672-140">Implementing a Custom InkCanvas</span></span>  
 <span data-ttu-id="6e672-141">使用自定义和笔划的最简单方法 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 是实现派生自的类 <xref:System.Windows.Controls.InkCanvas> ，并使用这些类。</span><span class="sxs-lookup"><span data-stu-id="6e672-141">The easiest way to use your customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and stroke is to implement a class that derives from <xref:System.Windows.Controls.InkCanvas> and uses these classes.</span></span> <span data-ttu-id="6e672-142"><xref:System.Windows.Controls.InkCanvas>具有一个 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 属性，该属性指定在用户绘制笔画时如何呈现笔画。</span><span class="sxs-lookup"><span data-stu-id="6e672-142">The <xref:System.Windows.Controls.InkCanvas> has a <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property that specifies how the stroke is rendered when the user is drawing it.</span></span>  
  
 <span data-ttu-id="6e672-143">若要在上自定义呈现笔画， <xref:System.Windows.Controls.InkCanvas> 请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6e672-143">To custom render strokes on an <xref:System.Windows.Controls.InkCanvas> do the following:</span></span>  
  
- <span data-ttu-id="6e672-144">创建一个派生自的类 <xref:System.Windows.Controls.InkCanvas> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-144">Create a class that derives from the <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
- <span data-ttu-id="6e672-145">将自定义 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 的分配给 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="6e672-145">Assign your customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="6e672-146">重写 <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="6e672-146">Override the <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> method.</span></span> <span data-ttu-id="6e672-147">使用此方法时，请删除之前添加到 InkCanvas 的原始笔划。</span><span class="sxs-lookup"><span data-stu-id="6e672-147">In this method, remove the original stroke that was added to the InkCanvas.</span></span> <span data-ttu-id="6e672-148">然后创建一个自定义笔画，将其添加到 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 属性，并使用 <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> 包含自定义笔划的新来调用基类。</span><span class="sxs-lookup"><span data-stu-id="6e672-148">Then create a custom stroke, add it to the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property, and call the base class with a new <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> that contains the custom stroke.</span></span>  
  
 <span data-ttu-id="6e672-149">下面的 c # 代码演示一个自定义 <xref:System.Windows.Controls.InkCanvas> 类，该类使用自定义的 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 并收集自定义笔画。</span><span class="sxs-lookup"><span data-stu-id="6e672-149">The following C# code demonstrates a custom <xref:System.Windows.Controls.InkCanvas> class that uses a customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and collects custom strokes.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 <span data-ttu-id="6e672-150"><xref:System.Windows.Controls.InkCanvas>可以有多个 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-150">An <xref:System.Windows.Controls.InkCanvas> can have more than one <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="6e672-151">可以通过将多个 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 对象 <xref:System.Windows.Controls.InkCanvas> 添加到属性，将这些对象添加到中 <xref:System.Windows.UIElement.StylusPlugIns%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-151">You can add multiple <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objects to the <xref:System.Windows.Controls.InkCanvas> by adding them to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span>  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a><span data-ttu-id="6e672-152">结束语</span><span class="sxs-lookup"><span data-stu-id="6e672-152">Conclusion</span></span>  
 <span data-ttu-id="6e672-153">您可以通过派生您自己的 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 、和类来自定义墨迹的外观 <xref:System.Windows.Ink.Stroke> <xref:System.Windows.Controls.InkCanvas> 。</span><span class="sxs-lookup"><span data-stu-id="6e672-153">You can customize the appearance of ink by deriving your own <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, and <xref:System.Windows.Controls.InkCanvas> classes.</span></span> <span data-ttu-id="6e672-154">将这些类结合使用可以确保用户绘制笔划时和笔划被收集后的笔划外观保持一致。</span><span class="sxs-lookup"><span data-stu-id="6e672-154">Together, these classes ensure that the appearance of the stroke is consistent when the user draws the stroke and after it is collected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e672-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e672-155">See also</span></span>

- [<span data-ttu-id="6e672-156">高级墨迹处理</span><span class="sxs-lookup"><span data-stu-id="6e672-156">Advanced Ink Handling</span></span>](advanced-ink-handling.md)
