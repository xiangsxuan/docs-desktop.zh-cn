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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972530"
---
# <a name="how-to-get-or-set-a-dock-value"></a><span data-ttu-id="473d8-102">如何：获取或设置 Dock 值</span><span class="sxs-lookup"><span data-stu-id="473d8-102">How to: Get or Set a Dock Value</span></span>
<span data-ttu-id="473d8-103">下面的示例演示如何为对象分配 <xref:System.Windows.Controls.Dock> 值。</span><span class="sxs-lookup"><span data-stu-id="473d8-103">The following example shows how to assign a <xref:System.Windows.Controls.Dock> value for an object.</span></span> <span data-ttu-id="473d8-104">该示例使用的 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 和 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 方法 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="473d8-104">The example uses the <xref:System.Windows.Controls.DockPanel.GetDock%2A> and <xref:System.Windows.Controls.DockPanel.SetDock%2A> methods of <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="473d8-105">示例</span><span class="sxs-lookup"><span data-stu-id="473d8-105">Example</span></span>  
 <span data-ttu-id="473d8-106">该示例创建了元素的一个实例， <xref:System.Windows.Controls.TextBlock> `txt1` 并使用的 <xref:System.Windows.Controls.Dock> 方法为赋值 `Top` <xref:System.Windows.Controls.DockPanel.SetDock%2A> <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="473d8-106">The example creates an instance of the <xref:System.Windows.Controls.TextBlock> element, `txt1`, and assigns a <xref:System.Windows.Controls.Dock> value of `Top` by using the <xref:System.Windows.Controls.DockPanel.SetDock%2A> method of <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="473d8-107">然后，它 <xref:System.Windows.Controls.Dock> 使用方法将属性值追加到 <xref:System.Windows.Controls.TextBlock.Text%2A> 元素的 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.DockPanel.GetDock%2A> 。</span><span class="sxs-lookup"><span data-stu-id="473d8-107">It then appends the value of the <xref:System.Windows.Controls.Dock> property to the <xref:System.Windows.Controls.TextBlock.Text%2A> of the <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.DockPanel.GetDock%2A> method.</span></span> <span data-ttu-id="473d8-108">最后，此示例将 <xref:System.Windows.Controls.TextBlock> 元素添加到父级 <xref:System.Windows.Controls.DockPanel> `dp1` 。</span><span class="sxs-lookup"><span data-stu-id="473d8-108">Finally, the example adds the <xref:System.Windows.Controls.TextBlock> element to the parent <xref:System.Windows.Controls.DockPanel>, `dp1`.</span></span>  
  
 [!code-csharp[DockPanelSetDock#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="473d8-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="473d8-109">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [<span data-ttu-id="473d8-110">面板概述</span><span class="sxs-lookup"><span data-stu-id="473d8-110">Panels Overview</span></span>](panels-overview.md)
