---
title: 如何：使对象跟随鼠标指针移动
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: f348586341d0fa5b6e1a5fe15ab8c3a75e369e64
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972781"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>如何：使对象跟随鼠标指针移动
此示例演示当鼠标指针移动到屏幕上时如何更改对象的尺寸。  
  
 该示例包含一个 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 文件，该文件创建 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 和一个代码隐藏文件来创建事件处理程序。  
  
## <a name="example"></a>示例  
 下面的 XAML 创建一个 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] ，它包含内的 <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Controls.StackPanel> ，并附加事件的事件处理程序 <xref:System.Windows.UIElement.MouseMove> 。  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 下面的代码将创建 <xref:System.Windows.UIElement.MouseMove> 事件处理程序。  当鼠标指针移动时，的高度和宽度将 <xref:System.Windows.Shapes.Ellipse> 增加并减小。  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>另请参阅

- [输入概述](input-overview.md)
