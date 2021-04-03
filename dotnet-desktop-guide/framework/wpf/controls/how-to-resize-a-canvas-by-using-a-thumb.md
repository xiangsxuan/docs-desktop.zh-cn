---
title: 如何：使用 Thumb 调整画布的大小
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: 84f5ac2b53124b7f4d7c15741e94b40e7ee81526
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972937"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="41e74-102">如何：使用 Thumb 调整画布的大小</span><span class="sxs-lookup"><span data-stu-id="41e74-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="41e74-103">此示例演示如何使用 <xref:System.Windows.Controls.Primitives.Thumb> 控件调整控件的大小 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="41e74-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41e74-104">示例</span><span class="sxs-lookup"><span data-stu-id="41e74-104">Example</span></span>  
 <span data-ttu-id="41e74-105"><xref:System.Windows.Controls.Primitives.Thumb>控件提供的拖动功能可用于通过监视和的事件来移动控件或调整控件的大小 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="41e74-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="41e74-106">当鼠标指针在控件上暂停时，用户通过按鼠标左键开始拖动操作 <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="41e74-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="41e74-107">只要鼠标左键处于按下状态，拖动操作便会继续。</span><span class="sxs-lookup"><span data-stu-id="41e74-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="41e74-108">在拖动操作过程中， <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 可以出现多次。</span><span class="sxs-lookup"><span data-stu-id="41e74-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="41e74-109">每次发生时， <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> 类提供与鼠标位置变化相对应的位置的更改。</span><span class="sxs-lookup"><span data-stu-id="41e74-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="41e74-110">当用户释放鼠标左键时，拖动操作完成。</span><span class="sxs-lookup"><span data-stu-id="41e74-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="41e74-111">拖动操作仅提供新坐标;它不会自动重定位 <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="41e74-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="41e74-112">下面的示例显示一个 <xref:System.Windows.Controls.Primitives.Thumb> 控件，该控件是控件的子元素 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="41e74-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="41e74-113">其事件的事件处理程序 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 提供了用于移动和重 <xref:System.Windows.Controls.Primitives.Thumb> 设大小的逻辑 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="41e74-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="41e74-114">和事件的事件处理程序在 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> <xref:System.Windows.Controls.Primitives.Thumb> 拖动操作期间更改的颜色。</span><span class="sxs-lookup"><span data-stu-id="41e74-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="41e74-115">下面的示例定义 <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="41e74-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="41e74-116">下面的示例演示了 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 一个事件处理程序，该处理程序 <xref:System.Windows.Controls.Primitives.Thumb> <xref:System.Windows.Controls.Canvas> 在响应鼠标移动的情况下移动和调整大小。</span><span class="sxs-lookup"><span data-stu-id="41e74-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="41e74-117">下面的示例显示了 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="41e74-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="41e74-118">下面的示例显示了 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="41e74-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="41e74-119">有关完整示例，请参阅 [Thumb 拖动功能示例](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps)。</span><span class="sxs-lookup"><span data-stu-id="41e74-119">For the complete sample, see [Thumb Drag Functionality Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e74-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41e74-120">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
