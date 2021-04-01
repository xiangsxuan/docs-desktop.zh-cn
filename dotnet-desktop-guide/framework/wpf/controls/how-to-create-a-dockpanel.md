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
# <a name="how-to-create-a-dockpanel"></a>如何：创建 DockPanel
## <a name="example"></a>示例  
 下面的示例通过使用代码创建和使用的实例 <xref:System.Windows.Controls.DockPanel> 。 该示例演示如何通过创建五个 <xref:System.Windows.Shapes.Rectangle> 元素并定位 (停靠) 它们在父级中的位置来分区空间 <xref:System.Windows.Controls.DockPanel> 。 如果保留默认设置，则最后一个矩形会填充所有剩余的未分配空间。  
  
 [!code-csharp[DockPanelCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelCode/CSharp/DockPanel_Code.cs#1)]
 [!code-vb[DockPanelCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelCode/VisualBasic/dockpanel_vb.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Dock>
- [面板概述](panels-overview.md)
