---
title: 如何：使用 Win32 宿主容器执行命中测试
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: a181b66eb527a0194bdc392c2b57c3e5822affb3
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973507"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="e2ef6-102">如何：使用 Win32 宿主容器执行命中测试</span><span class="sxs-lookup"><span data-stu-id="e2ef6-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="e2ef6-103">可以通过为视觉对象提供主机窗口容器，在 Win32 窗口中创建视觉对象。</span><span class="sxs-lookup"><span data-stu-id="e2ef6-103">You can create visual objects within a Win32 window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="e2ef6-104">若要为包含的视觉对象提供事件处理，需要处理传递到宿主窗口容器的消息筛选器循环的消息。</span><span class="sxs-lookup"><span data-stu-id="e2ef6-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="e2ef6-105">有关如何在 Win32 窗口中承载视觉对象的详细信息，请参阅 [教程：在 Win32 应用程序中承载视觉对象](tutorial-hosting-visual-objects-in-a-win32-application.md) 。</span><span class="sxs-lookup"><span data-stu-id="e2ef6-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a Win32 window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2ef6-106">示例</span><span class="sxs-lookup"><span data-stu-id="e2ef6-106">Example</span></span>  
 <span data-ttu-id="e2ef6-107">下面的代码演示如何为 Win32 窗口设置鼠标事件处理程序，该窗口用作视觉对象的宿主容器。</span><span class="sxs-lookup"><span data-stu-id="e2ef6-107">The following code shows how to set up mouse event handlers for a Win32 window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="e2ef6-108">下面的示例演示如何设置用于响应捕获特定鼠标事件的命中测试。</span><span class="sxs-lookup"><span data-stu-id="e2ef6-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="e2ef6-109"><xref:System.Windows.Interop.HwndSource>对象 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 在 Win32 窗口中显示内容。</span><span class="sxs-lookup"><span data-stu-id="e2ef6-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] content within a Win32 window.</span></span> <span data-ttu-id="e2ef6-110">对象的属性的值 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> <xref:System.Windows.Interop.HwndSource> 表示可视化树层次结构中最顶层的节点。</span><span class="sxs-lookup"><span data-stu-id="e2ef6-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="e2ef6-111">有关使用 Win32 主机容器命中测试对象的完整示例，请参阅 [使用 Win32 互操作进行命中测试示例](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)。</span><span class="sxs-lookup"><span data-stu-id="e2ef6-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ef6-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2ef6-112">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="e2ef6-113">可视化层中的命中测试</span><span class="sxs-lookup"><span data-stu-id="e2ef6-113">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="e2ef6-114">教程：在 Win32 应用程序中承载视觉对象</span><span class="sxs-lookup"><span data-stu-id="e2ef6-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](tutorial-hosting-visual-objects-in-a-win32-application.md)
