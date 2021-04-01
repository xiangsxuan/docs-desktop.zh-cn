---
title: 如何：确定此时是否可以打印一项打印作业
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print queues [WPF], timing
- printers [WPF], availability
- print jobs [WPF], timing
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
ms.openlocfilehash: 859dc75169e443d07361951692a428507886fa2e
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973491"
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>如何：确定此时是否可以打印一项打印作业
打印队列并非每日24小时始终可用。 它们具有 "开始时间" 和 "结束时间" 属性，可将其设置为在一天中的特定时间使其不可用。 例如，可以使用此功能在下午5点后预留打印机以供特定部门独占使用。 该部门与其他部门使用不同的队列来处理打印机。 其他部门的队列在下午5点后将被设置为不可用，而受欢迎部门的队列可设置为随时可用。  
  
 此外，打印作业本身可以设置为仅在指定的时间范围内可打印。  
  
 <xref:System.Printing.PrintQueue> <xref:System.Printing.PrintSystemJobInfo> 在 Microsoft .NET 框架的 api 中公开的和类提供一种远程检查给定的打印作业是否可以在指定的队列上打印的方法。  
  
## <a name="example"></a>示例  
 下面的示例是一个可诊断打印作业问题的示例。  
  
 下面是此类函数的两个主要步骤。  
  
1. 读取 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 的和 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 属性， <xref:System.Printing.PrintQueue> 以确定当前时间是否介于两者之间。  
  
2. 读取 <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> 的和 <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> 属性， <xref:System.Printing.PrintSystemJobInfo> 以确定当前时间是否介于两者之间。  
  
 但这种情况很复杂，这是因为这些属性不是 <xref:System.DateTime> 对象。 相反，它们是表示 <xref:System.Int32> 当天自午夜以来的时间间隔的对象。 此外，此时间不是当前时区的午夜，而是午夜 UTC (协调世界时) 。  
  
 第一个代码示例演示了 **ReportQueueAndJobAvailability** 的静态方法，该方法传递了 <xref:System.Printing.PrintSystemJobInfo> 并调用帮助程序方法来确定作业是否可以在当前时间打印，如果不能打印，则调用。 请注意， <xref:System.Printing.PrintQueue> 不会传递给方法。 这是因为在 <xref:System.Printing.PrintSystemJobInfo> 其属性中包含对队列的引用 <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> 。  
  
 从属方法包括重载的 **ReportAvailabilityAtThisTime** 方法，该方法可以采用 <xref:System.Printing.PrintQueue> 或 <xref:System.Printing.PrintSystemJobInfo> 作为参数。 还有一个 **TimeConverter。 ConvertToLocalHumanReadableTime**。 下面讨论所有这些方法。  
  
 **ReportQueueAndJobAvailability** 方法首先检查队列或打印作业此时是否不可用。 如果其中任何一个不可用，则它会检查队列是否不可用。 如果它不可用，则方法会报告此事实以及队列将再次变为可用的时间。 然后，它会检查作业，如果该作业不可用，它将在它可以打印时报告下一个时间跨度。 最后，该方法将报告作业可以打印的最早时间。 这是以下两次的后续版本。  
  
- 打印队列下一次可用的时间。  
  
- 打印作业下一次可用的时间。  
  
 报告当天的时间时， <xref:System.DateTime.ToShortTimeString%2A> 还会调用方法，因为此方法会取消输出的年、月和日。 不能将打印队列或打印作业的可用性限制为特定年、月或日。  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 除了传递给它们的类型外， **ReportAvailabilityAtThisTime** 方法的两个重载都是相同的，因此仅 <xref:System.Printing.PrintQueue> 下面提供版本。  
  
> [!NOTE]
> 除了类型外，方法是相同的，引发了示例不创建泛型方法 **ReportAvailabilityAtThisTime \<T>** 的问题。 原因在于，这种方法必须被限制为具有该方法所调用的 **StartTimeOfDay** 和 **system.printing.printqueue.untiltimeofday** 属性的类，但泛型方法只能限制为单一类，并且 <xref:System.Printing.PrintQueue> 在继承树中的唯一公共类没有 <xref:System.Printing.PrintSystemJobInfo> 此类 <xref:System.Printing.PrintSystemObject> 属性。  
  
 下面的代码示例中 (显示的 **ReportAvailabilityAtThisTime** 方法) 从 <xref:System.Boolean> 将 sentinel 变量初始化为开始 `true` 。 `false`如果队列不可用，它将重置为。  
  
 接下来，该方法将检查 "开始" 和 "结束" 时间是否相同。 如果是，则该队列始终可用，因此该方法返回 `true` 。  
  
 如果队列始终不可用，则该方法将使用静态 <xref:System.DateTime.UtcNow%2A> 属性获取当前时间作为 <xref:System.DateTime> 对象。  (我们不需要本地时间 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> ，因为和 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 属性本身是 UTC 时间。 )   
  
 但是，这两个属性不是 <xref:System.DateTime> 对象。 它们将 <xref:System.Int32> 时间表示为 UTC 时间之后的分钟数。 因此，我们必须将对象转换 <xref:System.DateTime> 为午夜后的分钟数。 完成此操作后，该方法只需检查 "现在" 是否在队列的 "开始" 和 "结束" 时间之间，如果 "now" 不在两个时间之间，则将 "sentinel" 设置为 "false"，并返回 sentinel。  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 下面的代码示例中 (提供的 **ConvertToLocalHumanReadableTime** 方法) 不使用 Microsoft .NET 框架引入的任何方法，因此讨论很简单。 方法具有双重转换任务：它必须采用一个整数，表示午夜后的分钟数，并将其转换为可读的时间，并且必须将其转换为本地时间。 它通过首先创建一个 <xref:System.DateTime> 设置为午夜 UTC 的对象来完成此工作，然后使用 <xref:System.DateTime.AddMinutes%2A> 方法来添加已传递给方法的分钟数。 这会返回一个新的， <xref:System.DateTime> 表示传递给方法的初始时间。 <xref:System.DateTime.ToLocalTime%2A>然后，方法将此转换为本地时间。  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.DateTime>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.Printing.PrintQueue>
- [WPF 中的文档](documents-in-wpf.md)
- [打印概述](printing-overview.md)
