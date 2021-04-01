---
title: 如何：使用事件创建翻转效果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: d4587b7b116045af11702a99c841956434f96404
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973459"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>如何：使用事件创建翻转效果
此示例演示如何在鼠标指针进入和离开元素占用的区域时更改元素的颜色。  
  
 此示例由一个 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 文件和一个代码隐藏文件组成。  
  
> [!NOTE]
> 此示例演示如何使用事件，但建议的方法是 <xref:System.Windows.Trigger> 在样式中使用。 有关详细信息，请参阅 [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)。  
  
## <a name="example"></a>示例  
 下面的 XAML 创建由围绕的组成的用户界面，并将 <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Input.Mouse.MouseEnter> 和 <xref:System.Windows.UIElement.MouseLeave> 事件处理程序附加到 <xref:System.Windows.Controls.Border> 。  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 下面的代码用于创建 <xref:System.Windows.UIElement.MouseEnter> 和 <xref:System.Windows.UIElement.MouseLeave> 事件处理程序。  当鼠标指针进入时 <xref:System.Windows.Controls.Border> ，的背景将 <xref:System.Windows.Controls.Border> 更改为红色。  当鼠标指针离开时 <xref:System.Windows.Controls.Border> ，的背景将 <xref:System.Windows.Controls.Border> 改回为白色。  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
