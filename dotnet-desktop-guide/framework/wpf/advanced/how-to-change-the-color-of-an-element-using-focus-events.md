---
title: 如何：使用焦点事件更改元素的颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: c5c0520aa60f1906f2fb3f545c795ba0034a09bd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972587"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>如何：使用焦点事件更改元素的颜色
此示例演示如何在使用和事件时更改元素的颜色，并使其失去焦点 <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus> 。  
  
 此示例由一个 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 文件和一个代码隐藏文件组成。  
  
## <a name="example"></a>示例  
 以下 XAML 创建用户界面，该用户界面由两个 <xref:System.Windows.Controls.Button> 对象组成，并将和事件的事件处理程序附加 <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus> 到 <xref:System.Windows.Controls.Button> 对象。  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 下面的代码用于创建 <xref:System.Windows.UIElement.GotFocus> 和 <xref:System.Windows.UIElement.LostFocus> 事件处理程序。  当 <xref:System.Windows.Controls.Button> 获得键盘焦点时，的将 <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button> 更改为红色。  当 <xref:System.Windows.Controls.Button> 失去键盘焦点时，的将 <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button> 改回为白色。  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>另请参阅

- [输入概述](input-overview.md)
