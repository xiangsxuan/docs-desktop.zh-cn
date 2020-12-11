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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973990"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a>如何：在 StackPanel 和 DockPanel 之间进行选择
此示例演示如何在 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.DockPanel> 中的堆栈内容时，在使用或之间进行选择 <xref:System.Windows.Controls.Panel> 。

## <a name="example"></a>示例
 尽管可以使用 <xref:System.Windows.Controls.DockPanel> 或 <xref:System.Windows.Controls.StackPanel> 来堆栈子元素，但这两个控件不会始终产生相同的结果。 例如，放置子元素的顺序可能会影响中子元素的大小，而不会影响中的子元素的大小 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.StackPanel> 。 之所以发生这种不同的行为，是因为 <xref:System.Windows.Controls.StackPanel> 度量值是在 [PositiveInfinity](xref:System.Double.PositiveInfinity)中的堆栈方向上; 但是， <xref:System.Windows.Controls.DockPanel> 只测量可用大小。

 下面的示例演示了和之间的主要差异 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.StackPanel> 。

 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [面板概述](panels-overview.md)
