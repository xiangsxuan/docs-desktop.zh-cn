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
# <a name="how-to-change-the-textwrapping-property-programmatically"></a><span data-ttu-id="869f0-102">如何：以编程方式更改 TextWrapping 属性</span><span class="sxs-lookup"><span data-stu-id="869f0-102">How to: Change the TextWrapping Property Programmatically</span></span>
## <a name="example"></a><span data-ttu-id="869f0-103">示例</span><span class="sxs-lookup"><span data-stu-id="869f0-103">Example</span></span>  
 <span data-ttu-id="869f0-104">下面的代码示例演示如何以 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 编程方式更改属性的值。</span><span class="sxs-lookup"><span data-stu-id="869f0-104">The following code example shows how to change the value of the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> property programmatically.</span></span>  
  
 <span data-ttu-id="869f0-105"><xref:System.Windows.Controls.Button>在的元素中放置三个元素 <xref:System.Windows.Controls.StackPanel> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="869f0-105">Three <xref:System.Windows.Controls.Button> elements are placed within a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="869f0-106">的每个 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件都 <xref:System.Windows.Controls.Button> 对应于代码中的一个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="869f0-106">Each <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for a <xref:System.Windows.Controls.Button> corresponds with an event handler in the code.</span></span> <span data-ttu-id="869f0-107">在单击按钮时，事件处理程序使用的名称与 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 将应用到的值相同 `txt2` 。</span><span class="sxs-lookup"><span data-stu-id="869f0-107">The event handlers use the same name as the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> value they will apply to `txt2` when the button is clicked.</span></span> <span data-ttu-id="869f0-108">此外， (中未) 显示的中的文本将 `txt1` <xref:System.Windows.Controls.TextBlock> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 会更新，以反映属性中的更改。</span><span class="sxs-lookup"><span data-stu-id="869f0-108">Also, the text in `txt1` (a <xref:System.Windows.Controls.TextBlock> not shown in the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]) is updated to reflect the change in the property.</span></span>  
  
 [!code-xaml[TextWrapProperty#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="869f0-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="869f0-109">See also</span></span>

- <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>
- <xref:System.Windows.TextWrapping>
