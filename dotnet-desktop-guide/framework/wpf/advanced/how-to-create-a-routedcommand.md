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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973455"
---
# <a name="how-to-create-a-routedcommand"></a>如何：创建 RoutedCommand
此示例演示如何创建自定义 <xref:System.Windows.Input.RoutedCommand> ，以及如何通过创建 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 和 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 并将其附加到来实现自定义命令 <xref:System.Windows.Input.CommandBinding> 。  有关命令的详细信息，请参阅 [命令概述](commanding-overview.md)。  
  
## <a name="example"></a>示例  
 创建的第一步 <xref:System.Windows.Input.RoutedCommand> 是定义并对其进行实例化。  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 若要在应用程序中使用命令，必须创建用于定义命令执行的操作的事件处理程序  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 接下来，  <xref:System.Windows.Input.CommandBinding> 创建一个将命令与事件处理程序相关联的。 在 <xref:System.Windows.Input.CommandBinding> 特定对象上创建。  此对象 <xref:System.Windows.Input.CommandBinding> 在元素树中定义的范围  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 最后一步是调用命令。  调用命令的一种方法是将其与相关联 <xref:System.Windows.Input.ICommandSource> ，例如 <xref:System.Windows.Controls.Button> 。  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 单击该按钮时，将 <xref:System.Windows.Input.RoutedCommand.Execute%2A> 调用自定义的方法 <xref:System.Windows.Input.RoutedCommand> 。  <xref:System.Windows.Input.RoutedCommand>引发 <xref:System.Windows.Input.CommandManager.PreviewExecuted> 和 <xref:System.Windows.Input.CommandManager.Executed> 路由事件。  这些事件遍历元素树， <xref:System.Windows.Input.CommandBinding> 以便查找此特定命令的。  如果 <xref:System.Windows.Input.CommandBinding> 找到，则 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 调用与关联的 <xref:System.Windows.Input.CommandBinding> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Input.RoutedCommand>
- [命令概述](commanding-overview.md)
