---
title: 如何：使用 DockPanel 元素对空间进行分区
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: 3682acc559e4e8740b97f781b6f927eac1e380d7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974064"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="125ef-102">如何：使用 DockPanel 元素对空间进行分区</span><span class="sxs-lookup"><span data-stu-id="125ef-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="125ef-103">下面的示例使用元素创建一个简单 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 框架 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="125ef-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="125ef-104">将 <xref:System.Windows.Controls.DockPanel> 可用空间分区给其子元素。</span><span class="sxs-lookup"><span data-stu-id="125ef-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="125ef-105">示例</span><span class="sxs-lookup"><span data-stu-id="125ef-105">Example</span></span>  
 <span data-ttu-id="125ef-106">此示例使用 <xref:System.Windows.Controls.DockPanel.Dock%2A> 属性，该属性是一个附加属性，用于将两个相同的 <xref:System.Windows.Controls.Border> 元素停靠在 <xref:System.Windows.Controls.Dock.Top> 分区空间的上。</span><span class="sxs-lookup"><span data-stu-id="125ef-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="125ef-107">第三个 <xref:System.Windows.Controls.Border> 元素停靠到 <xref:System.Windows.Controls.Dock.Left> ，其宽度设置为200像素。</span><span class="sxs-lookup"><span data-stu-id="125ef-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="125ef-108">第四个 <xref:System.Windows.Controls.Border> 停靠到 <xref:System.Windows.Controls.Dock.Bottom> 屏幕的。</span><span class="sxs-lookup"><span data-stu-id="125ef-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="125ef-109">最后一个 <xref:System.Windows.Controls.Border> 元素自动填充剩余的空间。</span><span class="sxs-lookup"><span data-stu-id="125ef-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> <span data-ttu-id="125ef-110">默认情况下，元素的最后一个子 <xref:System.Windows.Controls.DockPanel> 元素会填充剩余的未分配空间。</span><span class="sxs-lookup"><span data-stu-id="125ef-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="125ef-111">如果不希望出现此行为，请设置 `LastChildFill="False"`。</span><span class="sxs-lookup"><span data-stu-id="125ef-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="125ef-112">已编译的应用程序将生成如下所示的新 UI。</span><span class="sxs-lookup"><span data-stu-id="125ef-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="125ef-113">![典型的 DockPanel 方案。](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="125ef-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="125ef-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="125ef-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="125ef-115">面板概述</span><span class="sxs-lookup"><span data-stu-id="125ef-115">Panels Overview</span></span>](panels-overview.md)
