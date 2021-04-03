---
title: 如何：创建自定义 Panel 元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973978"
---
# <a name="how-to-create-a-custom-panel-element"></a>如何：创建自定义 Panel 元素
## <a name="example"></a>示例  
 此示例演示如何重写元素的默认布局行为 <xref:System.Windows.Controls.Panel> ，并创建派生自的自定义布局元素 <xref:System.Windows.Controls.Panel> 。  
  
 该示例定义一个名为的简单自定义 <xref:System.Windows.Controls.Panel> 元素 `PlotPanel` ，该元素根据两个硬编码的 x 坐标和 y 坐标来定位子元素。 在此示例中， `x` 和均 `y` 设置为 `50` ; 因此，所有子元素都放置在 x 和 y 轴上的该位置。  
  
 若要实现自定义 <xref:System.Windows.Controls.Panel> 行为，该示例使用 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 和 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 方法。 每个方法都返回 <xref:System.Windows.Size> 定位和呈现子元素所必需的数据。  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Panel>
- [面板概述](panels-overview.md)
