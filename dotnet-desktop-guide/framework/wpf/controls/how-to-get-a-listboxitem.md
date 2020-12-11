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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971037"
---
# <a name="how-to-get-a-listboxitem"></a>如何：获取 ListBoxItem
如果需要获取特定于 <xref:System.Windows.Controls.ListBoxItem> 中特定索引的 <xref:System.Windows.Controls.ListBox> ，可以使用 <xref:System.Windows.Controls.ItemContainerGenerator> 。  
  
## <a name="example"></a>示例  
 下面的示例演示 <xref:System.Windows.Controls.ListBox> 及其项。  
  
 [!code-xaml[ListBoxItems#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 下面的示例演示如何通过在的属性中指定项的索引来检索项 <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> <xref:System.Windows.Controls.ItemContainerGenerator> 。  
  
 [!code-csharp[ListBoxItems#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 检索列表框项后，可以显示项的内容，如下面的示例中所示。  
  
 [!code-csharp[ListBoxItems#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]
