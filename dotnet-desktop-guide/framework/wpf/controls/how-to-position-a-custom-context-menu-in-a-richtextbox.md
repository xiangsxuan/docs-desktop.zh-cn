---
title: 如何：在 RichTextBox 中定位自定义上下文菜单
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: f9407f59c3daafd09fa5b84006f33ef2f3ebd31f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974062"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a>如何：在 RichTextBox 中定位自定义上下文菜单
此示例演示如何定位的自定义上下文菜单 <xref:System.Windows.Controls.RichTextBox> 。  
  
 当为 **RichTextBox** 定位自定义上下文菜单时，你负责处理上下文菜单的定位。  默认情况下，自定义上下文菜单在 **RichTextBox** 的中心打开。  
  
## <a name="example"></a>示例  
 若要重写默认放置行为，请为事件添加侦听器 <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> 。  下面的示例演示如何通过编程方式执行此操作。  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a>示例  
 下面的示例演示了相应的 <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> 事件侦听器的实现。  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a>另请参阅

- [RichTextBox 概述](richtextbox-overview.md)
- [TextBox 概述](textbox-overview.md)
