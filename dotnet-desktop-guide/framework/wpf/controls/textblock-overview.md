---
title: TextBlock 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: 9e41cc905a529579dc63638467fe99b47c78400e
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667260"
---
# <a name="textblock-overview"></a>TextBlock 概述
<xref:System.Windows.Controls.TextBlock>控件为应用程序提供灵活的文本支持 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 该元素主要面向不需要多个文本段落的基本 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 方案。 它支持多个属性，这些属性可以实现精确控制演示，例如 <xref:System.Windows.Controls.TextBlock.FontFamily%2A> 、、、 <xref:System.Windows.Controls.TextBlock.FontSize%2A> <xref:System.Windows.Controls.TextBlock.FontWeight%2A> <xref:System.Windows.Controls.TextBlock.TextEffects%2A> 和 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 。 可以使用属性添加文本内容 <xref:System.Windows.Controls.TextBlock.Text%2A> 。 在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中使用时，开始标记和结束标记之间的内容隐式添加为元素的文本。  
  
 <xref:System.Windows.Controls.TextBlock>元素的实例化很简单，只需使用即可 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。  
  
 [!code-xaml[TextBlockSnip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 同样， <xref:System.Windows.Controls.TextBlock> 代码中的元素使用相对简单。  
  
 [!code-csharp[TextBlockSnip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Label>
