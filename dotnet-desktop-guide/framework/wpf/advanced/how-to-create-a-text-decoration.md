---
title: 如何：创建文本修饰
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973454"
---
# <a name="how-to-create-a-text-decoration"></a>如何：创建文本修饰
<xref:System.Windows.TextDecoration>对象是可添加到文本的视觉对象装饰。 有四种类型的文本修饰：下划线、基线、删除线和上划线。 下面的示例演示文本修饰相对于文本的位置。  
  
 ![文本修饰类型示意图](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 若要向文本添加文本修饰，请创建 <xref:System.Windows.TextDecoration> 对象并修改其属性。 使用 " <xref:System.Windows.TextDecoration.Location%2A> 属性" 指定文本修饰的显示位置，如 "下划线"。 使用 " <xref:System.Windows.TextDecoration.Pen%2A> 属性" 指定文本修饰的外观，例如纯色填充或渐变颜色。 如果没有为属性指定值 <xref:System.Windows.TextDecoration.Pen%2A> ，则修饰的默认颜色与文本相同。 定义 <xref:System.Windows.TextDecoration> 对象后，将其添加到所 <xref:System.Windows.TextDecorations> 需文本对象的集合。  
  
 下面的示例演示了使用线性渐变画笔和虚线笔进行样式化的文本修饰。  
  
 ![采用线性渐变下划线的文本修饰](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <xref:System.Windows.Documents.Hyperlink>对象是一个内联级别的流内容元素，它允许您在流内容中承载超链接。 默认情况下， <xref:System.Windows.Documents.Hyperlink> 使用 <xref:System.Windows.TextDecoration> 对象显示下划线。 <xref:System.Windows.TextDecoration> 实例化对象的性能可能会很高，尤其是在有多个对象的情况下 <xref:System.Windows.Documents.Hyperlink> 。 如果您广泛使用了 <xref:System.Windows.Documents.Hyperlink> 元素，则可能需要考虑仅在触发事件（例如事件）时显示下划线 <xref:System.Windows.ContentElement.MouseEnter> 。  
  
 在下面的示例中，"我的 MSN" 链接的下划线是动态的，它仅在触发事件时才会出现 <xref:System.Windows.ContentElement.MouseEnter> 。  
  
 ![显示 TextDecoration 的超链接](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 有关详细信息，请参阅[指定是否为超链接添加下划线](how-to-specify-whether-a-hyperlink-is-underlined.md)。  
  
## <a name="example"></a>示例  
 在下面的代码示例中，下划线文本修饰使用默认字体值。  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 在下面的代码示例中，将使用画笔的纯色画笔创建下划线文本修饰。  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 在下面的代码示例中，用虚线笔的线性渐变画笔创建下划线文本修饰。  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [指定是否为超链接添加下划线](how-to-specify-whether-a-hyperlink-is-underlined.md)
