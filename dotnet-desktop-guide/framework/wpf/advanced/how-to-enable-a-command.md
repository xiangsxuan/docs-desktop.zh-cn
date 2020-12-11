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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973452"
---
# <a name="how-to-enable-a-command"></a>如何：启用命令
下面的示例演示如何在中使用命令 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。  该示例演示如何将与关联 <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Controls.Button> ，创建 <xref:System.Windows.Input.CommandBinding> ，并创建实现的事件处理程序 <xref:System.Windows.Input.RoutedCommand> 。  有关命令的详细信息，请参阅 [命令概述](commanding-overview.md)。  
  
## <a name="example"></a>示例  
 代码的第一部分创建 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] ，它包含 <xref:System.Windows.Controls.Button> 和 <xref:System.Windows.Controls.StackPanel> ，然后创建一个将 <xref:System.Windows.Input.CommandBinding> 命令处理程序与相关联的 <xref:System.Windows.Input.RoutedCommand> 。  
  
 <xref:System.Windows.Input.ICommandSource.Command%2A> <xref:System.Windows.Controls.Button> 与命令关联的的属性 <xref:System.Windows.Input.ApplicationCommands.Close%2A> 。  
  
 将 <xref:System.Windows.Input.CommandBinding> 添加到根的 <xref:System.Windows.Input.CommandBindingCollection> <xref:System.Windows.Window> 。 <xref:System.Windows.Input.CommandBinding.Executed>和 <xref:System.Windows.Input.CommandBinding.CanExecute> 事件处理程序附加到此绑定并与命令相关联 <xref:System.Windows.Input.ApplicationCommands.Close%2A> 。  
  
 如果没有 <xref:System.Windows.Input.CommandBinding> 命令逻辑，则只有一种调用命令的机制。  当 <xref:System.Windows.Controls.Button> 单击时，将 <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> 在命令目标后引发，后跟 <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent> 。  这些事件遍历元素树 <xref:System.Windows.Input.CommandBinding> ，查找特定命令的。  值得注意的是，由于 <xref:System.Windows.RoutedEvent> 通过元素树进行隧道和冒泡操作，因此必须小心谨慎 <xref:System.Windows.Input.CommandBinding> 。   如果 <xref:System.Windows.Input.CommandBinding> 位于命令目标的同级上或不在的路由上的另一个节点上 <xref:System.Windows.RoutedEvent> ，则 <xref:System.Windows.Input.CommandBinding> 将不会访问。  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 下一部分代码实现了 <xref:System.Windows.Input.CommandManager.Executed> 和 <xref:System.Windows.Input.CommandBinding.CanExecute> 事件处理程序。  
  
 <xref:System.Windows.Input.CommandManager.Executed>处理程序将调用一个方法来关闭打开的文件。  <xref:System.Windows.Input.CommandBinding.CanExecute>处理程序调用方法来确定文件是否已打开。  如果文件已打开， <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> 则将设置为 `true` ; 否则设置为 `false` 。  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a>另请参阅

- [命令概述](commanding-overview.md)
