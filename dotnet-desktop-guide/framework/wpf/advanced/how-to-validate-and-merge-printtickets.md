---
title: 如何：验证和合并 PrintTicket
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: bd7f399555b343a52ec6f36aa3b8c706747d8b06
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973740"
---
# <a name="how-to-validate-and-merge-printtickets"></a>如何：验证和合并 PrintTicket
Microsoft Windows [打印架构](/windows/win32/printdocs/printschema) 包括灵活且可扩展的 <xref:System.Printing.PrintCapabilities> 和 <xref:System.Printing.PrintTicket> 元素。 前者列举打印设备的功能，后者指定设备应该如何根据特定的文档序列、单个文档或单个页面使用这些功能。  
  
 支持打印的应用程序的典型任务序列如下所示。  
  
1. 确定打印机的功能。  
  
2. 配置 <xref:System.Printing.PrintTicket> 以使用这些功能。  
  
3. 验证 <xref:System.Printing.PrintTicket> 。  
  
 本文说明如何执行此操作。  
  
## <a name="example"></a>示例  
 在下面的简单示例中，仅对打印机是否可以支持双面打印感兴趣。 主要步骤如下所示。  
  
1. <xref:System.Printing.PrintCapabilities>使用方法获取一个对象 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 。  
  
2. 测试所需功能是否存在。 在下面的示例中，我们将 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 对对象的属性进行测试， <xref:System.Printing.PrintCapabilities> 以了解在纸张的两面上是否存在打印的功能以及纸张的长边。 由于 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 是集合，因此使用的 `Contains` 方法 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 。  
  
    > [!NOTE]
    > 此步骤并不是必需的。 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>下面使用的方法将针对打印机的功能检查中的每个请求 <xref:System.Printing.PrintTicket> 。 如果打印机不支持所请求的功能，打印机驱动程序将用方法返回的中的替代请求 <xref:System.Printing.PrintTicket> 。  
  
3. 如果打印机支持双工，则示例代码会创建一个 <xref:System.Printing.PrintTicket> 请求双面打印的。 但应用程序不会指定元素中提供的每个可能的打印机设置 <xref:System.Printing.PrintTicket> 。 这会浪费程序员和计划时间。 相反，代码仅设置双工请求，然后将 <xref:System.Printing.PrintTicket> 其与现有的、完全配置和验证的（ <xref:System.Printing.PrintTicket> 在本例中为用户的默认值）合并 <xref:System.Printing.PrintTicket> 。  
  
4. 相应地，该示例调用 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 方法，以将新的最小 <xref:System.Printing.PrintTicket> 值与用户的默认值合并 <xref:System.Printing.PrintTicket> 。 这会返回 <xref:System.Printing.ValidationResult> ，其中包含新的 <xref:System.Printing.PrintTicket> 作为其属性之一。  
  
5. 然后，该示例测试新请求是否为 <xref:System.Printing.PrintTicket> 双工。 如果是这样，则示例将使其成为用户的新默认打印票证。 如果上面的步骤2已省略，并且打印机不支持沿长边进行双面打印，则测试将导致 `false` 。  (参见上面的说明。 )   
  
6. 最后一个重要步骤是将对的属性的更改提交到 <xref:System.Printing.PrintQueue.UserPrintTicket%2A> <xref:System.Printing.PrintQueue> <xref:System.Printing.PrintQueue.Commit%2A> 方法。  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 因此，你可以快速测试此示例，下面提供了它的其余部分。 创建项目和命名空间，然后将本文中的代码片段粘贴到命名空间块。  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [WPF 中的文档](documents-in-wpf.md)
- [打印概述](printing-overview.md)
- [打印架构](/windows/win32/printdocs/printschema)
