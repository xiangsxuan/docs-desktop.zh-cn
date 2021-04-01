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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974063"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="158e8-102">如何：定位 ToolTip</span><span class="sxs-lookup"><span data-stu-id="158e8-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="158e8-103">此示例演示如何在屏幕上指定工具提示的位置。</span><span class="sxs-lookup"><span data-stu-id="158e8-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="158e8-104">示例</span><span class="sxs-lookup"><span data-stu-id="158e8-104">Example</span></span>  
 <span data-ttu-id="158e8-105">您可以使用在和类中定义的五个属性集来定位工具提示 <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> 。</span><span class="sxs-lookup"><span data-stu-id="158e8-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="158e8-106">下表显示了这两组五个属性，并根据类提供指向其参考文档的链接。</span><span class="sxs-lookup"><span data-stu-id="158e8-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="158e8-107">根据类的相应工具提示属性</span><span class="sxs-lookup"><span data-stu-id="158e8-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="158e8-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> 类属性</span><span class="sxs-lookup"><span data-stu-id="158e8-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="158e8-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> 类属性</span><span class="sxs-lookup"><span data-stu-id="158e8-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="158e8-110">如果使用对象定义工具提示的内容 <xref:System.Windows.Controls.ToolTip> ，则可以使用任一类的属性; 但是， <xref:System.Windows.Controls.ToolTipService> 属性优先。</span><span class="sxs-lookup"><span data-stu-id="158e8-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="158e8-111">使用 <xref:System.Windows.Controls.ToolTipService> 未定义为对象的工具提示的属性 <xref:System.Windows.Controls.ToolTip> 。</span><span class="sxs-lookup"><span data-stu-id="158e8-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="158e8-112">下图演示了如何使用这些属性定位工具提示。</span><span class="sxs-lookup"><span data-stu-id="158e8-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="158e8-113">尽管 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 这些图中的示例演示如何设置由类定义的属性 <xref:System.Windows.Controls.ToolTip> ，但类的相应属性 <xref:System.Windows.Controls.ToolTipService> 遵循相同的布局规则。</span><span class="sxs-lookup"><span data-stu-id="158e8-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="158e8-114">有关位置属性的可能值的详细信息，请参阅 [Popup 放置行为](popup-placement-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="158e8-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  

 <span data-ttu-id="158e8-115">下图显示了使用 "位置" 属性的工具提示位置：</span><span class="sxs-lookup"><span data-stu-id="158e8-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![使用 "位置" 属性显示工具提示位置的关系图。](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 <span data-ttu-id="158e8-117">下图显示了使用位置和 System.windows.controls.primitives.popup.placementrectangle 属性的工具提示位置：</span><span class="sxs-lookup"><span data-stu-id="158e8-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>

 ![使用 System.windows.controls.primitives.popup.placementrectangle 属性显示工具提示位置的关系图。](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 <span data-ttu-id="158e8-119">下图显示了使用 "位置"、"System.windows.controls.primitives.popup.placementrectangle" 和 "偏移" 属性的工具提示位置：</span><span class="sxs-lookup"><span data-stu-id="158e8-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>
  
 ![使用 Offset 属性显示工具提示位置的关系图。](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="158e8-121">下面的示例演示如何使用 <xref:System.Windows.Controls.ToolTip> 属性指定其内容为对象的工具提示的位置 <xref:System.Windows.Controls.ToolTip> 。</span><span class="sxs-lookup"><span data-stu-id="158e8-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="158e8-122">下面的示例演示如何使用 <xref:System.Windows.Controls.ToolTipService> 属性指定其内容不是对象的工具提示的位置 <xref:System.Windows.Controls.ToolTip> 。</span><span class="sxs-lookup"><span data-stu-id="158e8-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="158e8-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="158e8-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="158e8-124">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="158e8-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="158e8-125">ToolTip 概述</span><span class="sxs-lookup"><span data-stu-id="158e8-125">ToolTip Overview</span></span>](tooltip-overview.md)
