---
title: 如何：诊断有问题的打印作业
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- troubleshooting print job problems [WPF]
- print jobs [WPF], troubleshooting
- print jobs [WPF], diagnosing problems
ms.assetid: b081a170-84c6-48f9-a487-5766a8d58a82
ms.openlocfilehash: ce79818b16824969ef0bd2a9c8adfd7ca094cec0
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970597"
---
# <a name="how-to-diagnose-problematic-print-job"></a>如何：诊断有问题的打印作业
网络管理员经常接收到有关打印作业无法打印或打印速度慢的用户投诉。 Microsoft .NET 框架的 Api 中公开的一组丰富的打印作业属性提供了一种快速远程诊断打印作业的方法。  
  
## <a name="example"></a>示例  
 以下是创建此类实用程序的主要步骤。  
  
1. 标识用户投诉的打印作业。 用户通常无法准确完成此操作。 他们可能不知道打印服务器或打印机的名称。 它们可能会描述打印机的位置，而不是在设置其属性时使用的术语 <xref:System.Printing.PrintQueue.Location%2A> 。 这样的话，一个好办法是生成用户当前所提交作业的列表。 如果存在多个作业，则可通过用户和打印系统管理员之间的通信来查明出现问题的作业。 子步骤如下。  
  
    1. 获取所有打印服务器的列表。  
  
    2. 循环访问服务器以查询其打印队列。  
  
    3. 在每一轮服务器循环访问过程中，循环访问所有服务器的队列，以查询其作业  
  
    4. 在每一轮服务器循环访问过程中，循环访问其作业，并收集与投诉用户已提交的作业相关的标识信息。  
  
2. 当已识别有问题的打印作业时，检查相关属性以查明可能的问题。 例如，作业是否处于错误状态，或服务于队列的打印机是否在打印该作业之前处于脱机状态？  
  
 以下代码是一系列代码示例。 第一个代码示例包含针对打印队列的循环访问操作。  (以上步骤1c。 ) 变量 `myPrintQueues` 是 <xref:System.Printing.PrintQueueCollection> 当前打印服务器的对象。  
  
 此代码示例通过使用刷新当前打印队列对象开始 <xref:System.Printing.PrintQueue.Refresh%2A?displayProperty=nameWithType> 。 这可确保该对象的属性能够准确表示它所表示的物理打印机的状态。 然后，应用程序通过使用获取打印队列中当前的打印作业的集合 <xref:System.Printing.PrintQueue.GetPrintJobInfoCollection%2A> 。  
  
 接下来，应用程序循环遍历该 <xref:System.Printing.PrintSystemJobInfo> 集合，并将每个 <xref:System.Printing.PrintSystemJobInfo.Submitter%2A> 属性与抱怨用户的别名进行比较。 如果属性和别名相匹配，则应用程序会将有关该作业的标识信息添加到将呈现的字符串。 （`userName` 和 `jobList` 变量在应用程序早期进行初始化。）  
  
 [!code-cpp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#enumeratejobsinqueues)]
 [!code-csharp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#enumeratejobsinqueues)]
 [!code-vb[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#enumeratejobsinqueues)]  
  
 下一代码示例在步骤 2 提取应用程序。  (参见上文。 ) 已确定有问题的作业，并且应用程序提示输入将标识该作业的信息。 通过此信息，它将创建 <xref:System.Printing.PrintServer> 、 <xref:System.Printing.PrintQueue> 和 <xref:System.Printing.PrintSystemJobInfo> 对象。  
  
 此时，应用程序包含一个分支结构，该结构对应于检查打印作业状态的两种方法：  
  
- 您可以读取 <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> 类型为的属性的标志 <xref:System.Printing.PrintJobStatus> 。  
  
- 您可以读取每个相关属性 <xref:System.Printing.PrintSystemJobInfo.IsBlocked%2A> ，例如和 <xref:System.Printing.PrintSystemJobInfo.IsInError%2A> 。  
  
 此示例演示了这两种方法，因此，如果用户想要使用属性的标志，则以前会提示用户要使用哪种方法并使用 "Y" 做出响应 <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> 。 请参阅以下有关这两种方法的详细信息。 最后，该应用程序使用一种名为 **ReportQueueAndJobAvailability** 的方法来报告是否可以在一天的此时打印该作业。 [确定此时是否可以打印一项打印作业](how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day.md)中就此方法进行了讨论。  
  
 [!code-cpp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#identifyanddiagnoseproblematicjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#identifyanddiagnoseproblematicjob)]
 [!code-vb[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#identifyanddiagnoseproblematicjob)]  
  
 若要使用属性的标志来检查打印作业状态 <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> ，请检查每个相关标志是否已设置。 检查是否在一组位标志中设置了一个位的标准方法是执行一个逻辑 AND 运算，其中将该组标志作为一个操作数，将标志本身作为另一操作数。 由于该标志本身仅设置一个位，因此逻辑 AND 的结果至多为设置了该相同位。 若要查明事实是否如此，只需将逻辑 AND 的结果与标志本身进行比较。 有关详细信息，请参阅 <xref:System.Printing.PrintJobStatus> [& 运算符 (c # 参考) ](/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#logical-and-operator-)和 <xref:System.FlagsAttribute> 。  
  
 对于已设置了其位的每个属性，代码会将此报告给控制台屏幕，有时还会建议如何响应。 （下面讨论了作业或队列暂停时所调用的 **HandlePausedJob** 方法。）  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobattributes)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobattributes)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobattributes)]  
  
 若要使用单独的属性检查打印作业状态，只需读取每个属性，如果属性为 `true`，则报告给控制台屏幕，并建议一种可能的响应方式。 （下面讨论了作业或队列暂停时所调用的 **HandlePausedJob** 方法。）  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobproperties)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobproperties)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobproperties)]  
  
 使用 **HandlePausedJob** 方法，应用程序的用户能够远程恢复暂停的作业。 由于可能存在一个充分的暂停打印队列的理由，因此该方法会首先提示用户是否确实要恢复该作业。 如果回答是 "Y"，则 <xref:System.Printing.PrintQueue.Resume%2A?displayProperty=nameWithType> 调用方法。  
  
 接下来，系统会提示用户是否确实要继续执行作业，这么做是考虑到这个作业可能是独立于队列中的其他作业被单独暂停的。  (比较 <xref:System.Printing.PrintQueue.IsPaused%2A?displayProperty=nameWithType> 和 <xref:System.Printing.PrintSystemJobInfo.IsPaused%2A?displayProperty=nameWithType> 。 ) 如果答案是 "Y"，则 <xref:System.Printing.PrintSystemJobInfo.Resume%2A?displayProperty=nameWithType> 调用; 否则 <xref:System.Printing.PrintSystemJobInfo.Cancel%2A> ，将调用。  
  
 [!code-cpp[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#handlepausedjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#handlepausedjob)]
 [!code-vb[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#handlepausedjob)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Printing.PrintJobStatus>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintQueue>
- [& 运算符 (c # 参考) ](/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#logical-and-operator-)
- [WPF 中的文档](documents-in-wpf.md)
- [打印概述](printing-overview.md)
