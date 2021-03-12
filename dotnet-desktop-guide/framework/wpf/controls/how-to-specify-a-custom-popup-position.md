---
title: 如何：指定自定义 Popup 位置
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: 758e3d82ce6dd795401aea2a6e27f47e74c4b5c3
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604298"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="5df09-102">如何：指定自定义 Popup 位置</span><span class="sxs-lookup"><span data-stu-id="5df09-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="5df09-103">此示例演示如何 <xref:System.Windows.Controls.Primitives.Popup> 在属性设置为时指定控件的自定义位置 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> 。</span><span class="sxs-lookup"><span data-stu-id="5df09-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5df09-104">示例</span><span class="sxs-lookup"><span data-stu-id="5df09-104">Example</span></span>  
 <span data-ttu-id="5df09-105">当 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 属性设置为时 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> ，将 <xref:System.Windows.Controls.Primitives.Popup> 调用已定义的委托实例 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 。</span><span class="sxs-lookup"><span data-stu-id="5df09-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="5df09-106">此委托返回一组可能的点，这些点相对于目标区域的左上角和左上角 <xref:System.Windows.Controls.Primitives.Popup> 。</span><span class="sxs-lookup"><span data-stu-id="5df09-106">This delegate returns a set of possible points that are relative to the top-left corner of the target area and the top-left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="5df09-107"><xref:System.Windows.Controls.Primitives.Popup>放置在提供最佳可见性的点上。</span><span class="sxs-lookup"><span data-stu-id="5df09-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="5df09-108">下面的示例演示如何 <xref:System.Windows.Controls.Primitives.Popup> 通过将属性设置为来定义的位置 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> 。</span><span class="sxs-lookup"><span data-stu-id="5df09-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="5df09-109">它还演示如何创建和分配委托，以便 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 定位 <xref:System.Windows.Controls.Primitives.Popup> 。</span><span class="sxs-lookup"><span data-stu-id="5df09-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="5df09-110">回调委托返回两个 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> 对象。</span><span class="sxs-lookup"><span data-stu-id="5df09-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="5df09-111">如果在 <xref:System.Windows.Controls.Primitives.Popup> 第一个位置由屏幕边缘隐藏，则将 <xref:System.Windows.Controls.Primitives.Popup> 放置在第二个位置。</span><span class="sxs-lookup"><span data-stu-id="5df09-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="5df09-112">有关完整示例，请参阅 [Popup 放置示例](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)。</span><span class="sxs-lookup"><span data-stu-id="5df09-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df09-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5df09-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="5df09-114">弹出窗口概述</span><span class="sxs-lookup"><span data-stu-id="5df09-114">Popup overview</span></span>](popup-overview.md)
- [<span data-ttu-id="5df09-115">操作指南文章</span><span class="sxs-lookup"><span data-stu-id="5df09-115">How-to articles</span></span>](popup-how-to-topics.md)
