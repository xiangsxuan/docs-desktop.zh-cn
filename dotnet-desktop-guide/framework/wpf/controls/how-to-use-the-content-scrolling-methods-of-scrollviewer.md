---
title: 如何：使用 ScrollViewer 的内容滚动方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: ac186cc9da0648b714627e9b7d70b5e9bc7d840f
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664010"
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a>如何：使用 ScrollViewer 的内容滚动方法
此示例演示如何使用元素的滚动方法 <xref:System.Windows.Controls.ScrollViewer> 。 这些方法在中按行或页的方式提供内容的增量滚动 <xref:System.Windows.Controls.ScrollViewer> 。  
  
## <a name="example"></a>示例  
 下面的示例创建一个 <xref:System.Windows.Controls.ScrollViewer> 名为的 `sv1` ，它承载一个子 <xref:System.Windows.Controls.TextBlock> 元素。 因为大于 <xref:System.Windows.Controls.TextBlock> 父项 <xref:System.Windows.Controls.ScrollViewer> ，所以滚动条会出现以便启用滚动。 <xref:System.Windows.Controls.Button> 表示各种滚动方法的元素停靠在单独的的左侧 <xref:System.Windows.Controls.StackPanel> 。 文件中的每个都 <xref:System.Windows.Controls.Button> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 调用相关的自定义方法，该方法控制中的滚动行为 <xref:System.Windows.Controls.ScrollViewer> 。  
  
 [!code-xaml[ScrollViewerMethods#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 下面的示例使用 <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> 和 <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> 方法。  
  
 [!code-csharp[ScrollViewerMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.StackPanel>
