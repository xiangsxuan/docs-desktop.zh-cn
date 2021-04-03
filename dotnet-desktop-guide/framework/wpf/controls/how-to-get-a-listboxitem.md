---
title: 如何：获取 ListBoxItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox controls [WPF], getting a ListBoxItem
- ListBoxItem [WPF]
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
ms.openlocfilehash: 27a435feb4a941c77af221ab25bd63ea98b16e92
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971037"
---
# <a name="how-to-get-a-listboxitem"></a><span data-ttu-id="71bb6-102">如何：获取 ListBoxItem</span><span class="sxs-lookup"><span data-stu-id="71bb6-102">How to: Get a ListBoxItem</span></span>
<span data-ttu-id="71bb6-103">如果需要获取特定于 <xref:System.Windows.Controls.ListBoxItem> 中特定索引的 <xref:System.Windows.Controls.ListBox> ，可以使用 <xref:System.Windows.Controls.ItemContainerGenerator> 。</span><span class="sxs-lookup"><span data-stu-id="71bb6-103">If you need to get a specific <xref:System.Windows.Controls.ListBoxItem> at a particular index in a <xref:System.Windows.Controls.ListBox>, you can use an <xref:System.Windows.Controls.ItemContainerGenerator>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71bb6-104">示例</span><span class="sxs-lookup"><span data-stu-id="71bb6-104">Example</span></span>  
 <span data-ttu-id="71bb6-105">下面的示例演示 <xref:System.Windows.Controls.ListBox> 及其项。</span><span class="sxs-lookup"><span data-stu-id="71bb6-105">The following example shows a <xref:System.Windows.Controls.ListBox> and its items.</span></span>  
  
 [!code-xaml[ListBoxItems#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="71bb6-106">下面的示例演示如何通过在的属性中指定项的索引来检索项 <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> <xref:System.Windows.Controls.ItemContainerGenerator> 。</span><span class="sxs-lookup"><span data-stu-id="71bb6-106">The following example shows how to retrieve the item by specifying the index of the item in the <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> property of the <xref:System.Windows.Controls.ItemContainerGenerator>.</span></span>  
  
 [!code-csharp[ListBoxItems#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 <span data-ttu-id="71bb6-107">检索列表框项后，可以显示项的内容，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="71bb6-107">After you have retrieved the list box item, you can display the contents of the item, as shown in the following example.</span></span>  
  
 [!code-csharp[ListBoxItems#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]
