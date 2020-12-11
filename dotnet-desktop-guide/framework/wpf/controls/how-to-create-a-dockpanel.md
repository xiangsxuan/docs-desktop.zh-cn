---
title: 如何：创建 DockPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], creating
ms.assetid: 9194f663-e279-4f1a-86d7-125a57d05c6f
ms.openlocfilehash: 35434a13386ae89fdc1428bd632d21c1551c9871
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973975"
---
# <a name="how-to-create-a-dockpanel"></a><span data-ttu-id="31376-102">如何：创建 DockPanel</span><span class="sxs-lookup"><span data-stu-id="31376-102">How to: Create a DockPanel</span></span>
## <a name="example"></a><span data-ttu-id="31376-103">示例</span><span class="sxs-lookup"><span data-stu-id="31376-103">Example</span></span>  
 <span data-ttu-id="31376-104">下面的示例通过使用代码创建和使用的实例 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="31376-104">The following example creates and uses an instance of <xref:System.Windows.Controls.DockPanel> by using code.</span></span> <span data-ttu-id="31376-105">该示例演示如何通过创建五个 <xref:System.Windows.Shapes.Rectangle> 元素并定位 (停靠) 它们在父级中的位置来分区空间 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="31376-105">The example shows you how to partition space by creating five <xref:System.Windows.Shapes.Rectangle> elements and positioning (docking) them inside a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="31376-106">如果保留默认设置，则最后一个矩形会填充所有剩余的未分配空间。</span><span class="sxs-lookup"><span data-stu-id="31376-106">If you retain the default setting, the final rectangle fills all the remaining unallocated space.</span></span>  
  
 [!code-csharp[DockPanelCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelCode/CSharp/DockPanel_Code.cs#1)]
 [!code-vb[DockPanelCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelCode/VisualBasic/dockpanel_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="31376-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31376-107">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Dock>
- [<span data-ttu-id="31376-108">面板概述</span><span class="sxs-lookup"><span data-stu-id="31376-108">Panels Overview</span></span>](panels-overview.md)
