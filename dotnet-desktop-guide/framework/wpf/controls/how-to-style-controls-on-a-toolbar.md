---
title: 如何：设置 ToolBar 上的控件的样式
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 22d3375b1177e13a1673e9720c1c241d7d3bfa08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970491"
---
# <a name="how-to-style-controls-on-a-toolbar"></a>如何：设置 ToolBar 上的控件的样式
<xref:System.Windows.Controls.ToolBar>定义 <xref:System.Windows.ResourceKey> 对象以指定中的控件的样式 <xref:System.Windows.Controls.ToolBar> 。  若要设置中控件的样式 <xref:System.Windows.Controls.ToolBar> ，请将 `x:key` 样式的特性设置为 <xref:System.Windows.ResourceKey> 中定义的 <xref:System.Windows.Controls.ToolBar> 。  
  
 <xref:System.Windows.Controls.ToolBar>定义以下 <xref:System.Windows.ResourceKey> 对象：  
  
- <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a>示例  
 下面的示例定义中的控件的样式 <xref:System.Windows.Controls.ToolBar> 。  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a>另请参阅

- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
