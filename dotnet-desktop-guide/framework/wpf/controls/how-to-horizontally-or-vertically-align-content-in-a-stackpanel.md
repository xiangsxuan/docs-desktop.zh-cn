---
title: 如何：在 StackPanel 中水平或垂直对齐内容
description: 了解如何在 Windows Presentation Foundation System.windows.controls.stackpanel> 和子内容的 HorizontalAlignment 和 VerticalAlignment 中调整内容方向。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: b847ee4808c14622f24d758b9eb9ada28712ab3c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972813"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>如何：在 StackPanel 中水平或垂直对齐内容
此示例演示如何调整 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 元素内内容的 <xref:System.Windows.Controls.StackPanel> ，以及如何调整 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 子内容的和。  
  
## <a name="example"></a>示例  
 下面的示例在中创建三个 <xref:System.Windows.Controls.ListBox> 元素 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。 每个都 <xref:System.Windows.Controls.ListBox> 表示的 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 、 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 和属性的可能值 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> <xref:System.Windows.Controls.StackPanel> 。 当用户在任何元素中选择某个值时 <xref:System.Windows.Controls.ListBox> ，的关联属性 <xref:System.Windows.Controls.StackPanel> 及其子 <xref:System.Windows.Controls.Button> 元素将发生更改。  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 下面的代码隐藏文件定义了对与选择更改关联的事件所做的更改 <xref:System.Windows.Controls.ListBox> 。 <xref:System.Windows.Controls.StackPanel> 由标识 <xref:System.Windows.FrameworkElement.Name%2A> `sp1` 。  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [面板概述](panels-overview.md)
