---
title: 教程：在 Win32 应用程序中承载视觉对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
ms.openlocfilehash: 489e7e8d495893187b7b671b6aafac8118ea3018
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666532"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a><span data-ttu-id="88bd0-102">教程：在 Win32 应用程序中承载视觉对象</span><span class="sxs-lookup"><span data-stu-id="88bd0-102">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="88bd0-103">提供了用于创建应用程序的丰富环境。</span><span class="sxs-lookup"><span data-stu-id="88bd0-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="88bd0-104">但是，当你在 Win32 代码中有大量投资时，向 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序添加功能（而不是重写你的代码）可能更有效。</span><span class="sxs-lookup"><span data-stu-id="88bd0-104">However, when you have a substantial investment in Win32 code, it might be more effective to add [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] functionality to your application rather than rewrite your code.</span></span> <span data-ttu-id="88bd0-105">为了支持 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在应用程序中同时使用的 Win32 和图形子系统， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供了一种在 Win32 窗口中承载对象的机制。</span><span class="sxs-lookup"><span data-stu-id="88bd0-105">To provide support for Win32 and [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] graphics subsystems used concurrently in an application, [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] provides a mechanism for hosting objects in a Win32 window.</span></span>  
  
 <span data-ttu-id="88bd0-106">本教程介绍如何编写示例应用程序， [使用 Win32 互操作进行命中测试](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)，以 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在 win32 窗口中承载视觉对象。</span><span class="sxs-lookup"><span data-stu-id="88bd0-106">This tutorial describes how to write a sample application, [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting), that hosts [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] visual objects in a Win32 window.</span></span>  

<a name="requirements"></a>
## <a name="requirements"></a><span data-ttu-id="88bd0-107">要求</span><span class="sxs-lookup"><span data-stu-id="88bd0-107">Requirements</span></span>  
 <span data-ttu-id="88bd0-108">本教程假定你基本熟悉 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 和 Win32 编程。</span><span class="sxs-lookup"><span data-stu-id="88bd0-108">This tutorial assumes a basic familiarity with both [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] and Win32 programming.</span></span> <span data-ttu-id="88bd0-109">有关编程的基本简介 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，请参阅 [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="88bd0-109">For a basic introduction to [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] programming, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span> <span data-ttu-id="88bd0-110">有关 Win32 编程的介绍，请参阅主题中的任意一本书，如 Charles Petzold 的特定 *编程窗口* 中所述。</span><span class="sxs-lookup"><span data-stu-id="88bd0-110">For an introduction to Win32 programming, see any of the numerous books on the subject, in particular *Programming Windows* by Charles Petzold.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88bd0-111">本教程包括来自相关示例的一些代码示例。</span><span class="sxs-lookup"><span data-stu-id="88bd0-111">This tutorial includes a number of code examples from the associated sample.</span></span> <span data-ttu-id="88bd0-112">但是，出于可读性考虑，不包括完整的示例代码。</span><span class="sxs-lookup"><span data-stu-id="88bd0-112">However, for readability, it does not include the complete sample code.</span></span> <span data-ttu-id="88bd0-113">有关完整的示例代码，请参阅 [通过 Win32 互操作进行命中测试示例](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)。</span><span class="sxs-lookup"><span data-stu-id="88bd0-113">For the complete sample code, see [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).</span></span>  
  
<a name="creating_the_host_win32_window"></a>
## <a name="creating-the-host-win32-window"></a><span data-ttu-id="88bd0-114">创建宿主 Win32 窗口</span><span class="sxs-lookup"><span data-stu-id="88bd0-114">Creating the Host Win32 Window</span></span>  
 <span data-ttu-id="88bd0-115">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]在 Win32 窗口中承载对象的关键是 <xref:System.Windows.Interop.HwndSource> 类。</span><span class="sxs-lookup"><span data-stu-id="88bd0-115">The key to hosting [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] objects in a Win32 window is the <xref:System.Windows.Interop.HwndSource> class.</span></span> <span data-ttu-id="88bd0-116">此类 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在 Win32 窗口中包装对象，从而使它们可以 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 作为子窗口合并到中。</span><span class="sxs-lookup"><span data-stu-id="88bd0-116">This class wraps the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] objects in a Win32 window, allowing them to be incorporated into your [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] as a child window.</span></span>  
  
 <span data-ttu-id="88bd0-117">下面的示例演示了用于 <xref:System.Windows.Interop.HwndSource> 将对象创建为视觉对象的 Win32 容器窗口的代码。</span><span class="sxs-lookup"><span data-stu-id="88bd0-117">The following example shows the code for creating the <xref:System.Windows.Interop.HwndSource> object as the Win32 container window for the visual objects.</span></span> <span data-ttu-id="88bd0-118">若要设置 Win32 窗口的窗口样式、位置和其他参数，请使用 <xref:System.Windows.Interop.HwndSourceParameters> 对象。</span><span class="sxs-lookup"><span data-stu-id="88bd0-118">To set the window style, position, and other parameters for the Win32 window, use the <xref:System.Windows.Interop.HwndSourceParameters> object.</span></span>  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> <span data-ttu-id="88bd0-119"><xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A>不能将属性的值设置为 WS_EX_TRANSPARENT。</span><span class="sxs-lookup"><span data-stu-id="88bd0-119">The value of the <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> property cannot be set to WS_EX_TRANSPARENT.</span></span> <span data-ttu-id="88bd0-120">这意味着主机 Win32 窗口不能是透明的。</span><span class="sxs-lookup"><span data-stu-id="88bd0-120">This means that the host Win32 window cannot be transparent.</span></span> <span data-ttu-id="88bd0-121">出于此原因，主机 Win32 窗口的背景色设置为与父窗口相同的背景色。</span><span class="sxs-lookup"><span data-stu-id="88bd0-121">For this reason, the background color of the host Win32 window is set to the same background color as its parent window.</span></span>  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>
## <a name="adding-visual-objects-to-the-host-win32-window"></a><span data-ttu-id="88bd0-122">将视觉对象添加到宿主 Win32 窗口</span><span class="sxs-lookup"><span data-stu-id="88bd0-122">Adding Visual Objects to the Host Win32 Window</span></span>  
 <span data-ttu-id="88bd0-123">为视觉对象创建宿主 Win32 容器窗口后，可以向其添加视觉对象。</span><span class="sxs-lookup"><span data-stu-id="88bd0-123">Once you have created a host Win32 container window for the visual objects, you can add visual objects to it.</span></span> <span data-ttu-id="88bd0-124">你需要确保任何视觉对象的转换（如动画）不超出主机 Win32 窗口的边框的界限。</span><span class="sxs-lookup"><span data-stu-id="88bd0-124">You will want to ensure that any transformations of the visual objects, such as animations, do not extend beyond the bounds of the host Win32 window's bounding rectangle.</span></span>  
  
 <span data-ttu-id="88bd0-125">下面的示例演示用于创建 <xref:System.Windows.Interop.HwndSource> 对象并向其中添加可视对象的代码。</span><span class="sxs-lookup"><span data-stu-id="88bd0-125">The following example shows the code for creating the <xref:System.Windows.Interop.HwndSource> object and adding visual objects to it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88bd0-126"><xref:System.Windows.Interop.HwndSource.RootVisual%2A>对象的属性 <xref:System.Windows.Interop.HwndSource> 设置为添加到主机 Win32 窗口的第一个视觉对象。</span><span class="sxs-lookup"><span data-stu-id="88bd0-126">The <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object is set to the first visual object added to the host Win32 window.</span></span> <span data-ttu-id="88bd0-127">根视觉对象定义视觉对象树最顶层的节点。</span><span class="sxs-lookup"><span data-stu-id="88bd0-127">The root visual object defines the top-most node of the visual object tree.</span></span> <span data-ttu-id="88bd0-128">添加到主机 Win32 窗口中的任何后续视觉对象将添加为子对象。</span><span class="sxs-lookup"><span data-stu-id="88bd0-128">Any subsequent visual objects added to the host Win32 window are added as child objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>
## <a name="implementing-the-win32-message-filter"></a><span data-ttu-id="88bd0-129">实现 Win32 消息筛选器</span><span class="sxs-lookup"><span data-stu-id="88bd0-129">Implementing the Win32 Message Filter</span></span>  
 <span data-ttu-id="88bd0-130">视觉对象的宿主 Win32 窗口需要一个窗口消息筛选器过程来处理从应用程序队列发送到窗口的消息。</span><span class="sxs-lookup"><span data-stu-id="88bd0-130">The host Win32 window for the visual objects requires a window message filter procedure to handle messages that are sent to the window from the application queue.</span></span> <span data-ttu-id="88bd0-131">窗口过程接收来自 Win32 系统的消息。</span><span class="sxs-lookup"><span data-stu-id="88bd0-131">The window procedure receives messages from the Win32 system.</span></span> <span data-ttu-id="88bd0-132">这些消息可以是输入消息，也可以是窗口管理消息。</span><span class="sxs-lookup"><span data-stu-id="88bd0-132">These may be input messages or window-management messages.</span></span> <span data-ttu-id="88bd0-133">可以选择在窗口过程中处理一条消息，或将消息传递到系统以供默认处理。</span><span class="sxs-lookup"><span data-stu-id="88bd0-133">You can optionally handle a message in your window procedure or pass the message to the system for default processing.</span></span>  
  
 <span data-ttu-id="88bd0-134"><xref:System.Windows.Interop.HwndSource>您定义为视觉对象的父级的对象必须引用您提供的窗口消息筛选器过程。</span><span class="sxs-lookup"><span data-stu-id="88bd0-134">The <xref:System.Windows.Interop.HwndSource> object that you defined as the parent for the visual objects must reference the window message filter procedure you provide.</span></span> <span data-ttu-id="88bd0-135">创建 <xref:System.Windows.Interop.HwndSource> 对象时，请将属性设置 <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> 为引用该窗口过程。</span><span class="sxs-lookup"><span data-stu-id="88bd0-135">When you create the <xref:System.Windows.Interop.HwndSource> object, set the <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> property to reference the window procedure.</span></span>  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 <span data-ttu-id="88bd0-136">下面的示例演示用于处理释放鼠标左键和右键消息的代码。</span><span class="sxs-lookup"><span data-stu-id="88bd0-136">The following example shows the code for handling the left and right mouse button up messages.</span></span> <span data-ttu-id="88bd0-137">鼠标点击位置的坐标值包含在参数的值中 `lParam` 。</span><span class="sxs-lookup"><span data-stu-id="88bd0-137">The coordinate value of the mouse hit position is contained in the value of the `lParam` parameter.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>
## <a name="processing-the-win32-messages"></a><span data-ttu-id="88bd0-138">处理 Win32 消息</span><span class="sxs-lookup"><span data-stu-id="88bd0-138">Processing the Win32 Messages</span></span>  
 <span data-ttu-id="88bd0-139">以下示例中的代码演示了如何针对主机 Win32 窗口中包含的视觉对象的层次结构执行命中测试。</span><span class="sxs-lookup"><span data-stu-id="88bd0-139">The code in the following example shows how a hit test is performed against the hierarchy of visual objects contained in the host Win32 window.</span></span> <span data-ttu-id="88bd0-140">您可以通过使用 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 方法指定要对其进行命中测试的根可视对象和坐标值，来识别某个点是否在可视对象的几何图形内。</span><span class="sxs-lookup"><span data-stu-id="88bd0-140">You can identify whether a point is within the geometry of a visual object, by using the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to specify the root visual object and the coordinate value to hit test against.</span></span> <span data-ttu-id="88bd0-141">在这种情况下，根可视对象是对象的属性的值 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> <xref:System.Windows.Interop.HwndSource> 。</span><span class="sxs-lookup"><span data-stu-id="88bd0-141">In this case, the root visual object is the value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="88bd0-142">有关对视觉对象进行命中测试的详细信息，请参阅 [可视化层中的命中测试](hit-testing-in-the-visual-layer.md)。</span><span class="sxs-lookup"><span data-stu-id="88bd0-142">For more information on hit testing against visual objects, see [Hit Testing in the Visual Layer](hit-testing-in-the-visual-layer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88bd0-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="88bd0-143">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="88bd0-144">使用 Win32 互操作进行命中测试示例</span><span class="sxs-lookup"><span data-stu-id="88bd0-144">Hit Test with Win32 Interoperation Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [<span data-ttu-id="88bd0-145">可视化层中的命中测试</span><span class="sxs-lookup"><span data-stu-id="88bd0-145">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
