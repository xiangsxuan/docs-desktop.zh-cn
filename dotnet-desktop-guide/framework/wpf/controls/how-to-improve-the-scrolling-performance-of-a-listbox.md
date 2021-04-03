---
title: 如何：提高 ListBox 的滚动性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: a9d1ca1d8ac2ef830984408f3052eb0ed0987c5d
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973093"
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a>如何：提高 ListBox 的滚动性能
如果 <xref:System.Windows.Controls.ListBox> 包含很多项，则当用户 <xref:System.Windows.Controls.ListBox> 使用鼠标滚轮滚动或拖动滚动条的滚动块时，用户界面响应可能会很慢。 <xref:System.Windows.Controls.ListBox>通过将附加属性设置为，可以提高用户滚动时的性能 `VirtualizingStackPanel.VirtualizationMode` <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 。  
  
## <a name="example"></a>示例  
  
## <a name="description"></a>说明  
下面的示例创建一个 <xref:System.Windows.Controls.ListBox> ，并将 `VirtualizingStackPanel.VirtualizationMode` 附加属性设置为， <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 以在滚动过程中提高性能。  
  
## <a name="code"></a>代码  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 下面的示例显示了上一示例所使用的数据。  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
