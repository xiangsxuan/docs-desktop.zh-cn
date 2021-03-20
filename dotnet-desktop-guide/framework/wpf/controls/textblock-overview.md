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
# <a name="textblock-overview"></a><span data-ttu-id="645a9-102">TextBlock 概述</span><span class="sxs-lookup"><span data-stu-id="645a9-102">TextBlock Overview</span></span>
<span data-ttu-id="645a9-103"><xref:System.Windows.Controls.TextBlock>控件为应用程序提供灵活的文本支持 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="645a9-103">The <xref:System.Windows.Controls.TextBlock> control provides flexible text support for [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="645a9-104">该元素主要面向不需要多个文本段落的基本 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 方案。</span><span class="sxs-lookup"><span data-stu-id="645a9-104">The element is targeted primarily toward basic [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] scenarios that do not require more than one paragraph of text.</span></span> <span data-ttu-id="645a9-105">它支持多个属性，这些属性可以实现精确控制演示，例如 <xref:System.Windows.Controls.TextBlock.FontFamily%2A> 、、、 <xref:System.Windows.Controls.TextBlock.FontSize%2A> <xref:System.Windows.Controls.TextBlock.FontWeight%2A> <xref:System.Windows.Controls.TextBlock.TextEffects%2A> 和 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 。</span><span class="sxs-lookup"><span data-stu-id="645a9-105">It supports a number of properties that enable precise control of presentation, such as <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, and <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span></span> <span data-ttu-id="645a9-106">可以使用属性添加文本内容 <xref:System.Windows.Controls.TextBlock.Text%2A> 。</span><span class="sxs-lookup"><span data-stu-id="645a9-106">Text content can be added using the <xref:System.Windows.Controls.TextBlock.Text%2A> property.</span></span> <span data-ttu-id="645a9-107">在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中使用时，开始标记和结束标记之间的内容隐式添加为元素的文本。</span><span class="sxs-lookup"><span data-stu-id="645a9-107">When used in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], content between the open and closing tag is implicitly added as the text of the element.</span></span>  
  
 <span data-ttu-id="645a9-108"><xref:System.Windows.Controls.TextBlock>元素的实例化很简单，只需使用即可 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="645a9-108">A <xref:System.Windows.Controls.TextBlock> element can be instantiated very simply using [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[TextBlockSnip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 <span data-ttu-id="645a9-109">同样， <xref:System.Windows.Controls.TextBlock> 代码中的元素使用相对简单。</span><span class="sxs-lookup"><span data-stu-id="645a9-109">Similarly, usage of the <xref:System.Windows.Controls.TextBlock> element in code is relatively simple.</span></span>  
  
 [!code-csharp[TextBlockSnip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="645a9-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="645a9-110">See also</span></span>

- <xref:System.Windows.Controls.Label>
