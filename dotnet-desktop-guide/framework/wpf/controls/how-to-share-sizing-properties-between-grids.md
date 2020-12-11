---
title: 如何：在网格之间共享大小调整属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974007"
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="c130d-102">如何：在网格之间共享大小调整属性</span><span class="sxs-lookup"><span data-stu-id="c130d-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="c130d-103">此示例演示如何在元素之间共享列和行的大小调整数据，以便 <xref:System.Windows.Controls.Grid> 保持一致的大小。</span><span class="sxs-lookup"><span data-stu-id="c130d-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c130d-104">示例</span><span class="sxs-lookup"><span data-stu-id="c130d-104">Example</span></span>  
 <span data-ttu-id="c130d-105">下面的示例将两个 <xref:System.Windows.Controls.Grid> 元素引入为父元素的子元素 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c130d-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="c130d-106">的 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> 附加属性 <xref:System.Windows.Controls.Grid> 是在父级上定义的 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c130d-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="c130d-107">该示例使用两个元素操作属性值 <xref:System.Windows.Controls.Button> ; 每个元素表示一个布尔属性值。</span><span class="sxs-lookup"><span data-stu-id="c130d-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="c130d-108">当 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> 属性值设置为时 `true` ，将共享大小调整信息的每个列或行成员 <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> ，而不考虑行或列的内容。</span><span class="sxs-lookup"><span data-stu-id="c130d-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="c130d-109">...</span><span class="sxs-lookup"><span data-stu-id="c130d-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="c130d-110">下面的代码隐藏示例处理按钮 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件引发的方法。</span><span class="sxs-lookup"><span data-stu-id="c130d-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="c130d-111">该示例将这些方法调用的结果写入到 <xref:System.Windows.Controls.TextBlock> 使用相关 get 方法的元素，以将新属性值输出为字符串。</span><span class="sxs-lookup"><span data-stu-id="c130d-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c130d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c130d-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [<span data-ttu-id="c130d-113">面板概述</span><span class="sxs-lookup"><span data-stu-id="c130d-113">Panels Overview</span></span>](panels-overview.md)
