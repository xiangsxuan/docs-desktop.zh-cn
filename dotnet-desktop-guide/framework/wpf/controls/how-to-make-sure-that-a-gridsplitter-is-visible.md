---
title: 如何：确保 GridSplitter 可见
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 2085ac5cec206d8692a1267acf132688f0aa9082
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974069"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>如何：确保 GridSplitter 可见
此示例演示如何确保 <xref:System.Windows.Controls.GridSplitter> 中的其他控件不会隐藏控件 <xref:System.Windows.Controls.Grid> 。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.Panel.Children%2A>控件的按 <xref:System.Windows.Controls.Grid> 其在标记或代码中定义的顺序呈现。 <xref:System.Windows.Controls.GridSplitter> 如果你未将控件定义为集合中的最后一个元素， <xref:System.Windows.Controls.Panel.Children%2A> 或者如果你为其他控件指定更高的控件，则这些控件可以隐藏控件 <xref:System.Windows.Controls.Panel.ZIndexProperty> 。  
  
 若要防止隐藏 <xref:System.Windows.Controls.GridSplitter> 控件，请执行以下操作之一。  
  
- 请确保 <xref:System.Windows.Controls.GridSplitter> 控件是最后 <xref:System.Windows.Controls.Panel.Children%2A> 添加到中的 <xref:System.Windows.Controls.Grid> 。 下面的示例演示 <xref:System.Windows.Controls.GridSplitter> 作为的集合中的最后一个元素 <xref:System.Windows.Controls.Panel.Children%2A> <xref:System.Windows.Controls.Grid> 。  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
- 将 <xref:System.Windows.Controls.Panel.ZIndexProperty> 上的设置 <xref:System.Windows.Controls.GridSplitter> 为高于将隐藏它的控件。 下面的示例为 <xref:System.Windows.Controls.GridSplitter> 控件提供的控件 <xref:System.Windows.Controls.Panel.ZIndexProperty> 比 <xref:System.Windows.Controls.Button> 控件高。  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
- 设置控件上的边距（否则将隐藏）， <xref:System.Windows.Controls.GridSplitter> 以便 <xref:System.Windows.Controls.GridSplitter> 公开。 下面的示例在控件上设置将以其他方式叠加并隐藏的边距 <xref:System.Windows.Controls.GridSplitter> 。  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.GridSplitter>
- [操作指南主题](gridsplitter-how-to-topics.md)
