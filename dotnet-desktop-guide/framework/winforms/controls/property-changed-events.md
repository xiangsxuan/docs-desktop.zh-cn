---
title: 属性更改事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: 939972713ad95e9302c436268f4a6288a659ca6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972856"
---
# <a name="property-changed-events"></a><span data-ttu-id="18f18-102">属性更改事件</span><span class="sxs-lookup"><span data-stu-id="18f18-102">Property-Changed Events</span></span>

<span data-ttu-id="18f18-103">如果希望控件在名为 *propertyname* 的属性发生更改时发送通知，请定义名为 *propertyname* 的事件 `Changed` 和 `On` 引发事件的名为 *propertyname* 的方法 `Changed` 。</span><span class="sxs-lookup"><span data-stu-id="18f18-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="18f18-104">Windows 窗体中的命名约定是将 *更改* 的单词附加到属性的名称。</span><span class="sxs-lookup"><span data-stu-id="18f18-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="18f18-105">属性更改事件的关联事件委托类型为 <xref:System.EventHandler> ，事件数据类型为 <xref:System.EventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="18f18-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="18f18-106">基类 <xref:System.Windows.Forms.Control> 定义许多属性更改事件，例如、、、等 <xref:System.Windows.Forms.Control.BackColorChanged> <xref:System.Windows.Forms.Control.BackgroundImageChanged> <xref:System.Windows.Forms.Control.FontChanged> <xref:System.Windows.Forms.Control.LocationChanged> 。</span><span class="sxs-lookup"><span data-stu-id="18f18-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="18f18-107">有关事件的背景信息，请参阅[Windows 窗体控件中的](events-in-windows-forms-controls.md)[事件](/dotnet/standard/events/index)和事件。</span><span class="sxs-lookup"><span data-stu-id="18f18-107">For background information about events, see [Events](/dotnet/standard/events/index) and [Events in Windows Forms Controls](events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="18f18-108">属性更改事件很有用，因为它们允许控件的使用者附加响应更改的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="18f18-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="18f18-109">如果控件需要响应它引发的属性更改的事件，请重写相应的 `On` *PropertyName* `Changed` 方法，而不是将委托附加到事件。</span><span class="sxs-lookup"><span data-stu-id="18f18-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="18f18-110">控件通常通过更新其他属性或通过重绘其部分或全部绘制图面来响应属性更改事件。</span><span class="sxs-lookup"><span data-stu-id="18f18-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="18f18-111">下面的示例演示 `FlashTrackBar` 自定义控件如何响应其继承自的某些属性更改事件 <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="18f18-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="18f18-112">有关完整示例，请参阅 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="18f18-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="18f18-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="18f18-113">See also</span></span>

- [<span data-ttu-id="18f18-114">事件</span><span class="sxs-lookup"><span data-stu-id="18f18-114">Events</span></span>](/dotnet/standard/events/index)
- [<span data-ttu-id="18f18-115">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="18f18-115">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="18f18-116">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="18f18-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
