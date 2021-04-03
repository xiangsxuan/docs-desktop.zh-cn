---
title: 如何：在 StackPanel 和 DockPanel 之间进行选择
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
ms.openlocfilehash: bdf4b38e67a7856136224368e86609c135e5ad6f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973990"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="adb6c-102">如何：在 StackPanel 和 DockPanel 之间进行选择</span><span class="sxs-lookup"><span data-stu-id="adb6c-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="adb6c-103">此示例演示如何在 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.DockPanel> 中的堆栈内容时，在使用或之间进行选择 <xref:System.Windows.Controls.Panel> 。</span><span class="sxs-lookup"><span data-stu-id="adb6c-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>

## <a name="example"></a><span data-ttu-id="adb6c-104">示例</span><span class="sxs-lookup"><span data-stu-id="adb6c-104">Example</span></span>
 <span data-ttu-id="adb6c-105">尽管可以使用 <xref:System.Windows.Controls.DockPanel> 或 <xref:System.Windows.Controls.StackPanel> 来堆栈子元素，但这两个控件不会始终产生相同的结果。</span><span class="sxs-lookup"><span data-stu-id="adb6c-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="adb6c-106">例如，放置子元素的顺序可能会影响中子元素的大小，而不会影响中的子元素的大小 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.StackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="adb6c-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="adb6c-107">之所以发生这种不同的行为，是因为 <xref:System.Windows.Controls.StackPanel> 度量值是在 [PositiveInfinity](xref:System.Double.PositiveInfinity)中的堆栈方向上; 但是， <xref:System.Windows.Controls.DockPanel> 只测量可用大小。</span><span class="sxs-lookup"><span data-stu-id="adb6c-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at [Double.PositiveInfinity](xref:System.Double.PositiveInfinity); however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>

 <span data-ttu-id="adb6c-108">下面的示例演示了和之间的主要差异 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.StackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="adb6c-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>

 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]

## <a name="see-also"></a><span data-ttu-id="adb6c-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="adb6c-109">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="adb6c-110">面板概述</span><span class="sxs-lookup"><span data-stu-id="adb6c-110">Panels Overview</span></span>](panels-overview.md)
