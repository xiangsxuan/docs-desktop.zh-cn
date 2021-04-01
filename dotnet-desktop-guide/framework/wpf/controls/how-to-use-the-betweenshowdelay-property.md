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
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="ef36b-102">如何：使用 BetweenShowDelay 属性</span><span class="sxs-lookup"><span data-stu-id="ef36b-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="ef36b-103">此示例显示了如何使用 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time 属性，以便在用户将鼠标指针从一个工具提示直接移到另一个工具提示时快速显示工具提示（几乎无延迟）。</span><span class="sxs-lookup"><span data-stu-id="ef36b-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef36b-104">示例</span><span class="sxs-lookup"><span data-stu-id="ef36b-104">Example</span></span>  
 <span data-ttu-id="ef36b-105">在下面的示例中， <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 属性设置为1秒 (1000 毫秒) ， <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 设置为两秒钟 (2000 毫秒) 对于这两个控件的工具提示 <xref:System.Windows.Shapes.Ellipse> 。</span><span class="sxs-lookup"><span data-stu-id="ef36b-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="ef36b-106">如果为其中一个省略号显示工具提示，然后在两秒钟内将鼠标指针移动到另一个椭圆并在其上暂停，则会立即显示第二个椭圆的工具提示。</span><span class="sxs-lookup"><span data-stu-id="ef36b-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="ef36b-107">在以下任一情况下， <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 应用，这会导致第二个椭圆的工具提示在显示前等待一秒钟：</span><span class="sxs-lookup"><span data-stu-id="ef36b-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
- <span data-ttu-id="ef36b-108">如果移动到第二个按钮所用的时间超过两秒。</span><span class="sxs-lookup"><span data-stu-id="ef36b-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
- <span data-ttu-id="ef36b-109">如果工具提示在第一个椭圆的时间间隔开始时不可见，则为。</span><span class="sxs-lookup"><span data-stu-id="ef36b-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="ef36b-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef36b-110">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="ef36b-111">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="ef36b-111">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="ef36b-112">ToolTip 概述</span><span class="sxs-lookup"><span data-stu-id="ef36b-112">ToolTip Overview</span></span>](tooltip-overview.md)
