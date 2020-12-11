---
title: 如何：获取或设置 Dock 值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: fb6c8a7d62aa09a6e1d82cb4079d1425a7f39f8c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972530"
---
# <a name="how-to-get-or-set-a-dock-value"></a>如何：获取或设置 Dock 值
下面的示例演示如何为对象分配 <xref:System.Windows.Controls.Dock> 值。 该示例使用的 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 和 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 方法 <xref:System.Windows.Controls.DockPanel> 。  
  
## <a name="example"></a>示例  
 该示例创建了元素的一个实例， <xref:System.Windows.Controls.TextBlock> `txt1` 并使用的 <xref:System.Windows.Controls.Dock> 方法为赋值 `Top` <xref:System.Windows.Controls.DockPanel.SetDock%2A> <xref:System.Windows.Controls.DockPanel> 。 然后，它 <xref:System.Windows.Controls.Dock> 使用方法将属性值追加到 <xref:System.Windows.Controls.TextBlock.Text%2A> 元素的 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.DockPanel.GetDock%2A> 。 最后，此示例将 <xref:System.Windows.Controls.TextBlock> 元素添加到父级 <xref:System.Windows.Controls.DockPanel> `dp1` 。  
  
 [!code-csharp[DockPanelSetDock#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [面板概述](panels-overview.md)
