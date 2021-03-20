---
title: 如何：以编程方式更改 TextWrapping 属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
ms.openlocfilehash: 9b52041df49b09d388de0b35404932b8af4946fb
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665960"
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a>如何：以编程方式更改 TextWrapping 属性
## <a name="example"></a>示例  
 下面的代码示例演示如何以 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 编程方式更改属性的值。  
  
 <xref:System.Windows.Controls.Button>在的元素中放置三个元素 <xref:System.Windows.Controls.StackPanel> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。 的每个 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件都 <xref:System.Windows.Controls.Button> 对应于代码中的一个事件处理程序。 在单击按钮时，事件处理程序使用的名称与 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 将应用到的值相同 `txt2` 。 此外， (中未) 显示的中的文本将 `txt1` <xref:System.Windows.Controls.TextBlock> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 会更新，以反映属性中的更改。  
  
 [!code-xaml[TextWrapProperty#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>
- <xref:System.Windows.TextWrapping>
