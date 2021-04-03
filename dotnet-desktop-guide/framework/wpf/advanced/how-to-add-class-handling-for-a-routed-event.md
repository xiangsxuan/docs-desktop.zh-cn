---
title: 如何：为路由事件添加类处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 7b897954cbdab461dc0305c6290e67c1af5282c3
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972474"
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a><span data-ttu-id="b53e3-102">如何：为路由事件添加类处理</span><span class="sxs-lookup"><span data-stu-id="b53e3-102">How to: Add Class Handling for a Routed Event</span></span>
<span data-ttu-id="b53e3-103">路由事件可以通过类处理程序或路由中任何给定节点上的实例处理程序来处理。</span><span class="sxs-lookup"><span data-stu-id="b53e3-103">Routed events can be handled either by class handlers or instance handlers on any given node in the route.</span></span> <span data-ttu-id="b53e3-104">首先调用类处理程序，类实现可使用这些处理程序来取消实例处理中的事件，或对由基类拥有的事件引入其他特定于事件的行为。</span><span class="sxs-lookup"><span data-stu-id="b53e3-104">Class handlers are invoked first, and can be used by class implementations to suppress events from instance handling or introduce other event specific behaviors on events that are owned by base classes.</span></span> <span data-ttu-id="b53e3-105">此示例阐释了实现类处理程序的两个紧密相关的技术。</span><span class="sxs-lookup"><span data-stu-id="b53e3-105">This example illustrates two closely related techniques for implementing class handlers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b53e3-106">示例</span><span class="sxs-lookup"><span data-stu-id="b53e3-106">Example</span></span>  
 <span data-ttu-id="b53e3-107">此示例使用基于面板的自定义类 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="b53e3-107">This example uses a custom class based on the <xref:System.Windows.Controls.Canvas> panel.</span></span> <span data-ttu-id="b53e3-108">应用程序的基本前提是自定义类在其子元素上引入了行为，包括截获鼠标左键单击并标记其处理，然后才会调用子元素类或其上的任何实例处理程序。</span><span class="sxs-lookup"><span data-stu-id="b53e3-108">The basic premise of the application is that the custom class introduces behaviors on its child elements, including intercepting any left mouse button clicks and marking them handled, before the child element class or any instance handlers on it will be invoked.</span></span>  
  
 <span data-ttu-id="b53e3-109"><xref:System.Windows.UIElement>类公开了一个虚拟方法，该方法 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> 通过只重写事件对事件启用类处理。</span><span class="sxs-lookup"><span data-stu-id="b53e3-109">The <xref:System.Windows.UIElement> class exposes a virtual method that enables class handling on the <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> event, by simply overriding the event.</span></span> <span data-ttu-id="b53e3-110">如果类的层次结构中的某个位置有此类处理方法，则这是实现类处理的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="b53e3-110">This is the simplest way to implement class handling if such a virtual method is available somewhere in your class' hierarchy.</span></span> <span data-ttu-id="b53e3-111">下面的代码演示了 <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> 从派生的 "MyEditContainer" 中的实现 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="b53e3-111">The following code shows the <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementation in the "MyEditContainer" that is derived from <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="b53e3-112">实现会将事件标记为已在参数中处理，然后添加一些代码，使源元素成为基本的可见更改。</span><span class="sxs-lookup"><span data-stu-id="b53e3-112">The implementation marks the event as handled in the arguments, and then adds some code to give the source element a basic visible change.</span></span>  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 <span data-ttu-id="b53e3-113">如果基类或该特定方法中没有可用的虚拟，则可以使用类的实用工具方法直接添加类处理 <xref:System.Windows.EventManager> <xref:System.Windows.EventManager.RegisterClassHandler%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b53e3-113">If no virtual is available on base classes or for that particular method, class handling can be added directly using a utility method of the <xref:System.Windows.EventManager> class, <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span></span> <span data-ttu-id="b53e3-114">只应在添加类处理的类的静态初始化中调用此方法。</span><span class="sxs-lookup"><span data-stu-id="b53e3-114">This method should only be called within the static initialization of classes that are adding class handling.</span></span> <span data-ttu-id="b53e3-115">此示例为添加了另一个处理程序 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> ，在这种情况下，已注册的类为自定义类。</span><span class="sxs-lookup"><span data-stu-id="b53e3-115">This example adds another handler for <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , and in this case the registered class is the custom class.</span></span> <span data-ttu-id="b53e3-116">相反，当使用虚方法时，已注册的类实际上是 <xref:System.Windows.UIElement> 基类。</span><span class="sxs-lookup"><span data-stu-id="b53e3-116">In contrast, when using the virtuals, the registered class is really the <xref:System.Windows.UIElement> base class.</span></span> <span data-ttu-id="b53e3-117">如果基类和子类都注册了类处理，则首先调用子类处理程序。</span><span class="sxs-lookup"><span data-stu-id="b53e3-117">In cases where base classes and subclass each register class handling, the subclass handlers are invoked first.</span></span> <span data-ttu-id="b53e3-118">应用程序中的行为是：首先，此处理程序会显示其消息框，然后将显示虚方法的处理程序中的可视更改。</span><span class="sxs-lookup"><span data-stu-id="b53e3-118">The behavior in an application would be that first this handler would show its message box and then the visual change in the virtual method's handler would be shown.</span></span>  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a><span data-ttu-id="b53e3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b53e3-119">See also</span></span>

- <xref:System.Windows.EventManager>
- [<span data-ttu-id="b53e3-120">将路由事件标记为“已处理”和“类处理”</span><span class="sxs-lookup"><span data-stu-id="b53e3-120">Marking Routed Events as Handled, and Class Handling</span></span>](marking-routed-events-as-handled-and-class-handling.md)
- [<span data-ttu-id="b53e3-121">处理路由事件</span><span class="sxs-lookup"><span data-stu-id="b53e3-121">Handle a Routed Event</span></span>](how-to-handle-a-routed-event.md)
- [<span data-ttu-id="b53e3-122">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="b53e3-122">Routed Events Overview</span></span>](routed-events-overview.md)
