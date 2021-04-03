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
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>如何：使用 DockPanel 元素对空间进行分区
下面的示例使用元素创建一个简单 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 框架 <xref:System.Windows.Controls.DockPanel> 。 将 <xref:System.Windows.Controls.DockPanel> 可用空间分区给其子元素。  
  
## <a name="example"></a>示例  
 此示例使用 <xref:System.Windows.Controls.DockPanel.Dock%2A> 属性，该属性是一个附加属性，用于将两个相同的 <xref:System.Windows.Controls.Border> 元素停靠在 <xref:System.Windows.Controls.Dock.Top> 分区空间的上。 第三个 <xref:System.Windows.Controls.Border> 元素停靠到 <xref:System.Windows.Controls.Dock.Left> ，其宽度设置为200像素。 第四个 <xref:System.Windows.Controls.Border> 停靠到 <xref:System.Windows.Controls.Dock.Bottom> 屏幕的。 最后一个 <xref:System.Windows.Controls.Border> 元素自动填充剩余的空间。  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> 默认情况下，元素的最后一个子 <xref:System.Windows.Controls.DockPanel> 元素会填充剩余的未分配空间。 如果不希望出现此行为，请设置 `LastChildFill="False"`。  
  
 已编译的应用程序将生成如下所示的新 UI。  
  
 ![典型的 DockPanel 方案。](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.DockPanel>
- [面板概述](panels-overview.md)
