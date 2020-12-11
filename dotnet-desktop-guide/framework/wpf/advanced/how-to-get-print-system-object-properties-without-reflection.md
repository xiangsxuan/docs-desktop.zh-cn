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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971824"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="e4fe0-102">如何：在不使用反射的情况下获得打印系统对象属性</span><span class="sxs-lookup"><span data-stu-id="e4fe0-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="e4fe0-103">使用反射来对属性进行 (，并对对象) 这些属性类型可能会降低应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="e4fe0-104"><xref:System.Printing.IndexedProperties>命名空间提供了使用反射获取此信息的方法。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4fe0-105">示例</span><span class="sxs-lookup"><span data-stu-id="e4fe0-105">Example</span></span>  
 <span data-ttu-id="e4fe0-106">执行此操作的步骤如下所示。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-106">The steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="e4fe0-107">创建类型的实例。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-107">Create an instance of the type.</span></span> <span data-ttu-id="e4fe0-108">在下面的示例中，类型是 <xref:System.Printing.PrintQueue> 随 Microsoft .NET 框架附带的类型，但几乎完全相同的代码应该适用于从派生的类型 <xref:System.Printing.PrintSystemObject> 。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with Microsoft .NET Framework, but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2. <span data-ttu-id="e4fe0-109"><xref:System.Printing.IndexedProperties.PrintPropertyDictionary>从类型的创建 <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="e4fe0-110"><xref:System.Collections.DictionaryEntry.Value%2A>此字典中的每个项的属性是从派生的类型之一的对象 <xref:System.Printing.IndexedProperties.PrintProperty> 。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3. <span data-ttu-id="e4fe0-111">枚举字典的成员。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="e4fe0-112">对于每个文件，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-112">For each of them, do the following.</span></span>  
  
4. <span data-ttu-id="e4fe0-113">向上-将每个条目的值强制转换为 <xref:System.Printing.IndexedProperties.PrintProperty> ，并使用它来创建 <xref:System.Printing.IndexedProperties.PrintProperty> 对象。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5. <span data-ttu-id="e4fe0-114">获取 <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> 每个对象的的类型 <xref:System.Printing.IndexedProperties.PrintProperty> 。</span><span class="sxs-lookup"><span data-stu-id="e4fe0-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="e4fe0-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4fe0-115">See also</span></span>

- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="e4fe0-116">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="e4fe0-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="e4fe0-117">打印概述</span><span class="sxs-lookup"><span data-stu-id="e4fe0-117">Printing Overview</span></span>](printing-overview.md)
