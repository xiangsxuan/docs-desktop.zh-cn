---
title: 截获触笔输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: f05a3c25a61e90ec91cd1db725ba9a40763f0a7f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970470"
---
# <a name="intercepting-input-from-the-stylus"></a><span data-ttu-id="03905-102">截获触笔输入</span><span class="sxs-lookup"><span data-stu-id="03905-102">Intercepting Input from the Stylus</span></span>

<span data-ttu-id="03905-103">该 <xref:System.Windows.Input.StylusPlugIns> 体系结构提供了一种机制，用于实现对 <xref:System.Windows.Input.Stylus> 输入和数字墨迹对象创建的低级别控制 <xref:System.Windows.Ink.Stroke> 。</span><span class="sxs-lookup"><span data-stu-id="03905-103">The <xref:System.Windows.Input.StylusPlugIns> architecture provides a mechanism for implementing low-level control over <xref:System.Windows.Input.Stylus> input and the creation of digital ink <xref:System.Windows.Ink.Stroke> objects.</span></span> <span data-ttu-id="03905-104"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类提供一种机制，用于实现自定义行为，并将其应用于来自触笔设备的数据流，以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="03905-104">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> class provides a mechanism for you to implement custom behavior and apply it to the stream of data coming from the stylus device for the optimal performance.</span></span>  
  
 <span data-ttu-id="03905-105">本主题包含以下小节：</span><span class="sxs-lookup"><span data-stu-id="03905-105">This topic contains the following subsections:</span></span>  
  
- [<span data-ttu-id="03905-106">体系结构</span><span class="sxs-lookup"><span data-stu-id="03905-106">Architecture</span></span>](#Architecture)  
  
- [<span data-ttu-id="03905-107">实现触笔插件</span><span class="sxs-lookup"><span data-stu-id="03905-107">Implementing Stylus Plug-ins</span></span>](#ImplementingStylusPlugins)  
  
- [<span data-ttu-id="03905-108">将插件添加到 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="03905-108">Adding Your Plug-in to an InkCanvas</span></span>](#AddingYourPluginToAnInkCanvas)  
  
- [<span data-ttu-id="03905-109">结束语</span><span class="sxs-lookup"><span data-stu-id="03905-109">Conclusion</span></span>](#Conclusion)  
  
<a name="Architecture"></a>

## <a name="architecture"></a><span data-ttu-id="03905-110">体系结构</span><span class="sxs-lookup"><span data-stu-id="03905-110">Architecture</span></span>  

 <span data-ttu-id="03905-111"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>是[StylusInput](/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) api 的发展，如[访问和操作笔输入](/previous-versions/ms818317(v%3dmsdn.10))中所述。</span><span class="sxs-lookup"><span data-stu-id="03905-111">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> is the evolution of the [StylusInput](/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) APIs, described in [Accessing and Manipulating Pen Input](/previous-versions/ms818317(v%3dmsdn.10)).</span></span>  
  
 <span data-ttu-id="03905-112">每个 <xref:System.Windows.UIElement> 都有一个的 <xref:System.Windows.UIElement.StylusPlugIns%2A> 属性 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 。</span><span class="sxs-lookup"><span data-stu-id="03905-112">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.UIElement.StylusPlugIns%2A> property that is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span> <span data-ttu-id="03905-113">可以向 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 元素的属性添加， <xref:System.Windows.UIElement.StylusPlugIns%2A> 以便在生成数据时对数据进行操作 <xref:System.Windows.Input.StylusPoint> 。</span><span class="sxs-lookup"><span data-stu-id="03905-113">You can add a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to an element's <xref:System.Windows.UIElement.StylusPlugIns%2A> property to manipulate <xref:System.Windows.Input.StylusPoint> data as it is generated.</span></span> <span data-ttu-id="03905-114"><xref:System.Windows.Input.StylusPoint> 数据包含系统数字化器支持的所有属性，包括 <xref:System.Windows.Input.StylusPoint.X%2A> 和 <xref:System.Windows.Input.StylusPoint.Y%2A> 点数据以及 <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> 数据。</span><span class="sxs-lookup"><span data-stu-id="03905-114"><xref:System.Windows.Input.StylusPoint> data consists of all the properties supported by the system digitizer, including the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> point data, as well as <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> data.</span></span>  
  
 <span data-ttu-id="03905-115"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.Stylus> 当你将添加到属性中时，你的对象将直接插入来自设备的数据流 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.UIElement.StylusPlugIns%2A> 。</span><span class="sxs-lookup"><span data-stu-id="03905-115">Your <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects are inserted directly into the stream of data coming from the <xref:System.Windows.Input.Stylus> device when you add the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span> <span data-ttu-id="03905-116">插件添加到集合中的顺序 <xref:System.Windows.UIElement.StylusPlugIns%2A> 指示它们将接收数据的顺序 <xref:System.Windows.Input.StylusPoint> 。</span><span class="sxs-lookup"><span data-stu-id="03905-116">The order in which plug-ins are added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection dictates the order in which they will receive <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="03905-117">例如，如果添加一个筛选器插件，该插件将输入限制为特定区域，然后添加一个可在写入时识别手势的插件，则识别手势的插件将接收筛选的 <xref:System.Windows.Input.StylusPoint> 数据。</span><span class="sxs-lookup"><span data-stu-id="03905-117">For example, if you add a filter plug-in that restricts input to a particular region, and then add a plug-in that recognizes gestures as they are written, the plug-in that recognizes gestures will receive filtered <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
<a name="ImplementingStylusPlugins"></a>

## <a name="implementing-stylus-plug-ins"></a><span data-ttu-id="03905-118">实现触笔插件</span><span class="sxs-lookup"><span data-stu-id="03905-118">Implementing Stylus Plug-ins</span></span>  

 <span data-ttu-id="03905-119">若要实现某个插件，请从派生一个类 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 。</span><span class="sxs-lookup"><span data-stu-id="03905-119">To implement a plug-in, derive a class from <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span> <span data-ttu-id="03905-120">此类应用于从传入的数据流的输出 <xref:System.Windows.Input.Stylus> 。</span><span class="sxs-lookup"><span data-stu-id="03905-120">This class is applied o the stream of data as it comes in from the <xref:System.Windows.Input.Stylus>.</span></span> <span data-ttu-id="03905-121">在此类中，您可以修改数据的值 <xref:System.Windows.Input.StylusPoint> 。</span><span class="sxs-lookup"><span data-stu-id="03905-121">In this class you can modify the values of the <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="03905-122">如果 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 引发或导致异常，应用程序将关闭。</span><span class="sxs-lookup"><span data-stu-id="03905-122">If a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> throws or causes an exception, the application will close.</span></span> <span data-ttu-id="03905-123">你应全面测试使用的控件， <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 并且仅当你确定 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 不会引发异常时，才使用控件。</span><span class="sxs-lookup"><span data-stu-id="03905-123">You should thoroughly test controls that consume a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and only use a control if you are certain the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> will not throw an exception.</span></span>  
  
 <span data-ttu-id="03905-124">下面的示例演示一个插件，该插件通过修改数据中来自设备的和值来限制触笔输入 <xref:System.Windows.Input.StylusPoint.X%2A> <xref:System.Windows.Input.StylusPoint.Y%2A> <xref:System.Windows.Input.StylusPoint> <xref:System.Windows.Input.Stylus> 。</span><span class="sxs-lookup"><span data-stu-id="03905-124">The following example demonstrates a plug-in that restricts the stylus input by modifying the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> values in the <xref:System.Windows.Input.StylusPoint> data as it comes in from the <xref:System.Windows.Input.Stylus> device.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>

## <a name="adding-your-plug-in-to-an-inkcanvas"></a><span data-ttu-id="03905-125">将插件添加到 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="03905-125">Adding Your Plug-in to an InkCanvas</span></span>  

 <span data-ttu-id="03905-126">使用自定义插件的最简单方法是实现从 InkCanvas 派生的类并将其添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="03905-126">The easiest way to use your custom plug-in is to implement a class that derives from InkCanvas and add it to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span>  
  
 <span data-ttu-id="03905-127">下面的示例演示 <xref:System.Windows.Controls.InkCanvas> 用于筛选墨迹的自定义。</span><span class="sxs-lookup"><span data-stu-id="03905-127">The following example demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 <span data-ttu-id="03905-128">如果你将添加 `FilterInkCanvas` 到应用程序并运行它，你会注意到，在用户完成笔划之前，不会将墨迹限制在某个区域。</span><span class="sxs-lookup"><span data-stu-id="03905-128">If you add a `FilterInkCanvas` to your application and run it, you will notice that the ink isn't restricted to a region until after the user completes a stroke.</span></span> <span data-ttu-id="03905-129">这是因为 <xref:System.Windows.Controls.InkCanvas> 具有一个 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 属性，该属性是 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ，并且已经是集合的成员 <xref:System.Windows.UIElement.StylusPlugIns%2A> 。</span><span class="sxs-lookup"><span data-stu-id="03905-129">This is because the <xref:System.Windows.Controls.InkCanvas> has a <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property, which is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and is already a member of the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="03905-130">添加到集合中的自定义接收 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.UIElement.StylusPlugIns%2A> <xref:System.Windows.Input.StylusPoint> 数据后接收数据 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 。</span><span class="sxs-lookup"><span data-stu-id="03905-130">The custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> you added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection receives the <xref:System.Windows.Input.StylusPoint> data after <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives data.</span></span> <span data-ttu-id="03905-131">因此，在 <xref:System.Windows.Input.StylusPoint> 用户将笔提起到结束笔划之前，将不会对数据进行筛选。</span><span class="sxs-lookup"><span data-stu-id="03905-131">As a result, the <xref:System.Windows.Input.StylusPoint> data will not be filtered until after the user lifts the pen to end a stroke.</span></span> <span data-ttu-id="03905-132">若要在用户绘制墨迹时筛选墨迹，必须在之前插入 `FilterPlugin` <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 。</span><span class="sxs-lookup"><span data-stu-id="03905-132">To filter the ink as the user draws it, you must insert the `FilterPlugin` before the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span>  
  
 <span data-ttu-id="03905-133">下面的 c # 代码演示了一个自定义，它在 <xref:System.Windows.Controls.InkCanvas> 绘制时筛选墨迹。</span><span class="sxs-lookup"><span data-stu-id="03905-133">The following C# code demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink as it is drawn.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>

## <a name="conclusion"></a><span data-ttu-id="03905-134">结束语</span><span class="sxs-lookup"><span data-stu-id="03905-134">Conclusion</span></span>  

 <span data-ttu-id="03905-135">通过派生你自己的 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 类并将它们插入到 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 集合中，你可以极大地增强数字墨迹的行为。</span><span class="sxs-lookup"><span data-stu-id="03905-135">By deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes and inserting them into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> collections, you can greatly enhance the behavior of your digital ink.</span></span> <span data-ttu-id="03905-136">您可以在生成数据时对其进行访问 <xref:System.Windows.Input.StylusPoint> ，从而为您提供自定义输入的机会 <xref:System.Windows.Input.Stylus> 。</span><span class="sxs-lookup"><span data-stu-id="03905-136">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to customize the <xref:System.Windows.Input.Stylus> input.</span></span> <span data-ttu-id="03905-137">由于你对数据具有这样的低级别访问权限 <xref:System.Windows.Input.StylusPoint> ，因此你可以实现墨迹收集并使用应用程序的最佳性能进行呈现。</span><span class="sxs-lookup"><span data-stu-id="03905-137">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and rendering with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03905-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="03905-138">See also</span></span>

- [<span data-ttu-id="03905-139">高级墨迹处理</span><span class="sxs-lookup"><span data-stu-id="03905-139">Advanced Ink Handling</span></span>](advanced-ink-handling.md)
- <span data-ttu-id="03905-140">[访问和操作笔输入](/previous-versions/ms818317(v%3dmsdn.10))</span><span class="sxs-lookup"><span data-stu-id="03905-140">[Accessing and Manipulating Pen Input](/previous-versions/ms818317(v%3dmsdn.10))</span></span>
