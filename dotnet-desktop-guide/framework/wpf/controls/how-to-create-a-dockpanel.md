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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973975"
---
# <a name="how-to-create-a-dockpanel"></a><span data-ttu-id="d0173-102">如何：创建 DockPanel</span><span class="sxs-lookup"><span data-stu-id="d0173-102">How to: Create a DockPanel</span></span>
## <a name="example"></a><span data-ttu-id="d0173-103">示例</span><span class="sxs-lookup"><span data-stu-id="d0173-103">Example</span></span>  
 <span data-ttu-id="d0173-104">下面的示例通过使用代码创建和使用的实例 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="d0173-104">The following example creates and uses an instance of <xref:System.Windows.Controls.DockPanel> by using code.</span></span> <span data-ttu-id="d0173-105">该示例演示如何通过创建五个 <xref:System.Windows.Shapes.Rectangle> 元素并定位 (停靠) 它们在父级中的位置来分区空间 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="d0173-105">The example shows you how to partition space by creating five <xref:System.Windows.Shapes.Rectangle> elements and positioning (docking) them inside a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="d0173-106">如果保留默认设置，则最后一个矩形会填充所有剩余的未分配空间。</span><span class="sxs-lookup"><span data-stu-id="d0173-106">If you retain the default setting, the final rectangle fills all the remaining unallocated space.</span></span>  
  
 [!code-csharp[DockPanelCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelCode/CSharp/DockPanel_Code.cs#1)]
 [!code-vb[DockPanelCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelCode/VisualBasic/dockpanel_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d0173-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0173-107">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Dock>
- [<span data-ttu-id="d0173-108">面板概述</span><span class="sxs-lookup"><span data-stu-id="d0173-108">Panels Overview</span></span>](panels-overview.md)
