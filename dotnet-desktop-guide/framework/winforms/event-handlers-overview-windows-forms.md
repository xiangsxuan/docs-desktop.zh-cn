---
title: 事件处理程序概述
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: ec8bc23ce8aba36ad456114ec645d4f0799f107f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971728"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="d8fec-102">事件处理程序概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="d8fec-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="d8fec-103">事件处理程序是绑定到事件的方法。</span><span class="sxs-lookup"><span data-stu-id="d8fec-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="d8fec-104">引发事件时，将执行事件处理程序中的代码。</span><span class="sxs-lookup"><span data-stu-id="d8fec-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="d8fec-105">每个事件处理程序提供了两个参数，可用于正确处理事件。</span><span class="sxs-lookup"><span data-stu-id="d8fec-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="d8fec-106">下面的示例演示控件事件的事件处理程序 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> 。</span><span class="sxs-lookup"><span data-stu-id="d8fec-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 <span data-ttu-id="d8fec-107">第一个参数 `sender` 提供对引发事件的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="d8fec-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="d8fec-108">`e`在上面的示例中，第二个参数传递特定于正在处理的事件的对象。</span><span class="sxs-lookup"><span data-stu-id="d8fec-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="d8fec-109">通过引用对象的属性 (，有时，它的方法) ，你可以获取诸如鼠标事件或拖放事件中正在传输的数据的鼠标位置等信息。</span><span class="sxs-lookup"><span data-stu-id="d8fec-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="d8fec-110">通常，每个事件都为第二个参数生成一个具有不同事件对象类型的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d8fec-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="d8fec-111">某些事件处理程序（例如和事件的）的 <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseUp> 第二个参数具有相同的对象类型。</span><span class="sxs-lookup"><span data-stu-id="d8fec-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="d8fec-112">对于这些类型的事件，可以使用同一事件处理程序来处理这两个事件。</span><span class="sxs-lookup"><span data-stu-id="d8fec-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="d8fec-113">你还可以使用同一事件处理程序来处理不同控件的同一事件。</span><span class="sxs-lookup"><span data-stu-id="d8fec-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="d8fec-114">例如，如果窗体上有一组 <xref:System.Windows.Forms.RadioButton> 控件，则可以为事件创建一个事件处理程序，并将 <xref:System.Windows.Forms.Control.Click> 每个控件的 <xref:System.Windows.Forms.Control.Click> 事件绑定到单个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d8fec-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="d8fec-115">有关详细信息，请参阅 [如何：将多个事件连接到 Windows 窗体中的单个事件处理程序](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="d8fec-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8fec-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8fec-116">See also</span></span>

- [<span data-ttu-id="d8fec-117">在 Windows 窗体中创建事件处理程序</span><span class="sxs-lookup"><span data-stu-id="d8fec-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="d8fec-118">事件概述</span><span class="sxs-lookup"><span data-stu-id="d8fec-118">Events Overview</span></span>](events-overview-windows-forms.md)
