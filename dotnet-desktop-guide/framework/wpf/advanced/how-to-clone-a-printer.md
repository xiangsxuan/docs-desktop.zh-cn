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
# <a name="how-to-clone-a-printer"></a>如何：克隆打印机
在某些情况下，大多数企业会购买同一模型的多个打印机。 通常，这些都是以几乎完全相同的配置设置安装的。 安装每个打印机可能非常耗时且容易出错。 <xref:System.Printing.IndexedProperties?displayProperty=nameWithType>使用 Microsoft .NET 框架公开的命名空间和类，可以 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> 立即安装从现有打印队列克隆的任意数量的其他打印队列。  
  
## <a name="example"></a>示例  
 在下面的示例中，第二个打印队列是从现有打印队列克隆的。 第二个仅在其名称、位置、端口和共享状态中不同于第一个。 执行此操作的主要步骤如下所示。  
  
1. 为将要 <xref:System.Printing.PrintQueue> 克隆的现有打印机创建一个对象。  
  
2. 从的创建一个 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> <xref:System.Printing.PrintQueue> 。 <xref:System.Collections.DictionaryEntry.Value%2A>此字典中的每个项的属性是从派生的类型之一的对象 <xref:System.Printing.IndexedProperties.PrintProperty> 。 可以通过两种方式设置此字典中的项的值。  
  
    - 使用字典的 **删除** 和 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> 方法删除该条目，然后使用所需的值重新添加该条目。  
  
    - 使用字典的 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> 方法。  
  
     下面的示例演示了这两种方法。  
  
3. 创建一个 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 对象，并将其设置 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> 为 "IsShared"，并将其设置为 <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> `true` 。  
  
4. 使用 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 对象作为 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> "IsShared" 项的值。  
  
5. 创建一个 <xref:System.Printing.IndexedProperties.PrintStringProperty> 对象，并将其设置 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> 为 "共享名"，并将其设置 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> 为合适的 <xref:System.String> 。  
  
6. 使用 <xref:System.Printing.IndexedProperties.PrintStringProperty> 对象作为 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> "共享名" 项的值。  
  
7. 创建另一个 <xref:System.Printing.IndexedProperties.PrintStringProperty> 对象并将其设置 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> 为 "位置"，并将其设置 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> 为合适的 <xref:System.String> 。  
  
8. 使用第二个 <xref:System.Printing.IndexedProperties.PrintStringProperty> 对象作为 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> "Location" 项的值。  
  
9. 创建的数组 <xref:System.String> 。 每个项都是服务器上的端口的名称。  
  
10. 使用 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> 安装具有新值的新打印机。  
  
 下面是一个示例。  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [WPF 中的文档](documents-in-wpf.md)
- [打印概述](printing-overview.md)
