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
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="20b4f-102">如何：枚举打印队列的子集</span><span class="sxs-lookup"><span data-stu-id="20b4f-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="20b4f-103">信息技术面临的一种常见情况是， (IT) 专业人员管理公司范围内的打印机，就是生成具有特定特征的打印机的列表。</span><span class="sxs-lookup"><span data-stu-id="20b4f-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="20b4f-104">此功能由 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 对象的方法 <xref:System.Printing.PrintServer> 和枚举提供 <xref:System.Printing.EnumeratedPrintQueueTypes> 。</span><span class="sxs-lookup"><span data-stu-id="20b4f-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20b4f-105">示例</span><span class="sxs-lookup"><span data-stu-id="20b4f-105">Example</span></span>  
 <span data-ttu-id="20b4f-106">在下面的示例中，代码首先创建一个标志数组，用于指定要列出的打印队列的特性。</span><span class="sxs-lookup"><span data-stu-id="20b4f-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="20b4f-107">在此示例中，我们将查找在打印服务器上本地安装并共享的打印队列。</span><span class="sxs-lookup"><span data-stu-id="20b4f-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="20b4f-108"><xref:System.Printing.EnumeratedPrintQueueTypes>枚举提供了许多其他可能性。</span><span class="sxs-lookup"><span data-stu-id="20b4f-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="20b4f-109">然后，该代码将创建一个 <xref:System.Printing.LocalPrintServer> 对象，该对象是一个派生自的类 <xref:System.Printing.PrintServer> 。</span><span class="sxs-lookup"><span data-stu-id="20b4f-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="20b4f-110">本地打印服务器是在其上运行应用程序的计算机。</span><span class="sxs-lookup"><span data-stu-id="20b4f-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="20b4f-111">最后一个重要步骤是将数组传递给 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="20b4f-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="20b4f-112">最后，会向用户显示结果。</span><span class="sxs-lookup"><span data-stu-id="20b4f-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="20b4f-113">您可以通过使 `foreach` 每个打印队列步骤逐步进行筛选的循环来扩展此示例。</span><span class="sxs-lookup"><span data-stu-id="20b4f-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="20b4f-114">例如，您可以通过循环调用每个打印队列的 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 方法，并测试是否存在双工的返回值，来使不支持双面打印的打印机出现。</span><span class="sxs-lookup"><span data-stu-id="20b4f-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b4f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="20b4f-115">See also</span></span>

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="20b4f-116">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="20b4f-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="20b4f-117">打印概述</span><span class="sxs-lookup"><span data-stu-id="20b4f-117">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="20b4f-118">Microsoft XPS 文档编写器</span><span class="sxs-lookup"><span data-stu-id="20b4f-118">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
