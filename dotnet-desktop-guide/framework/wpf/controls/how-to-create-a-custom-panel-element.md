---
title: 如何：创建自定义 Panel 元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973978"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="3fb81-102">如何：创建自定义 Panel 元素</span><span class="sxs-lookup"><span data-stu-id="3fb81-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="3fb81-103">示例</span><span class="sxs-lookup"><span data-stu-id="3fb81-103">Example</span></span>  
 <span data-ttu-id="3fb81-104">此示例演示如何重写元素的默认布局行为 <xref:System.Windows.Controls.Panel> ，并创建派生自的自定义布局元素 <xref:System.Windows.Controls.Panel> 。</span><span class="sxs-lookup"><span data-stu-id="3fb81-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="3fb81-105">该示例定义一个名为的简单自定义 <xref:System.Windows.Controls.Panel> 元素 `PlotPanel` ，该元素根据两个硬编码的 x 坐标和 y 坐标来定位子元素。</span><span class="sxs-lookup"><span data-stu-id="3fb81-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="3fb81-106">在此示例中， `x` 和均 `y` 设置为 `50` ; 因此，所有子元素都放置在 x 和 y 轴上的该位置。</span><span class="sxs-lookup"><span data-stu-id="3fb81-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="3fb81-107">若要实现自定义 <xref:System.Windows.Controls.Panel> 行为，该示例使用 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 和 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="3fb81-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="3fb81-108">每个方法都返回 <xref:System.Windows.Size> 定位和呈现子元素所必需的数据。</span><span class="sxs-lookup"><span data-stu-id="3fb81-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3fb81-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fb81-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="3fb81-110">面板概述</span><span class="sxs-lookup"><span data-stu-id="3fb81-110">Panels Overview</span></span>](panels-overview.md)
