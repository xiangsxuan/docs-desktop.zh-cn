---
title: 如何：远程调查打印机的状态
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
ms.openlocfilehash: 94390b0660afce6af38c7ed6da6174f5425802c1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971501"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>如何：远程调查打印机的状态
在大中型公司，在任何给定时间里，都可能发生由于卡纸、纸张用完或某些其他有问题而导致多台打印机无法工作的情况。 Microsoft .NET 框架的 Api 中公开的一组丰富的打印机属性提供了一种快速调查打印机状态的方法。  
  
## <a name="example"></a>示例  
 以下是创建此类实用程序的主要步骤。  
  
1. 获取所有打印服务器的列表。  
  
2. 循环访问服务器以查询其打印队列。  
  
3. 在每一轮服务器循环访问过程中，循环访问所有服务器的队列并读取每个属性，这些属性可能指示队列当前不在工作。  
  
 以下代码是一系列代码段。 为简单起见，本示例假定存在通过 CRLF 分隔的打印服务器列表。 变量 `fileOfPrintServers` 是 <xref:System.IO.StreamReader> 此文件的对象。 由于每个服务器名称都在其自己的行上，因此的任何调用都将 <xref:System.IO.StreamReader.ReadLine%2A> 获取下一个服务器的名称，并将 <xref:System.IO.StreamReader> 的光标移到下一行的开头。  
  
 在外部循环中，代码 <xref:System.Printing.PrintServer> 为最新的打印服务器创建一个对象，并指定该应用程序将具有对服务器的管理权限。  
  
> [!NOTE]
> 如果有大量服务器，则可以使用 <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> 只初始化需要的属性的构造函数来提高性能。  
  
 然后，该示例使用 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 创建服务器的所有队列的集合，并开始循环遍历它们。 此内部循环包含一个分支结构，该结构对应于检查打印机状态的两种方法：  
  
- 您可以读取 <xref:System.Printing.PrintQueue.QueueStatus%2A> 类型为的属性的标志 <xref:System.Printing.PrintQueueStatus> 。  
  
- 您可以读取每个相关属性 <xref:System.Printing.PrintQueue.IsOutOfPaper%2A> ，例如、和 <xref:System.Printing.PrintQueue.IsPaperJammed%2A> 。  
  
 此示例演示了这两种方法，因此，如果用户想要使用属性的标志，则以前会提示用户要使用哪种方法并使用 "y" 做出响应 <xref:System.Printing.PrintQueue.QueueStatus%2A> 。 请参阅以下有关这两种方法的详细信息。  
  
 最后，会向用户显示结果。  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 若要使用属性的标志来检查打印机状态 <xref:System.Printing.PrintQueue.QueueStatus%2A> ，请检查每个相关标志是否已设置。 检查是否在一组位标志中设置了一个位的标准方法是执行一个逻辑 AND 运算，其中将该组标志作为一个操作数，将标志本身作为另一操作数。 由于该标志本身仅设置一个位，因此逻辑 AND 的结果至多为设置了该相同位。 若要查明事实是否如此，只需将逻辑 AND 的结果与标志本身进行比较。 有关详细信息，请参阅 <xref:System.Printing.PrintQueueStatus> [& 运算符 (c # 参考) ](/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#logical-and-operator-)和 <xref:System.FlagsAttribute> 。  
  
 对于已设置了其位的各个特性，代码会将一条通知添加到将向用户显示的最终报告中。 （下面会讨论代码结束时调用的 **ReportAvailabilityAtThisTime** 方法。）  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 若要使用各个属性检查打印机状态，只需读取各个属性，并将注释添加到最终报告，如果属性为 `true`，将向用户显示最终报告。 （下面会讨论代码结束时调用的 **ReportAvailabilityAtThisTime** 方法。）  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 创建了 **ReportAvailabilityAtThisTime** 方法，以应对需要确定队列在一天的当前时间是否可用的情况。  
  
 如果和属性相等，则方法将不执行任何操作 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> ; 因为在这种情况下，打印机始终可用。 如果它们不同，则方法获取当前时间，该时间之后必须转换为午夜的总分钟数，因为 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 和 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 属性 <xref:System.Int32> 表示午夜后的分钟数（而不是 <xref:System.DateTime> 对象）。 最后，该方法会检查当前时间是否介于开始时间和“截至”时间之间。  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>
- <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>
- <xref:System.DateTime>
- <xref:System.Printing.PrintQueueStatus>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- [& 运算符 (c # 参考) ](/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#logical-and-operator-)
- [WPF 中的文档](documents-in-wpf.md)
- [打印概述](printing-overview.md)
