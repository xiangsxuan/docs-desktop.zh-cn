---
title: 如何：按名称查找元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: d8f5e9077400d460e2e42638a534bacc656db22f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973479"
---
# <a name="how-to-find-an-element-by-its-name"></a><span data-ttu-id="388fa-102">如何：按名称查找元素</span><span class="sxs-lookup"><span data-stu-id="388fa-102">How to: Find an Element by Its Name</span></span>
<span data-ttu-id="388fa-103">此示例说明如何使用 <xref:System.Windows.FrameworkElement.FindName%2A> 方法通过其值查找元素 <xref:System.Windows.FrameworkElement.Name%2A> 。</span><span class="sxs-lookup"><span data-stu-id="388fa-103">This example describes how to use the <xref:System.Windows.FrameworkElement.FindName%2A> method to find an element by its <xref:System.Windows.FrameworkElement.Name%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="388fa-104">示例</span><span class="sxs-lookup"><span data-stu-id="388fa-104">Example</span></span>  
 <span data-ttu-id="388fa-105">在此示例中，按其名称查找特定元素的方法被编写为按钮的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="388fa-105">In this example, the method to find a particular element by its name is written as the event handler of a button.</span></span> <span data-ttu-id="388fa-106">`stackPanel` 是 <xref:System.Windows.FrameworkElement.Name%2A> 要搜索的根的 <xref:System.Windows.FrameworkElement> ，然后该示例方法通过将其强制转换为 <xref:System.Windows.Controls.TextBlock> 并更改某个可见的属性，直观地指示找到的元素 <xref:System.Windows.Controls.TextBlock> [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="388fa-106">`stackPanel` is the <xref:System.Windows.FrameworkElement.Name%2A> of the root <xref:System.Windows.FrameworkElement> being searched, and the example method then visually indicates the found element by casting it as <xref:System.Windows.Controls.TextBlock> and changing one of the <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] properties.</span></span>  
  
 [!code-csharp[FEFindName#Find](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
