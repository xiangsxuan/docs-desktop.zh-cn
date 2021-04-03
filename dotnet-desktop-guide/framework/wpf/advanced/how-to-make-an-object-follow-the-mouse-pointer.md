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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972781"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="dd3e2-102">如何：使对象跟随鼠标指针移动</span><span class="sxs-lookup"><span data-stu-id="dd3e2-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="dd3e2-103">此示例演示当鼠标指针移动到屏幕上时如何更改对象的尺寸。</span><span class="sxs-lookup"><span data-stu-id="dd3e2-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="dd3e2-104">该示例包含一个 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 文件，该文件创建 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 和一个代码隐藏文件来创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="dd3e2-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd3e2-105">示例</span><span class="sxs-lookup"><span data-stu-id="dd3e2-105">Example</span></span>  
 <span data-ttu-id="dd3e2-106">下面的 XAML 创建一个 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] ，它包含内的 <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Controls.StackPanel> ，并附加事件的事件处理程序 <xref:System.Windows.UIElement.MouseMove> 。</span><span class="sxs-lookup"><span data-stu-id="dd3e2-106">The following XAML creates the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="dd3e2-107">下面的代码将创建 <xref:System.Windows.UIElement.MouseMove> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="dd3e2-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="dd3e2-108">当鼠标指针移动时，的高度和宽度将 <xref:System.Windows.Shapes.Ellipse> 增加并减小。</span><span class="sxs-lookup"><span data-stu-id="dd3e2-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="dd3e2-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd3e2-109">See also</span></span>

- [<span data-ttu-id="dd3e2-110">输入概述</span><span class="sxs-lookup"><span data-stu-id="dd3e2-110">Input Overview</span></span>](input-overview.md)
