---
title: 如何：处理 ScrollChanged 事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], raising ScrollChanged events
- ScrollChanged events [WPF]
ms.assetid: 42c695d8-ee28-49d4-80fd-fc71e9be7f29
ms.openlocfilehash: 070706ef5f9da25a4ee2fd009367fa8e1fd9ddc2
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668144"
---
# <a name="how-to-handle-the-scrollchanged-event"></a>如何：处理 ScrollChanged 事件
## <a name="example"></a>示例  
 此示例演示如何处理的 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 事件 <xref:System.Windows.Controls.ScrollViewer> 。  
  
 <xref:System.Windows.Documents.FlowDocument>包含部分的元素 <xref:System.Windows.Documents.Paragraph> 在中定义 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。 当 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 由于用户交互而发生事件时，将调用处理程序，并将文本写入 <xref:System.Windows.Controls.TextBlock> 指示事件已发生的。  
  
 [!code-xaml[scrollchangedeventargsLayout#1](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xaml[scrollchangedeventargsLayout#2](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>
- <xref:System.Windows.Controls.ScrollChangedEventHandler>
- <xref:System.Windows.Controls.ScrollChangedEventArgs>
