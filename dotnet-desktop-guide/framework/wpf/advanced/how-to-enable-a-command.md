---
title: 如何：启用命令
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
ms.openlocfilehash: a2044f9504b3f2ee05ccaa63fa5e0277e2798b60
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973452"
---
# <a name="how-to-enable-a-command"></a><span data-ttu-id="21164-102">如何：启用命令</span><span class="sxs-lookup"><span data-stu-id="21164-102">How to: Enable a Command</span></span>
<span data-ttu-id="21164-103">下面的示例演示如何在中使用命令 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="21164-103">The following example demonstrates how to use commanding in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)].</span></span>  <span data-ttu-id="21164-104">该示例演示如何将与关联 <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Controls.Button> ，创建 <xref:System.Windows.Input.CommandBinding> ，并创建实现的事件处理程序 <xref:System.Windows.Input.RoutedCommand> 。</span><span class="sxs-lookup"><span data-stu-id="21164-104">The example shows how to associate a <xref:System.Windows.Input.RoutedCommand> to a <xref:System.Windows.Controls.Button>, create a <xref:System.Windows.Input.CommandBinding>, and create the event handlers which implement the <xref:System.Windows.Input.RoutedCommand>.</span></span>  <span data-ttu-id="21164-105">有关命令的详细信息，请参阅 [命令概述](commanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="21164-105">For more information on commanding, see the [Commanding Overview](commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21164-106">示例</span><span class="sxs-lookup"><span data-stu-id="21164-106">Example</span></span>  
 <span data-ttu-id="21164-107">代码的第一部分创建 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] ，它包含 <xref:System.Windows.Controls.Button> 和 <xref:System.Windows.Controls.StackPanel> ，然后创建一个将 <xref:System.Windows.Input.CommandBinding> 命令处理程序与相关联的 <xref:System.Windows.Input.RoutedCommand> 。</span><span class="sxs-lookup"><span data-stu-id="21164-107">The first section of code creates the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], which consists of a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.StackPanel>, and creates a <xref:System.Windows.Input.CommandBinding> that associates the command handlers with the <xref:System.Windows.Input.RoutedCommand>.</span></span>  
  
 <span data-ttu-id="21164-108"><xref:System.Windows.Input.ICommandSource.Command%2A> <xref:System.Windows.Controls.Button> 与命令关联的的属性 <xref:System.Windows.Input.ApplicationCommands.Close%2A> 。</span><span class="sxs-lookup"><span data-stu-id="21164-108">The <xref:System.Windows.Input.ICommandSource.Command%2A> property of the <xref:System.Windows.Controls.Button> is associated with the <xref:System.Windows.Input.ApplicationCommands.Close%2A> command.</span></span>  
  
 <span data-ttu-id="21164-109">将 <xref:System.Windows.Input.CommandBinding> 添加到根的 <xref:System.Windows.Input.CommandBindingCollection> <xref:System.Windows.Window> 。</span><span class="sxs-lookup"><span data-stu-id="21164-109">The <xref:System.Windows.Input.CommandBinding> is added to the <xref:System.Windows.Input.CommandBindingCollection> of the root <xref:System.Windows.Window>.</span></span> <span data-ttu-id="21164-110"><xref:System.Windows.Input.CommandBinding.Executed>和 <xref:System.Windows.Input.CommandBinding.CanExecute> 事件处理程序附加到此绑定并与命令相关联 <xref:System.Windows.Input.ApplicationCommands.Close%2A> 。</span><span class="sxs-lookup"><span data-stu-id="21164-110">The <xref:System.Windows.Input.CommandBinding.Executed> and <xref:System.Windows.Input.CommandBinding.CanExecute> event handlers are attached to this binding and associated with the <xref:System.Windows.Input.ApplicationCommands.Close%2A> command.</span></span>  
  
 <span data-ttu-id="21164-111">如果没有 <xref:System.Windows.Input.CommandBinding> 命令逻辑，则只有一种调用命令的机制。</span><span class="sxs-lookup"><span data-stu-id="21164-111">Without the <xref:System.Windows.Input.CommandBinding> there is no command logic, only a mechanism to invoke the command.</span></span>  <span data-ttu-id="21164-112">当 <xref:System.Windows.Controls.Button> 单击时，将 <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> 在命令目标后引发，后跟 <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent> 。</span><span class="sxs-lookup"><span data-stu-id="21164-112">When the <xref:System.Windows.Controls.Button> is clicked, the <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> is raised on the command target followed by the <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.</span></span>  <span data-ttu-id="21164-113">这些事件遍历元素树 <xref:System.Windows.Input.CommandBinding> ，查找特定命令的。</span><span class="sxs-lookup"><span data-stu-id="21164-113">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for that particular command.</span></span>  <span data-ttu-id="21164-114">值得注意的是，由于 <xref:System.Windows.RoutedEvent> 通过元素树进行隧道和冒泡操作，因此必须小心谨慎 <xref:System.Windows.Input.CommandBinding> 。</span><span class="sxs-lookup"><span data-stu-id="21164-114">It is worth noting that because <xref:System.Windows.RoutedEvent> tunnel and bubble through the element tree, care must be taken in where the <xref:System.Windows.Input.CommandBinding> is put.</span></span>   <span data-ttu-id="21164-115">如果 <xref:System.Windows.Input.CommandBinding> 位于命令目标的同级上或不在的路由上的另一个节点上 <xref:System.Windows.RoutedEvent> ，则 <xref:System.Windows.Input.CommandBinding> 将不会访问。</span><span class="sxs-lookup"><span data-stu-id="21164-115">If the <xref:System.Windows.Input.CommandBinding> is on a sibling of the command target or another node that is not on the route of the <xref:System.Windows.RoutedEvent>, the <xref:System.Windows.Input.CommandBinding> will not be accessed.</span></span>  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 <span data-ttu-id="21164-116">下一部分代码实现了 <xref:System.Windows.Input.CommandManager.Executed> 和 <xref:System.Windows.Input.CommandBinding.CanExecute> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="21164-116">The next section of code implements the <xref:System.Windows.Input.CommandManager.Executed> and <xref:System.Windows.Input.CommandBinding.CanExecute> event handlers.</span></span>  
  
 <span data-ttu-id="21164-117"><xref:System.Windows.Input.CommandManager.Executed>处理程序将调用一个方法来关闭打开的文件。</span><span class="sxs-lookup"><span data-stu-id="21164-117">The <xref:System.Windows.Input.CommandManager.Executed> handler calls a method to close the open file.</span></span>  <span data-ttu-id="21164-118"><xref:System.Windows.Input.CommandBinding.CanExecute>处理程序调用方法来确定文件是否已打开。</span><span class="sxs-lookup"><span data-stu-id="21164-118">The <xref:System.Windows.Input.CommandBinding.CanExecute> handler calls a method to determine whether a file is open.</span></span>  <span data-ttu-id="21164-119">如果文件已打开， <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> 则将设置为 `true` ; 否则设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="21164-119">If a file is open, <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> is set to `true`; otherwise, it is set to `false`.</span></span>  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a><span data-ttu-id="21164-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21164-120">See also</span></span>

- [<span data-ttu-id="21164-121">命令概述</span><span class="sxs-lookup"><span data-stu-id="21164-121">Commanding Overview</span></span>](commanding-overview.md)
