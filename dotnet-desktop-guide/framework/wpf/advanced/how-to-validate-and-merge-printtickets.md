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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973740"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="c3827-102">如何：验证和合并 PrintTicket</span><span class="sxs-lookup"><span data-stu-id="c3827-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="c3827-103">Microsoft Windows [打印架构](/windows/win32/printdocs/printschema) 包括灵活且可扩展的 <xref:System.Printing.PrintCapabilities> 和 <xref:System.Printing.PrintTicket> 元素。</span><span class="sxs-lookup"><span data-stu-id="c3827-103">The Microsoft Windows [Print Schema](/windows/win32/printdocs/printschema) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="c3827-104">前者列举打印设备的功能，后者指定设备应该如何根据特定的文档序列、单个文档或单个页面使用这些功能。</span><span class="sxs-lookup"><span data-stu-id="c3827-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="c3827-105">支持打印的应用程序的典型任务序列如下所示。</span><span class="sxs-lookup"><span data-stu-id="c3827-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="c3827-106">确定打印机的功能。</span><span class="sxs-lookup"><span data-stu-id="c3827-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="c3827-107">配置 <xref:System.Printing.PrintTicket> 以使用这些功能。</span><span class="sxs-lookup"><span data-stu-id="c3827-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="c3827-108">验证 <xref:System.Printing.PrintTicket> 。</span><span class="sxs-lookup"><span data-stu-id="c3827-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="c3827-109">本文说明如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c3827-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3827-110">示例</span><span class="sxs-lookup"><span data-stu-id="c3827-110">Example</span></span>  
 <span data-ttu-id="c3827-111">在下面的简单示例中，仅对打印机是否可以支持双面打印感兴趣。</span><span class="sxs-lookup"><span data-stu-id="c3827-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="c3827-112">主要步骤如下所示。</span><span class="sxs-lookup"><span data-stu-id="c3827-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="c3827-113"><xref:System.Printing.PrintCapabilities>使用方法获取一个对象 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c3827-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="c3827-114">测试所需功能是否存在。</span><span class="sxs-lookup"><span data-stu-id="c3827-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="c3827-115">在下面的示例中，我们将 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 对对象的属性进行测试， <xref:System.Printing.PrintCapabilities> 以了解在纸张的两面上是否存在打印的功能以及纸张的长边。</span><span class="sxs-lookup"><span data-stu-id="c3827-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="c3827-116">由于 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 是集合，因此使用的 `Contains` 方法 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 。</span><span class="sxs-lookup"><span data-stu-id="c3827-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c3827-117">此步骤并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="c3827-117">This step is not strictly necessary.</span></span> <span data-ttu-id="c3827-118"><xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>下面使用的方法将针对打印机的功能检查中的每个请求 <xref:System.Printing.PrintTicket> 。</span><span class="sxs-lookup"><span data-stu-id="c3827-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="c3827-119">如果打印机不支持所请求的功能，打印机驱动程序将用方法返回的中的替代请求 <xref:System.Printing.PrintTicket> 。</span><span class="sxs-lookup"><span data-stu-id="c3827-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="c3827-120">如果打印机支持双工，则示例代码会创建一个 <xref:System.Printing.PrintTicket> 请求双面打印的。</span><span class="sxs-lookup"><span data-stu-id="c3827-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="c3827-121">但应用程序不会指定元素中提供的每个可能的打印机设置 <xref:System.Printing.PrintTicket> 。</span><span class="sxs-lookup"><span data-stu-id="c3827-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="c3827-122">这会浪费程序员和计划时间。</span><span class="sxs-lookup"><span data-stu-id="c3827-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="c3827-123">相反，代码仅设置双工请求，然后将 <xref:System.Printing.PrintTicket> 其与现有的、完全配置和验证的（ <xref:System.Printing.PrintTicket> 在本例中为用户的默认值）合并 <xref:System.Printing.PrintTicket> 。</span><span class="sxs-lookup"><span data-stu-id="c3827-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="c3827-124">相应地，该示例调用 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 方法，以将新的最小 <xref:System.Printing.PrintTicket> 值与用户的默认值合并 <xref:System.Printing.PrintTicket> 。</span><span class="sxs-lookup"><span data-stu-id="c3827-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="c3827-125">这会返回 <xref:System.Printing.ValidationResult> ，其中包含新的 <xref:System.Printing.PrintTicket> 作为其属性之一。</span><span class="sxs-lookup"><span data-stu-id="c3827-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="c3827-126">然后，该示例测试新请求是否为 <xref:System.Printing.PrintTicket> 双工。</span><span class="sxs-lookup"><span data-stu-id="c3827-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="c3827-127">如果是这样，则示例将使其成为用户的新默认打印票证。</span><span class="sxs-lookup"><span data-stu-id="c3827-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="c3827-128">如果上面的步骤2已省略，并且打印机不支持沿长边进行双面打印，则测试将导致 `false` 。</span><span class="sxs-lookup"><span data-stu-id="c3827-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="c3827-129"> (参见上面的说明。 ) </span><span class="sxs-lookup"><span data-stu-id="c3827-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="c3827-130">最后一个重要步骤是将对的属性的更改提交到 <xref:System.Printing.PrintQueue.UserPrintTicket%2A> <xref:System.Printing.PrintQueue> <xref:System.Printing.PrintQueue.Commit%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="c3827-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="c3827-131">因此，你可以快速测试此示例，下面提供了它的其余部分。</span><span class="sxs-lookup"><span data-stu-id="c3827-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="c3827-132">创建项目和命名空间，然后将本文中的代码片段粘贴到命名空间块。</span><span class="sxs-lookup"><span data-stu-id="c3827-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="c3827-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3827-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="c3827-134">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="c3827-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="c3827-135">打印概述</span><span class="sxs-lookup"><span data-stu-id="c3827-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="c3827-136">打印架构</span><span class="sxs-lookup"><span data-stu-id="c3827-136">Print Schema</span></span>](/windows/win32/printdocs/printschema)
