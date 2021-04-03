---
title: 如何：创建 RoutedCommand
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: d433658a3039c262d2f682eff09df646d978018c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973455"
---
# <a name="how-to-create-a-routedcommand"></a><span data-ttu-id="c3316-102">如何：创建 RoutedCommand</span><span class="sxs-lookup"><span data-stu-id="c3316-102">How to: Create a RoutedCommand</span></span>
<span data-ttu-id="c3316-103">此示例演示如何创建自定义 <xref:System.Windows.Input.RoutedCommand> ，以及如何通过创建 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 和 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 并将其附加到来实现自定义命令 <xref:System.Windows.Input.CommandBinding> 。</span><span class="sxs-lookup"><span data-stu-id="c3316-103">This example shows how to create a custom <xref:System.Windows.Input.RoutedCommand> and how to implement the custom command by creating a <xref:System.Windows.Input.ExecutedRoutedEventHandler> and a <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and attaching them to a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="c3316-104">有关命令的详细信息，请参阅 [命令概述](commanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c3316-104">For more information on commanding, see the [Commanding Overview](commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3316-105">示例</span><span class="sxs-lookup"><span data-stu-id="c3316-105">Example</span></span>  
 <span data-ttu-id="c3316-106">创建的第一步 <xref:System.Windows.Input.RoutedCommand> 是定义并对其进行实例化。</span><span class="sxs-lookup"><span data-stu-id="c3316-106">The first step in creating a <xref:System.Windows.Input.RoutedCommand> is defining the command and instantiating it.</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 <span data-ttu-id="c3316-107">若要在应用程序中使用命令，必须创建用于定义命令执行的操作的事件处理程序</span><span class="sxs-lookup"><span data-stu-id="c3316-107">In order to use the command in an application, event handlers which define what the command does must be created</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 <span data-ttu-id="c3316-108">接下来，  <xref:System.Windows.Input.CommandBinding> 创建一个将命令与事件处理程序相关联的。</span><span class="sxs-lookup"><span data-stu-id="c3316-108">Next, a  <xref:System.Windows.Input.CommandBinding> is created which associates the command with the event handlers.</span></span> <span data-ttu-id="c3316-109">在 <xref:System.Windows.Input.CommandBinding> 特定对象上创建。</span><span class="sxs-lookup"><span data-stu-id="c3316-109">The <xref:System.Windows.Input.CommandBinding> is created on a specific object.</span></span>  <span data-ttu-id="c3316-110">此对象 <xref:System.Windows.Input.CommandBinding> 在元素树中定义的范围</span><span class="sxs-lookup"><span data-stu-id="c3316-110">This object defines the scope of the <xref:System.Windows.Input.CommandBinding> in the element tree</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 <span data-ttu-id="c3316-111">最后一步是调用命令。</span><span class="sxs-lookup"><span data-stu-id="c3316-111">The final step is invoking the command.</span></span>  <span data-ttu-id="c3316-112">调用命令的一种方法是将其与相关联 <xref:System.Windows.Input.ICommandSource> ，例如 <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="c3316-112">One way to invoke a command is to associate it with a <xref:System.Windows.Input.ICommandSource>, such as a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 <span data-ttu-id="c3316-113">单击该按钮时，将 <xref:System.Windows.Input.RoutedCommand.Execute%2A> 调用自定义的方法 <xref:System.Windows.Input.RoutedCommand> 。</span><span class="sxs-lookup"><span data-stu-id="c3316-113">When the Button is clicked, the <xref:System.Windows.Input.RoutedCommand.Execute%2A> method on the custom <xref:System.Windows.Input.RoutedCommand> is called.</span></span>  <span data-ttu-id="c3316-114"><xref:System.Windows.Input.RoutedCommand>引发 <xref:System.Windows.Input.CommandManager.PreviewExecuted> 和 <xref:System.Windows.Input.CommandManager.Executed> 路由事件。</span><span class="sxs-lookup"><span data-stu-id="c3316-114">The <xref:System.Windows.Input.RoutedCommand> raises the <xref:System.Windows.Input.CommandManager.PreviewExecuted> and <xref:System.Windows.Input.CommandManager.Executed> routed events.</span></span>  <span data-ttu-id="c3316-115">这些事件遍历元素树， <xref:System.Windows.Input.CommandBinding> 以便查找此特定命令的。</span><span class="sxs-lookup"><span data-stu-id="c3316-115">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for this particular command.</span></span>  <span data-ttu-id="c3316-116">如果 <xref:System.Windows.Input.CommandBinding> 找到，则 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 调用与关联的 <xref:System.Windows.Input.CommandBinding> 。</span><span class="sxs-lookup"><span data-stu-id="c3316-116">If a <xref:System.Windows.Input.CommandBinding> is found, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> associated with <xref:System.Windows.Input.CommandBinding> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3316-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3316-117">See also</span></span>

- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="c3316-118">命令概述</span><span class="sxs-lookup"><span data-stu-id="c3316-118">Commanding Overview</span></span>](commanding-overview.md)
