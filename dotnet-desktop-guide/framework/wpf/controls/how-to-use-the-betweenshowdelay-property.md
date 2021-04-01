---
title: 如何：使用 BetweenShowDelay 属性
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 9b63675ec21294496117860aa5b58af132c4284a
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972464"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a>如何：使用 BetweenShowDelay 属性
此示例显示了如何使用 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time 属性，以便在用户将鼠标指针从一个工具提示直接移到另一个工具提示时快速显示工具提示（几乎无延迟）。  
  
## <a name="example"></a>示例  
 在下面的示例中， <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 属性设置为1秒 (1000 毫秒) ， <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 设置为两秒钟 (2000 毫秒) 对于这两个控件的工具提示 <xref:System.Windows.Shapes.Ellipse> 。 如果为其中一个省略号显示工具提示，然后在两秒钟内将鼠标指针移动到另一个椭圆并在其上暂停，则会立即显示第二个椭圆的工具提示。  
  
 在以下任一情况下， <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 应用，这会导致第二个椭圆的工具提示在显示前等待一秒钟：  
  
- 如果移动到第二个按钮所用的时间超过两秒。  
  
- 如果工具提示在第一个椭圆的时间间隔开始时不可见，则为。  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [操作指南主题](tooltip-how-to-topics.md)
- [ToolTip 概述](tooltip-overview.md)
