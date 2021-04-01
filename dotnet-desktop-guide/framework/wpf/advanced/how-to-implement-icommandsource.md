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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972584"
---
# <a name="how-to-implement-icommandsource"></a>如何：实现 ICommandSource

此示例演示如何通过实现来创建命令源 <xref:System.Windows.Input.ICommandSource> 。 命令源是一个知道如何调用命令的对象。 <xref:System.Windows.Input.ICommandSource>接口公开三个成员：

- <xref:System.Windows.Input.ICommandSource.Command%2A>：要调用的命令。
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>：用户定义数据类型，它从命令源传递到处理命令的方法。
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>：在其上执行命令的对象。

在此示例中，创建了从 <xref:System.Windows.Controls.Slider> 控件继承并实现接口的类  <xref:System.Windows.Input.ICommandSource> 。
  
## <a name="example"></a>示例

WPF 提供了许多实现的类 <xref:System.Windows.Input.ICommandSource> ，例如、 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.MenuItem> 和 <xref:System.Windows.Documents.Hyperlink> 。 命令源定义它调用命令的方式。 这些类在被单击时调用一个命令，在设置其属性时，它们只能成为命令源 <xref:System.Windows.Input.ICommandSource.Command%2A> 。

在此示例中，你将在移动滑块时或者更准确地在更改属性时调用该命令 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 。

下面是类定义：

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

下一步是实现 <xref:System.Windows.Input.ICommandSource> 成员。 在此示例中，属性实现为 <xref:System.Windows.DependencyProperty> 对象。 这使属性能够使用数据绑定。 有关类的详细信息 <xref:System.Windows.DependencyProperty> ，请参阅 [依赖属性概述](dependency-properties-overview.md)。 有关数据绑定的详细信息，请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。

此处仅 <xref:System.Windows.Input.ICommandSource.Command%2A> 显示属性。

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
下面是 <xref:System.Windows.DependencyProperty> 更改回调：

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

下一步是添加和删除与命令源关联的命令。 <xref:System.Windows.Input.ICommandSource.Command%2A>添加新命令时，属性不能简单覆盖，因为与前一个命令相关联的事件处理程序（如果有）必须先删除。

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

下一步是创建处理程序的逻辑 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 。

此 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 事件通知命令源，对当前命令目标执行的命令的功能可能已更改。 当命令源收到此事件时，它通常会对 <xref:System.Windows.Input.ICommand.CanExecute%2A> 命令调用方法。 如果无法对当前命令目标执行该命令，则命令源通常会禁用自身。 如果命令可在当前命令目标上执行，则命令源通常会自行启用。

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

最后一步是 <xref:System.Windows.Input.ICommand.Execute%2A> 方法。 如果命令为，则 <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> 调用方法; 否则，将 <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> 调用方法。

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [命令概述](commanding-overview.md)
