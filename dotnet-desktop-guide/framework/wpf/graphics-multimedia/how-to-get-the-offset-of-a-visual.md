---
title: 如何：获取 Visual 的偏移量
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
ms.openlocfilehash: 4787b771c7e59a8b033b9267079c068a5845a1e6
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972686"
---
# <a name="how-to-get-the-offset-of-a-visual"></a>如何：获取 Visual 的偏移量
这些示例演示了如何检索相对于其父对象或任何祖先或后代的视觉对象的偏移量值。  
  
## <a name="example"></a>示例  
 以下标记示例演示了一个 <xref:System.Windows.Controls.TextBlock> 定义，其 <xref:System.Windows.FrameworkElement.Margin%2A> 值为4。  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 下面的代码示例演示如何使用 <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> 方法检索的偏移量 <xref:System.Windows.Controls.TextBlock> 。 偏移量值包含在返回值中 <xref:System.Windows.Vector> 。  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 偏移量会考虑 <xref:System.Windows.FrameworkElement.Margin%2A> 值。 在本例中， <xref:System.Windows.Vector.X%2A> 为4， <xref:System.Windows.Vector.Y%2A> 为4。  
  
 返回的偏移值是相对于的父的 <xref:System.Windows.Media.Visual> 。 如果要返回不是相对于的父对象的偏移量值 <xref:System.Windows.Media.Visual> ，请使用 <xref:System.Windows.Media.Visual.TransformToAncestor%2A> 方法。  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a>获取相对于祖先的偏移量  
 以下标记示例演示了 <xref:System.Windows.Controls.TextBlock> 嵌套在两个对象中的 <xref:System.Windows.Controls.StackPanel> 。  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 下图显示了标记的结果。  
  
 ![对象的偏移量值](./media/visualoffset-01.png "VisualOffset_01")  
TextBlock 嵌套在两个 StackPanels 中  
  
 下面的代码示例演示如何使用 <xref:System.Windows.Media.Visual.TransformToAncestor%2A> 方法检索 <xref:System.Windows.Controls.TextBlock> 相对于所包含的的偏移量 <xref:System.Windows.Window> 。 偏移量值包含在返回值中 <xref:System.Windows.Media.GeneralTransform> 。  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 偏移量将考虑 <xref:System.Windows.FrameworkElement.Margin%2A> 包含中的所有对象的值 <xref:System.Windows.Window> 。 在本例中， <xref:System.Windows.Vector.X%2A> 为 28 (16 + 8 + 4) ，且 <xref:System.Windows.Vector.Y%2A> 为28。  
  
 返回的偏移量值相对于的上级 <xref:System.Windows.Media.Visual> 。 如果要返回相对于子代的偏移量值 <xref:System.Windows.Media.Visual> ，请使用 <xref:System.Windows.Media.Visual.TransformToDescendant%2A> 方法。  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a>获取相对于子代的偏移量  
 以下标记示例显示了一个 <xref:System.Windows.Controls.TextBlock> 包含在对象中的 <xref:System.Windows.Controls.StackPanel> 。  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 下面的代码示例演示如何使用 <xref:System.Windows.Media.Visual.TransformToDescendant%2A> 方法检索相对于其子级的偏移量 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.TextBlock> 。 偏移量值包含在返回值中 <xref:System.Windows.Media.GeneralTransform> 。  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 偏移量会考虑 <xref:System.Windows.FrameworkElement.Margin%2A> 所有对象的值。 在此示例中， <xref:System.Windows.Vector.X%2A> 为-4，并且 <xref:System.Windows.Vector.Y%2A> 为-4。 偏移量值是负值，因为父对象相对于其子对象是负偏移。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- [WPF 图形呈现疑难解答](wpf-graphics-rendering-overview.md)
