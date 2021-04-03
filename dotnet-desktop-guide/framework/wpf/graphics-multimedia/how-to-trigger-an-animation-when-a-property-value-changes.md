---
title: 如何：在属性值更改时触发动画
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973508"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>如何：在属性值更改时触发动画
此示例演示如何使用在 <xref:System.Windows.Trigger> <xref:System.Windows.Media.Animation.Storyboard> 属性值更改时启动。 您可以 <xref:System.Windows.Trigger> 在 <xref:System.Windows.Style> 、或中使用 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.DataTemplate> 。  
  
## <a name="example"></a>示例  
 下面的示例使用在 <xref:System.Windows.Trigger> <xref:System.Windows.UIElement.Opacity%2A> <xref:System.Windows.Controls.Button> 其属性变为时对 a 的进行动画处理 <xref:System.Windows.UIElement.IsMouseOver%2A> `true` 。  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 属性对象应用的动画的 <xref:System.Windows.Trigger> 行为方式比 <xref:System.Windows.EventTrigger> 使用方法启动动画或动画更复杂 <xref:System.Windows.Media.Animation.Storyboard> 。  它们使用其他对象定义的动画 "切换" <xref:System.Windows.Trigger> ，但使用 <xref:System.Windows.EventTrigger> 和方法触发的动画进行组合。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Trigger>
- [属性动画技术概述](property-animation-techniques-overview.md)
- [演示图板概述](storyboards-overview.md)
