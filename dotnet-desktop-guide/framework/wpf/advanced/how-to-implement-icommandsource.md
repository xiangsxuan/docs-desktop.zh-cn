---
title: 如何：实现 ICommandSource
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 2d8238eb4e008b8032ca0c22da44a554438765fc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972584"
---
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="1d573-102">如何：实现 ICommandSource</span><span class="sxs-lookup"><span data-stu-id="1d573-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="1d573-103">此示例演示如何通过实现来创建命令源 <xref:System.Windows.Input.ICommandSource> 。</span><span class="sxs-lookup"><span data-stu-id="1d573-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="1d573-104">命令源是一个知道如何调用命令的对象。</span><span class="sxs-lookup"><span data-stu-id="1d573-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="1d573-105"><xref:System.Windows.Input.ICommandSource>接口公开三个成员：</span><span class="sxs-lookup"><span data-stu-id="1d573-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="1d573-106"><xref:System.Windows.Input.ICommandSource.Command%2A>：要调用的命令。</span><span class="sxs-lookup"><span data-stu-id="1d573-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="1d573-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>：用户定义数据类型，它从命令源传递到处理命令的方法。</span><span class="sxs-lookup"><span data-stu-id="1d573-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="1d573-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>：在其上执行命令的对象。</span><span class="sxs-lookup"><span data-stu-id="1d573-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="1d573-109">在此示例中，创建了从 <xref:System.Windows.Controls.Slider> 控件继承并实现接口的类  <xref:System.Windows.Input.ICommandSource> 。</span><span class="sxs-lookup"><span data-stu-id="1d573-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="1d573-110">示例</span><span class="sxs-lookup"><span data-stu-id="1d573-110">Example</span></span>

<span data-ttu-id="1d573-111">WPF 提供了许多实现的类 <xref:System.Windows.Input.ICommandSource> ，例如、 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.MenuItem> 和 <xref:System.Windows.Documents.Hyperlink> 。</span><span class="sxs-lookup"><span data-stu-id="1d573-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="1d573-112">命令源定义它调用命令的方式。</span><span class="sxs-lookup"><span data-stu-id="1d573-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="1d573-113">这些类在被单击时调用一个命令，在设置其属性时，它们只能成为命令源 <xref:System.Windows.Input.ICommandSource.Command%2A> 。</span><span class="sxs-lookup"><span data-stu-id="1d573-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="1d573-114">在此示例中，你将在移动滑块时或者更准确地在更改属性时调用该命令 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 。</span><span class="sxs-lookup"><span data-stu-id="1d573-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="1d573-115">下面是类定义：</span><span class="sxs-lookup"><span data-stu-id="1d573-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="1d573-116">下一步是实现 <xref:System.Windows.Input.ICommandSource> 成员。</span><span class="sxs-lookup"><span data-stu-id="1d573-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="1d573-117">在此示例中，属性实现为 <xref:System.Windows.DependencyProperty> 对象。</span><span class="sxs-lookup"><span data-stu-id="1d573-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="1d573-118">这使属性能够使用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="1d573-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="1d573-119">有关类的详细信息 <xref:System.Windows.DependencyProperty> ，请参阅 [依赖属性概述](dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1d573-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="1d573-120">有关数据绑定的详细信息，请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。</span><span class="sxs-lookup"><span data-stu-id="1d573-120">For more information about data binding, see the [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>

<span data-ttu-id="1d573-121">此处仅 <xref:System.Windows.Input.ICommandSource.Command%2A> 显示属性。</span><span class="sxs-lookup"><span data-stu-id="1d573-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="1d573-122">下面是 <xref:System.Windows.DependencyProperty> 更改回调：</span><span class="sxs-lookup"><span data-stu-id="1d573-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="1d573-123">下一步是添加和删除与命令源关联的命令。</span><span class="sxs-lookup"><span data-stu-id="1d573-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="1d573-124"><xref:System.Windows.Input.ICommandSource.Command%2A>添加新命令时，属性不能简单覆盖，因为与前一个命令相关联的事件处理程序（如果有）必须先删除。</span><span class="sxs-lookup"><span data-stu-id="1d573-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="1d573-125">下一步是创建处理程序的逻辑 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 。</span><span class="sxs-lookup"><span data-stu-id="1d573-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="1d573-126">此 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 事件通知命令源，对当前命令目标执行的命令的功能可能已更改。</span><span class="sxs-lookup"><span data-stu-id="1d573-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="1d573-127">当命令源收到此事件时，它通常会对 <xref:System.Windows.Input.ICommand.CanExecute%2A> 命令调用方法。</span><span class="sxs-lookup"><span data-stu-id="1d573-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="1d573-128">如果无法对当前命令目标执行该命令，则命令源通常会禁用自身。</span><span class="sxs-lookup"><span data-stu-id="1d573-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="1d573-129">如果命令可在当前命令目标上执行，则命令源通常会自行启用。</span><span class="sxs-lookup"><span data-stu-id="1d573-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="1d573-130">最后一步是 <xref:System.Windows.Input.ICommand.Execute%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1d573-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="1d573-131">如果命令为，则 <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> 调用方法; 否则，将 <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> 调用方法。</span><span class="sxs-lookup"><span data-stu-id="1d573-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="1d573-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d573-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="1d573-133">命令概述</span><span class="sxs-lookup"><span data-stu-id="1d573-133">Commanding Overview</span></span>](commanding-overview.md)
