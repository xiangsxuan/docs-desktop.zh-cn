---
title: 如何：获取或设置画布定位属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971034"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>如何：获取或设置画布定位属性
此示例演示如何使用元素的定位方法 <xref:System.Windows.Controls.Canvas> 来定位子内容。 此示例使用中的内容 <xref:System.Windows.Controls.ListBoxItem> 来表示定位值，并将值转换为的实例 <xref:System.Double> ，这是定位的必需参数。 然后，使用方法将这些值转换回字符串并在元素中显示为文本 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.Canvas.GetLeft%2A> 。  
  
## <a name="example"></a>示例  
 下面的示例创建一个 <xref:System.Windows.Controls.ListBox> 具有十一个可选择 <xref:System.Windows.Controls.ListBoxItem> 元素的元素。 此 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 事件触发 `ChangeLeft` 自定义方法，后面的代码块将定义该方法。  
  
 每个都 <xref:System.Windows.Controls.ListBoxItem> 表示一个 <xref:System.Double> 值，该值是接受的方法的参数之一 <xref:System.Windows.Controls.Canvas.SetLeft%2A> <xref:System.Windows.Controls.Canvas> 。 为了使用 <xref:System.Windows.Controls.ListBoxItem> 来表示的实例 <xref:System.Double> ，必须先将转换 <xref:System.Windows.Controls.ListBoxItem> 为正确的数据类型。  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 当用户更改 <xref:System.Windows.Controls.ListBox> 所选内容时，它会调用 `ChangeLeft` 自定义方法。 此方法将传递 <xref:System.Windows.Controls.ListBoxItem> 到一个 <xref:System.Windows.LengthConverter> 对象，该对象将 <xref:System.Windows.Controls.ContentControl.Content%2A> 的转换 <xref:System.Windows.Controls.ListBoxItem> 为 <xref:System.Double> (注意，此值已 <xref:System.String> 通过使用 <xref:System.Windows.Controls.Control.ToString%2A> 方法) 转换为。 然后，将此值传递回的 <xref:System.Windows.Controls.Canvas.SetLeft%2A> 和 <xref:System.Windows.Controls.Canvas.GetLeft%2A> 方法，以 <xref:System.Windows.Controls.Canvas> 更改对象的位置 `text1` 。  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [面板概述](panels-overview.md)
