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
# <a name="how-to-specify-a-custom-popup-position"></a>如何：指定自定义 Popup 位置
此示例演示如何 <xref:System.Windows.Controls.Primitives.Popup> 在属性设置为时指定控件的自定义位置 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> 。  
  
## <a name="example"></a>示例  
 当 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 属性设置为时 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> ，将 <xref:System.Windows.Controls.Primitives.Popup> 调用已定义的委托实例 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 。 此委托返回一组可能的点，这些点相对于目标区域的左上角和左上角 <xref:System.Windows.Controls.Primitives.Popup> 。 <xref:System.Windows.Controls.Primitives.Popup>放置在提供最佳可见性的点上。  
  
 下面的示例演示如何 <xref:System.Windows.Controls.Primitives.Popup> 通过将属性设置为来定义的位置 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> 。 它还演示如何创建和分配委托，以便 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 定位 <xref:System.Windows.Controls.Primitives.Popup> 。  回调委托返回两个 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> 对象。  如果在 <xref:System.Windows.Controls.Primitives.Popup> 第一个位置由屏幕边缘隐藏，则将 <xref:System.Windows.Controls.Primitives.Popup> 放置在第二个位置。  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 有关完整示例，请参阅 [Popup 放置示例](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Primitives.Popup>
- [弹出窗口概述](popup-overview.md)
- [操作指南文章](popup-how-to-topics.md)
