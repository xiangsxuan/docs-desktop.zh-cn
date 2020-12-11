---
title: 如何：定位 ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 851dc3c07e0abb4c7772f55f79900f1852b41232
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974063"
---
# <a name="how-to-position-a-tooltip"></a>如何：定位 ToolTip
此示例演示如何在屏幕上指定工具提示的位置。  
  
## <a name="example"></a>示例  
 您可以使用在和类中定义的五个属性集来定位工具提示 <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> 。 下表显示了这两组五个属性，并根据类提供指向其参考文档的链接。  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>根据类的相应工具提示属性  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> 类属性|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> 类属性|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 如果使用对象定义工具提示的内容 <xref:System.Windows.Controls.ToolTip> ，则可以使用任一类的属性; 但是， <xref:System.Windows.Controls.ToolTipService> 属性优先。 使用 <xref:System.Windows.Controls.ToolTipService> 未定义为对象的工具提示的属性 <xref:System.Windows.Controls.ToolTip> 。  
  
 下图演示了如何使用这些属性定位工具提示。 尽管 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 这些图中的示例演示如何设置由类定义的属性 <xref:System.Windows.Controls.ToolTip> ，但类的相应属性 <xref:System.Windows.Controls.ToolTipService> 遵循相同的布局规则。 有关位置属性的可能值的详细信息，请参阅 [Popup 放置行为](popup-placement-behavior.md)。  

 下图显示了使用 "位置" 属性的工具提示位置：  
  
 ![使用 "位置" 属性显示工具提示位置的关系图。](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 下图显示了使用位置和 System.windows.controls.primitives.popup.placementrectangle 属性的工具提示位置：

 ![使用 System.windows.controls.primitives.popup.placementrectangle 属性显示工具提示位置的关系图。](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 下图显示了使用 "位置"、"System.windows.controls.primitives.popup.placementrectangle" 和 "偏移" 属性的工具提示位置：
  
 ![使用 Offset 属性显示工具提示位置的关系图。](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 下面的示例演示如何使用 <xref:System.Windows.Controls.ToolTip> 属性指定其内容为对象的工具提示的位置 <xref:System.Windows.Controls.ToolTip> 。  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 下面的示例演示如何使用 <xref:System.Windows.Controls.ToolTipService> 属性指定其内容不是对象的工具提示的位置 <xref:System.Windows.Controls.ToolTip> 。  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [操作指南主题](tooltip-how-to-topics.md)
- [ToolTip 概述](tooltip-overview.md)
