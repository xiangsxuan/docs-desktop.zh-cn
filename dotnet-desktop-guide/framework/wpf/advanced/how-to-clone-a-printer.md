---
title: 如何：克隆打印机
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: e6af8d6410c4e383990bdaa27f97cc698be71719
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972838"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="a2176-102">如何：克隆打印机</span><span class="sxs-lookup"><span data-stu-id="a2176-102">How to: Clone a Printer</span></span>
<span data-ttu-id="a2176-103">在某些情况下，大多数企业会购买同一模型的多个打印机。</span><span class="sxs-lookup"><span data-stu-id="a2176-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="a2176-104">通常，这些都是以几乎完全相同的配置设置安装的。</span><span class="sxs-lookup"><span data-stu-id="a2176-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="a2176-105">安装每个打印机可能非常耗时且容易出错。</span><span class="sxs-lookup"><span data-stu-id="a2176-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="a2176-106"><xref:System.Printing.IndexedProperties?displayProperty=nameWithType>使用 Microsoft .NET 框架公开的命名空间和类，可以 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> 立即安装从现有打印队列克隆的任意数量的其他打印队列。</span><span class="sxs-lookup"><span data-stu-id="a2176-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2176-107">示例</span><span class="sxs-lookup"><span data-stu-id="a2176-107">Example</span></span>  
 <span data-ttu-id="a2176-108">在下面的示例中，第二个打印队列是从现有打印队列克隆的。</span><span class="sxs-lookup"><span data-stu-id="a2176-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="a2176-109">第二个仅在其名称、位置、端口和共享状态中不同于第一个。</span><span class="sxs-lookup"><span data-stu-id="a2176-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="a2176-110">执行此操作的主要步骤如下所示。</span><span class="sxs-lookup"><span data-stu-id="a2176-110">The major steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="a2176-111">为将要 <xref:System.Printing.PrintQueue> 克隆的现有打印机创建一个对象。</span><span class="sxs-lookup"><span data-stu-id="a2176-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2. <span data-ttu-id="a2176-112">从的创建一个 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> <xref:System.Printing.PrintQueue> 。</span><span class="sxs-lookup"><span data-stu-id="a2176-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="a2176-113"><xref:System.Collections.DictionaryEntry.Value%2A>此字典中的每个项的属性是从派生的类型之一的对象 <xref:System.Printing.IndexedProperties.PrintProperty> 。</span><span class="sxs-lookup"><span data-stu-id="a2176-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="a2176-114">可以通过两种方式设置此字典中的项的值。</span><span class="sxs-lookup"><span data-stu-id="a2176-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    - <span data-ttu-id="a2176-115">使用字典的 **删除** 和 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> 方法删除该条目，然后使用所需的值重新添加该条目。</span><span class="sxs-lookup"><span data-stu-id="a2176-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    - <span data-ttu-id="a2176-116">使用字典的 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="a2176-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="a2176-117">下面的示例演示了这两种方法。</span><span class="sxs-lookup"><span data-stu-id="a2176-117">The example below illustrates both ways.</span></span>  
  
3. <span data-ttu-id="a2176-118">创建一个 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 对象，并将其设置 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> 为 "IsShared"，并将其设置为 <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="a2176-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4. <span data-ttu-id="a2176-119">使用 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 对象作为 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> "IsShared" 项的值。</span><span class="sxs-lookup"><span data-stu-id="a2176-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5. <span data-ttu-id="a2176-120">创建一个 <xref:System.Printing.IndexedProperties.PrintStringProperty> 对象，并将其设置 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> 为 "共享名"，并将其设置 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> 为合适的 <xref:System.String> 。</span><span class="sxs-lookup"><span data-stu-id="a2176-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6. <span data-ttu-id="a2176-121">使用 <xref:System.Printing.IndexedProperties.PrintStringProperty> 对象作为 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> "共享名" 项的值。</span><span class="sxs-lookup"><span data-stu-id="a2176-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7. <span data-ttu-id="a2176-122">创建另一个 <xref:System.Printing.IndexedProperties.PrintStringProperty> 对象并将其设置 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> 为 "位置"，并将其设置 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> 为合适的 <xref:System.String> 。</span><span class="sxs-lookup"><span data-stu-id="a2176-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8. <span data-ttu-id="a2176-123">使用第二个 <xref:System.Printing.IndexedProperties.PrintStringProperty> 对象作为 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> "Location" 项的值。</span><span class="sxs-lookup"><span data-stu-id="a2176-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="a2176-124">创建的数组 <xref:System.String> 。</span><span class="sxs-lookup"><span data-stu-id="a2176-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="a2176-125">每个项都是服务器上的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="a2176-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="a2176-126">使用 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> 安装具有新值的新打印机。</span><span class="sxs-lookup"><span data-stu-id="a2176-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="a2176-127">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="a2176-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="a2176-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2176-128">See also</span></span>

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="a2176-129">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="a2176-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="a2176-130">打印概述</span><span class="sxs-lookup"><span data-stu-id="a2176-130">Printing Overview</span></span>](printing-overview.md)
