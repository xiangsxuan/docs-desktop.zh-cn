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
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>如何：使用 Thumb 调整画布的大小
此示例演示如何使用 <xref:System.Windows.Controls.Primitives.Thumb> 控件调整控件的大小 <xref:System.Windows.Controls.Canvas> 。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.Primitives.Thumb>控件提供的拖动功能可用于通过监视和的事件来移动控件或调整控件的大小 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> <xref:System.Windows.Controls.Primitives.Thumb> 。  
  
 当鼠标指针在控件上暂停时，用户通过按鼠标左键开始拖动操作 <xref:System.Windows.Controls.Primitives.Thumb> 。 只要鼠标左键处于按下状态，拖动操作便会继续。 在拖动操作过程中， <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 可以出现多次。 每次发生时， <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> 类提供与鼠标位置变化相对应的位置的更改。 当用户释放鼠标左键时，拖动操作完成。 拖动操作仅提供新坐标;它不会自动重定位 <xref:System.Windows.Controls.Primitives.Thumb> 。  
  
 下面的示例显示一个 <xref:System.Windows.Controls.Primitives.Thumb> 控件，该控件是控件的子元素 <xref:System.Windows.Controls.Canvas> 。 其事件的事件处理程序 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 提供了用于移动和重 <xref:System.Windows.Controls.Primitives.Thumb> 设大小的逻辑 <xref:System.Windows.Controls.Canvas> 。 和事件的事件处理程序在 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> <xref:System.Windows.Controls.Primitives.Thumb> 拖动操作期间更改的颜色。 下面的示例定义 <xref:System.Windows.Controls.Primitives.Thumb> 。  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 下面的示例演示了 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 一个事件处理程序，该处理程序 <xref:System.Windows.Controls.Primitives.Thumb> <xref:System.Windows.Controls.Canvas> 在响应鼠标移动的情况下移动和调整大小。  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 下面的示例显示了 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 事件处理程序。  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 下面的示例显示了 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 事件处理程序。  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 有关完整示例，请参阅 [Thumb 拖动功能示例](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
