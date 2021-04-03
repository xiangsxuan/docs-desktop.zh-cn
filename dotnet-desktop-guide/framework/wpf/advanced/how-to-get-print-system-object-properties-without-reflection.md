---
title: 如何：在不使用反射的情况下获得打印系统对象属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: bb906dafd98e75708764b5f0f009900719f6a475
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971824"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a>如何：在不使用反射的情况下获得打印系统对象属性
使用反射来对属性进行 (，并对对象) 这些属性类型可能会降低应用程序性能。 <xref:System.Printing.IndexedProperties>命名空间提供了使用反射获取此信息的方法。  
  
## <a name="example"></a>示例  
 执行此操作的步骤如下所示。  
  
1. 创建类型的实例。 在下面的示例中，类型是 <xref:System.Printing.PrintQueue> 随 Microsoft .NET 框架附带的类型，但几乎完全相同的代码应该适用于从派生的类型 <xref:System.Printing.PrintSystemObject> 。  
  
2. <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>从类型的创建 <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> 。 <xref:System.Collections.DictionaryEntry.Value%2A>此字典中的每个项的属性是从派生的类型之一的对象 <xref:System.Printing.IndexedProperties.PrintProperty> 。  
  
3. 枚举字典的成员。 对于每个文件，请执行以下操作。  
  
4. 向上-将每个条目的值强制转换为 <xref:System.Printing.IndexedProperties.PrintProperty> ，并使用它来创建 <xref:System.Printing.IndexedProperties.PrintProperty> 对象。  
  
5. 获取 <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> 每个对象的的类型 <xref:System.Printing.IndexedProperties.PrintProperty> 。  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [WPF 中的文档](documents-in-wpf.md)
- [打印概述](printing-overview.md)
