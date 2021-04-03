---
title: 如何：枚举打印队列的子集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: aae41931f012f6d34fc057fdd6ee9fc9baab6e7b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973447"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>如何：枚举打印队列的子集
信息技术面临的一种常见情况是， (IT) 专业人员管理公司范围内的打印机，就是生成具有特定特征的打印机的列表。 此功能由 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 对象的方法 <xref:System.Printing.PrintServer> 和枚举提供 <xref:System.Printing.EnumeratedPrintQueueTypes> 。  
  
## <a name="example"></a>示例  
 在下面的示例中，代码首先创建一个标志数组，用于指定要列出的打印队列的特性。 在此示例中，我们将查找在打印服务器上本地安装并共享的打印队列。 <xref:System.Printing.EnumeratedPrintQueueTypes>枚举提供了许多其他可能性。  
  
 然后，该代码将创建一个 <xref:System.Printing.LocalPrintServer> 对象，该对象是一个派生自的类 <xref:System.Printing.PrintServer> 。 本地打印服务器是在其上运行应用程序的计算机。  
  
 最后一个重要步骤是将数组传递给 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 方法。  
  
 最后，会向用户显示结果。  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 您可以通过使 `foreach` 每个打印队列步骤逐步进行筛选的循环来扩展此示例。 例如，您可以通过循环调用每个打印队列的 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 方法，并测试是否存在双工的返回值，来使不支持双面打印的打印机出现。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [WPF 中的文档](documents-in-wpf.md)
- [打印概述](printing-overview.md)
- [Microsoft XPS 文档编写器](/windows/win32/printdocs/microsoft-xps-document-writer)
